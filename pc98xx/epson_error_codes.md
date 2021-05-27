# Epson PC-* error codes

Epson PC-98 clones returns a specific set of errors

At current stage it is unknown if these also applies to N5200/APC III business class machines.

(kudos to [DFJustin](https://github.com/DopefishJustin) for translating these)

| error code | beeps (S=short, L=long) | description |
|------------|-------------------------|-------------|
|ERR:R0|S|ROM BIOS problem (checksum error)|
|ERR:RA|SS|Conventional RAM problem (r/w error on 640kB)|
|ERR:VR:|SSS|Graphic VRAM problem (r/w)|
|ERR:BR|SSSS|BIOS load error|
|ERR:MW|SL|RAM window problem (boot continues)|
|ERR:CC|SSL|Cache controller problem (boot continues)|
|ERR:TB|SSSL|Tablet problem|
|ERR:EP|L|Unable to correctly read soft DIP switch (SDIP)|
|ERR:TM|LS|Problem with timer IC (PIT8253)|
|ERR:DM|LSS|DMA controller problem (AM9517A)|
|ERR:IR|LSSS|Interrupt controller problem (PIC8259)|
|ERR:CG|LSSSS|CG window problem|
|ERR:GC|LL|Graphic charger problem (GRCG)|
|ERR:PA|LLS|Page frame error|
|ERR:HD|LLS|HDD buffer problem|
|ERR:RM|LLSS|Internal expansion memory problem|
|ERR:TV|LLSSS|Text VRAM problem (master μPD7220)|
|ERR:ST|LLL|1MB region wraparound error (segment?)|
|Parity Check Error|L|IOCHK signal (NMI) input from expansion slot|
|SYSTEM SHUTDOWN ERROR|continuous|High-res mode reset error|

## References

- [エプソン98互換機の自動チェック機能によるエラーメッセージ](https://98epjunk.shakunage.net/miscel/ep_errors.html)
