# Super A'Can per-game observations

## UM6619 (sound + system control)

### IRQ control

| romset   | irq_mask `$e90010` | frc control/freq `$e90014` / `$e90016` | irq notes |
| --- | --- | --- | --- |
| boomzoo | 0x80 | _frc not set_ ||
| formduel | 0xc8   | 0xa000 0xffff | _irq 3 `rte`_ ||
| gamblord | 0x00 -> 0xc0 -> 0xfe | 0xa20f 0x0xxx (normally 0x000a) ||
| jttlaugh | 0xc0 |_frc not set_ |_irq 3 `rte`, irq 4 populated with a jmp `$[ff]c036.w` -> `dc.w`_ |
| magipool | 0x00 -> 0xd8         | 0xa201 0x0104 ||
| monopoly | 0x00 -> 0xf8         | _frc not set_|_irq 1-3 `rte`, irq 4 with no-op stack push and pop, irq 5 valid, irq 6 `rte`_ |
| sangofgt | 0xb8 | _frc not set_ | _irq 3 shared with hblank timings?_ |
| slghtsag | 0x00 -> 0x80 | _frc not set_ | _fussy without a proper vblank mask_ |
| sonevil | 0x00 -> 0x80  | _frc not set_ | _irq 3 `rte`_ |
| speedyd | 0x80 on company logo, 0xa0 on intro, 0x80 otherwise | 0xa0d6 -> 0xa200 0x13a | _the only place that irq 3 matters is on logo ..._ |
| staiwbbl | 0xc0 | _frc ???_ | _irq 3 `rte`, irq 6 to a `jsr` -> `rts` |
