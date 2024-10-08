# Super A'Can per-game observations

## UM6618 (video)

### `$f001f0`

```c++
---x x--- P[ixel?] MODE
---0 0--- tile mode
---0 1--- bitmap mode
---1 0--- tile + special (???)
---1 x--- <not defined>
---- -xxx GFX mode
---- -000 2bpp-2bpp-2bpp-2bpp (1bpp selectable for all)
---- -001 4bpp-4bpp-2bpp (1bpp selectable for layer 3)
---- -010 8bpp-4bpp
---- -011 (4bpp + linescroll)-(4bpp + linescroll)-1bpp
---- -100 (8bpp + linescroll)-(2bpp or 1bpp + linescroll)
---- -1xx <reserved>
```

Game observations:

| romset ID | `$f001f0` | notes |
| --- | --- | --- |
| A'Can BIOS | 0x09 | |
| boomzoo | 0x01 | |
| formduel | 0x01 | |
| gamblord | 0x01 | |
| jttlaugh | 0x01 | |
| magipool | 0x01 | |
| monopoly | 0x01 | |
| sangofgt | 0x03 | linescroll, particularly during gameplay |
| slghtsag | 0x04 | |
| sonevil | 0x01 during attract, 0x09 on new game intro | |
| speedyd | 0x01 | |
| staiwbbl | 0x03 | |

### Layers

Four normal layers + ROZ

$f00100-$f0011f layer 1

$f00120-$f0013f layer 2

$f00140-$f0015f layer 3

$f00160-$f0017f layer 4

```c++
[$+000]
?xx- ---- ---- ---- priority
                    \- on collisions higher number layer wins over lower. (speedyd, formduel, magipool)
---- xxx- ---- ---- tilemap page size
---- 000- ---- ---- 64x64
---- 001- ---- ---- 128x128
---- 010- ---- ---- 256x256
---- 011- ---- ---- 512x256
---- 100- ---- ---- 256x512
---- 101- ---- ---- 1024x256
---- 110- ---- ---- 512x512
---- 111- ---- ---- 256x1024
---- ---x ---- ---- 16x16 tiles if set, otherwise 8x8
---- ---- x--- ---- 1bpp mode
---- ---- -x-- ---- color mix?
---- ---- --x- ---- wraparound tilemap if enabled
---- ---- ---x xx-- mosaic
---- ---- ---- --x- global x flip (formduel)
---- ---- ---- ---x global y flip

[$+002]
-x-- ---- ---- ---- enable per-X scroll
--x- ---- ---- ---- enable per-Y scroll
---- x--- ---- ---- Line Y Select enable
---- -x-- ---- ---- <settings for linescroll, unknown purpose>
---- --x- ---- ---- per-tile priority thru bit 15 (speedyd / sonevil)
---- ---x ---- ---- <more unknown linescroll setting> (speedyd layer 2)

[$+004] scroll X & 0xfff, signed

[$+006] scroll Y & 0xfff, signed

[$+008] base tilemap pointer, << 5

[$+00a] base tile pointer, (value & 0xf800) << 13

[$+00c] per line X scroll table, << 2

[+$00e] line select table, << 2

[+$010] per line Y scroll table (presumably), applies to layer 1 only, (value & 0xffe0) << 7
```

Tile format is (mostly) identical for these, for ROZ and for sprites tables.

```c++
xxxx ---- ---- ---- palette base color
x--- ---- ---- ---- override with per-tile priority if setting enabled (will limit palette uses to $8-$f entries)
---- x--- ---- ---- flip X
---- -x-- ---- ---- flip Y
---- --xx xxxx xxxx tile entry
```

### ROZ

$f00180-$f0019f

```c++
[$180]
^^^^ ^^^^ ^^^^ -^^^ ^^-- same as regular layers (priority, tile paging etc.)
---- ---- ---- x--- ---- <ignored>
---- ---- ---- ---- --xx Select Color Mode
---- ---- ---- ---- --00 1bpp
---- ---- ---- ---- --01 2bpp
---- ---- ---- ---- --10 4bpp
---- ---- ---- ---- --11 8bpp

[$182] (note: different than above)
x--- ---- ---- ---- enable Y lineselect
-x-- ---- ---- ---- enable per-X scroll
---x ---- ---- ---- <unknown X related setting>
---- -x-- ---- ---- Line Y Select enable (note: different bit here)
---- --x- ---- ---- per-tile priority thru bit 15
---- ---x ---- ---- <unknown linescroll setting>
---- ---- -x-- ---- X select setting
---- ---- -0-- ---- use $18c base
---- ---- -1-- ---- use $198 per-line base
---- ---- ---x ---- Y select setting
---- ---- ---0 ---- use $190 base
---- ---- ---1 ---- use $19c per-line base
---- ---- ---- xxxx bitmap mode palette base

[$184]-[$186]
---- ---- xxxx xxxx
xxxx xxxx xxxx xxxx scroll X & 0xffffff, signed

[$188]-[$18a]
---- ---- xxxx xxxx
xxxx xxxx xxxx xxxx scroll Y & 0xffffff, signed

[$18c] incxx

[$18e] incyx

[$190] incyy

[$192] incxy

[$194] base tilemap pointer, << 5

[$196] base tile pointer, (value & 0xff80) << 9

[$198] X select thru [$182] bit 6, << 2

[$19a] per-line X base, << 2

[$19c] Y select thru [$182] bit 4, << 10

[$19e] line select table, << 2

```

TODO: examples here

### Sprites

$f00020-$f00027

32 sprites per scanline

320 sprites max per frame

```c++
[$020] sprite base address, (value & 0xfc00) << 2
[$022] sprite count, (value & 0x1ff) + 1
[$024] sprite monochrome color, (value & 0xff)
[$026]
---- ---- ---- ---x 8bpp/4bpp color depth
```

Sprite blocks are in 4 words units.

```c++
[+$000]
xxx- ---- ---- ---- sprite vertical zoom factor
010- ---- ---- ---- normal size (0x10000)
---x xxxx ---- ---- Y tile size
---- ---- xxxx xxxx Y position

[+$002]
xxx- ---- ---- ---- Tile bank
---- x--- ---- ---- flip X
---- -x-- ---- ---- flip Y
---- --x- ---- ---- 1bpp select?
---- ---x ---- ---- color mix?
---- ---- --xx x--- ???
---- ---- ---- -xxx X tile size

[+$004]
xxxx x--- ---- ---- sprite horizontal zoom factor
---- -xx- ---- ---- priority
---- ---x xxxx xxxx X position

[+$006]
xxxx xxxx xxxx xxxx sprite pointer block
```

### Video Control

$f00008

```c++
-x-- ---- ---- ---- <unknown>
--x- ---- ---- ---- <unknown>
---x ---- ---- ---- 4bpp/8bpp color mix select
---- x--- ---- ---- interlace
---- -x-- ---- ---- global double height
---- --x- ---- ---- overscan enable (0=240, 1=224)
---- ---x ---- ---- h320 mode, else 256
---- ---- x--- ---- enable layer 1
---- ---- -x-- ---- enable layer 2
---- ---- --x- ---- enable layer 3
---- ---- ---x ---- enable layer 4
---- ---- ---- x--- enable sprites
---- ---- ---- -x-- enable ROZ
---- ---- ---- --x- enable window clip layer 1
---- ---- ---- ---x enable window clip layer 2
```

### Window/Clipping Control

$f001d0 window 1

$f001d8 window 2

```c++
[+$000]
?xx- ---- ---- ---- priority? TODO: condition with layer collisions
---- x--- ---- ---- Reverse meaning?
---- -x-- ---- ---- color mix?
---- ---x ---- ---- Applies line table if enabled, otherwise just one entry for all (sangofgt, see below)
---- ---- xxxx xxxx color code

[+002] Table pointer, value << 2
Interleaves X start and end positions, word units & 0x1ff

[+004] Base X position, (value & 0x3ff) << 2

[+006] Base Y position, (value & 0x3ff) << 2
```

Clipping applies per-layer, thru `$f00008` bits 1 and 0.
In normal conditions the color code fills layer pixels if condition arises, essentially acting as
an opaque flag.

Following assumes that `$f00008` & 0x3 == 2, TBD 1 and especially 3 (both unused by any available SW).

| romset ID | `$f001d0` | table contents | notes |
| --- | --- | --- | --- |
| A'Can BIOS | 0x6802 | all zeroes | Wants 0x02 for the bg pen fill |
| boomzoo | 0x29af | strips of 0-0 intermixed with 0x0-0x0xff | Intro, clips wolf sprite on bottom |
| formduel | 0x090f | variable table | used on title screen for a circular clip |
| magipool | 0x89f0 | variable table | pre-title screen, circular clip |
| magipool | 0x01f8 | 0-0x141 | actual title screen, uses scroll registers to "fake" white opacity |
| sangofgt | 0x0805 | one entry, variable thru irq 4 | Used as an horizontal curtain effect |
| slghtsag | 0x0901 | variable table | On map screen, for a circular clip |
| speedyd | 0x01ff | strips of 0-0x140 intermixed with 0x0-0x0 | Intro, clips sprite clouds on top |

## UM6619 (sound + system control)

### IRQ control

#### Main irqs

1. expansion irq
2. cart irq
3. UM6619 timer overflow (gamblord, magipool, speedyd)
4. UM6618 horizontal retrace
5. UM6618 fixed-point trigger (sangofgt)
6. UM6619 from sound to main
7. UM6618 vertical retrace

#### Sound irqs

- NMI UM6618 vertical retrace

1. _unconnected_
2. "mouse move" DE-9 port 1
3. "mouse move" DE-9 port 2
4. from UM6619 PCRD signal, with 1->0 transitions (sample end on repeats?)
5. from 68k data timer
6. internal sound CYCLE END
7. internal sound timer

Game observations:

| romset ID | irq_mask `$e90010` | frc control/freq `$e90014` / `$e90016` | irq notes |
| --- | --- | --- | --- |
| boomzoo | 0x80 | _frc not set_ ||
| formduel | 0xc8   | 0xa000 0xffff | _irq 3 `rte`_ ||
| gamblord | 0x00 -> 0xc0 -> 0xfe | 0xa20f 0x0xxx (normally 0x000a) ||
| jttlaugh | 0xc0 |_frc not set_ |_irq 3 `rte`, irq 4 populated with a jmp `$[ff]c036.w` -> `dc.w`_ |
| magipool | 0x00 -> 0xd8         | 0xa201 0x0104 ||
| monopoly | 0x00 -> 0xf8         | _frc not set_|_irq 1-3 `rte`, irq 4 with no-op stack push and pop, irq 5 valid, irq 6 `rte`_ |
| sangofgt | 0xb8 | _frc not set_ | _uses irq 5 for raster effect at specific point_ |
| slghtsag | 0x00 -> 0x80 | _frc not set_ | _fussy without a proper vblank mask_ |
| sonevil | 0x00 -> 0x80  | _frc not set_ | _irq 3 `rte`_ |
| speedyd | 0x80 on company logo, 0xa0 on intro, 0x80 otherwise | 0xa0d6 -> 0xa200 0x13a | _irq 3 used as a gameplay timer of some sort_ |
| staiwbbl | 0xc0 | _frc ???_ | _irq 3 `rte`, irq 6 to a `jsr` -> `rts` |
