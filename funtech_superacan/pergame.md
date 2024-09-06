# Super A'Can per-game observations

## UM6618 (video)

### $f001f0

```
---x x--- P[ixel?] MODE
---0 0--- tile mode
---0 1--- bitmap mode
---1 0--- tile + special (???)
---1 x--- <not defined>
---- -xxx GFX mode
---- -000 2bpp-2bpp-2bpp-2bpp (1bpp selectable for all)
---- -001 4bpp-4bpp-2bpp (1bpp selectable for layer 2)
---- -010 8bpp-4bpp
---- -011 4bpp + linescroll-4bpp + linescroll-1bpp
---- -100 8bpp + linescroll-2bpp or 1bpp + linescroll
---- -1xx <reserved>
```

#### Per game

| romset ID | `$f001f0` | notes |
| --- | --- | --- |
| A'Can BIOS | 0x09 | |
| boomzoo | 0x01 | |
| formduel | 0x01 | |
| gamblord | 0x01 | |
| jttlaugh | 0x01 | |
| magipool | 0x01 | |
| monopoly | 0x01 | |
| sangofgt | 0x03 | linescroll particularly during gameplay |
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

```
[$+000]
-xx- ---- ---- ---- priority
---- xxx- ---- ---- tilemap page size (unknown values)
---- ---x ---- ---- 16x16 if set, otherwise 8x8
---- ---- x--- ---- 1bpp mode
---- ---- -x-- ---- color mix?
---- ---- --x- ---- wraparound?
---- ---- ---x xx-- mosaic
---- ---- ---- --x- global x flip (formduel)
---- ---- ---- ---x global y flip
```

```
[$+002]
-x-- ---- ---- ---- enable X linescroll
--x- ---- ---- ---- enable Y linescroll
---- xx-- ---- ---- <settings for linescroll, unknown purpose>
---- --x- ---- ---- per-tile priority for bit 15 (speedyd)
---- ---x ---- ---- <more unknown linescroll setting> (speedyd layer 2)
```

```
[$+004] scroll X & 0x7ff
```

```
[$+006] scroll Y & 0x7ff
```

```
[$+008] base tilemap pointer, << 5
```

```
[$+00a] base tile pointer, (value & 0xf800) << 13
```

```
[$+00c] X linescroll table, << 2
```

```
[+$00e] Y linescroll table?, << 2
```

```
[+$010] unknown Y table, applies to layer 1 only, (value & 0xffe0) << 7
```

### ROZ

TODO: fill me

### Sprites

TODO: fill me

## UM6619 (sound + system control)

### IRQ control

#### Main irqs:

1. expansion irq
2. cart irq
3. UM6619 timer overflow (gamblord, magipool, speedyd)
4. UM6618 horizontal retrace
5. UM6618 fixed-point trigger (sangofgt)
6. UM6619 from sound to main
7. UM6618 vertical retrace

#### Sound irqs:

- NMI UM6618 vertical retrace
2. "mouse move" DE-9 port 1
3. "mouse move" DE-9 port 2
4. from UM6619 PCRD signal, with 1->0 transitions (sample end?)
5. from 68k data timer
6. internal sound CYCLE END
7. internal sound timer

#### Per game

_TODO:

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
