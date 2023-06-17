# List of Arcade games using PCI

- Last update 17th June 2023

- MAME driver refers to the current filename as found from [MAME drivers directory](https://github.com/mamedev/mame/tree/master/src/mame)

| MAME driver      | CPU class   | Motherboard | Northbridge | Southbridge | Video card | Sound card | Other |
|-|-|-|-|-|-|-|-|
|atari/mediagx.cpp | Cyrix MediaGX SoC | P5GX-LG | Cyrix MediaGX | Cyrix CX5510Rev2 | MediaGX VGA | Analog Devices AD1847JP |
|funworld/photoply.cpp | I486DX4 | ? | SiS85C496 | SiS85C497 | Cirrus Logic CL-GD5446 | AudioDrive ES1868F ISA | Winbond W83877AF Super I/O |
|funworld/photoplys.cpp | Celeron FV524RX366 | ? | ? | Intel FW82801AA ICH / Intel N82802AB FWH / ITE IT8888F | ? | C-Media CMI8738 | Realtek RTL8139C Ethernet |
|funworld/photoplysx.cpp | CELERON SL6VR 2 GHz | I865G-based, Pm49FL004T-33JC | Intel 865G | Intel FW82801FR | Intel 865G + Extreme Graphics 2? | C-Media CMI9761A | Winbond W83627HF Super I/O / Realtek RTL8101L Ethernet / GNT FNW USB Token |
|gaelco/gaelcopc.cpp | Pentium 3 or Celeron Socket 370? | _custom_ | Intel 82815 | Intel 82801 | nVidia GeForce 4 TI4200 (NV25) | RTM 560-25R | Intel 82562 LAN |
|ice/frenzyxprss.cpp | Celeron SL5ZF Socket 370 | 694T Pro Ver 5 | Via VT82C686B | Via VT82C694T | InsideTNC IV011A -> GeForce2 MX/GTS (NV15/NV11) superset? | Crystal CS4281-CM ||
|jaleco/jaleco_vj_pc.cpp | Pentium 1? | NMC-5VXC or EP-5BVPXB | Via VT82C585 Apollo VP,VPX,VPX-97 | Via VT82C586B | S3 Virge/DX Q5C2BB | | Winbond W83877F Super I/O |
|konami/otomedius.cpp | Intel Socket 478 Celeron SL6ZY | ? | Intel 82865G | Intel 82801EB ICH5 | ATI Radeon 9600XT | ? ||
|merit/mtouchxl.cpp | Intel 486DX4 | ? | SiS85C496 | SiS85C497 | Cirrus Logic GD-5440 _unconfirmed | CS4231 (Gravis Ultrasound MAX) | |
| midway/midqslvr.cpp (Quicksilver II) | Celeron (P2 equivalent) 333 MHz | Intel SE440BX-2 | Intel 82443BX | Intel i82371EB PIIX4 | Quantum Obsidian 3dfx Voodoo 2 | YMF740G (SE440BX on-board) | |
| midway/midqslvr.cpp (Graphite) | Pentium III 733 MHz | BCM GT694VP | Via VT82C694X | Via VT82C686A | 3dfx Voodoo 3 | AC97 (VT82C686A on-board) or ES1373/CT5880 | SMC EZ Card 10 / SMC1208T Ethernet |
| midway/pinball2k.cpp | Cyrix MediaGX SoC | ? | MediaGX | Cyrix CX5520 | MediaGX VGA | DCS2 custom ADSP-2104 | Prism custom PCI bridge / VS9824AG Super I/O, _unknown brand_ |
| misc/astropc.cpp | Pentium 4 based? _Award compressed block with custom astrok1.bmp boot image, SiS based?_ | ? | | | _unknown SVGA_ | | |
| misc/bntyhunt.cpp | Pentium III 1 GHz | ? | _Via based AGP_ | _Via based_ | nVidia GeForce 2 MX 200 (NV11) | Via VT82x ComboAudio a1u300a | |
| misc/cavepc.cpp | AMD Athlon 64 X2 5050e | Gigabyte GA-MA78GPM-UD2H _apparently_ | ? | ? | ATI Radeon HD 3200 | Realtek ALC1200 | Cave JVS "CV2000XP" |
| misc/chameleonx1.cpp | Intel Pentium 4 Socket 478 | Asus P4B533-M | Intel 845E | Intel ICH4 | SUMA GFX 5600X 128MB SV3MDN0 (?) | Sound Blaster Live! 5.1 SB0220 | |
| misc/comebaby.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/ez2d.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/funkball.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/gammagic.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/gfamily.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/globalvr.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/matrix.cpp | Cyrix MediaGX GXm-266GP |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/neomania.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/odyssey.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/playcenter.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/odyssey.cpp (Thor) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/odyssey.cpp (Tucson) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/playcenter.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/radikaldarts.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/rawthrillspc.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/rfslotspcpent.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/savquest.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/silverball.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/skopro.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/startouch.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/voyager.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| misc/xtom3d.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| namco/rbowlorama.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| pc/calchase.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| pc/fruitpc.cpp |<cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| pc/igspc.cpp |<cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| pc/paokaipc.cpp |<cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| pc/sis630.cpp (GameCristal) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| pc/quakeat.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| pc/queen.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| pc/newcanasta.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| sega/chihiro.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| sega/lindbergh.cpp (Red) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| taito/taitotx.cpp (Type X) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| taito/taitotx.cpp (Type X+) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| taito/taitotx.cpp (Type X7) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| taito/taitotx.cpp (Type X2 & Satellite Terminal) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| taito/taitotx.cpp (Type X Zero)| <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| taito/taitotx.cpp (Type X3)| <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| taito/taitowlf.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
| unico/unianapc.cpp | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
