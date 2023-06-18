# List of Arcade games using PCI

- Last update 17th June 2023

- MAME driver refers to the current filename as found from [MAME drivers directory](https://github.com/mamedev/mame/tree/master/src/mame)

| MAME driver      | CPU class   | Motherboard | Northbridge | Southbridge | Video card | Sound card | Other |
|-|-|-|-|-|-|-|-|
|[atari/mediagx.cpp](https://github.com/mamedev/mame/tree/master/src/mame/atari/mediagx.cpp) | Cyrix MediaGX SoC | P5GX-LG | Cyrix MediaGX | Cyrix CX5510Rev2 | MediaGX VGA | Analog Devices AD1847JP |
|[funworld/photoply.cpp](https://github.com/mamedev/mame/tree/master/src/mame/funworld/photoply.cpp) | I486DX4 | ? | SiS85C496 | SiS85C497 | Cirrus Logic CL-GD5446 | AudioDrive ES1868F ISA | Winbond W83877AF Super I/O |
|[funworld/photoplys.cpp](https://github.com/mamedev/mame/tree/master/src/mame/funworld/photoplys.cpp) | Celeron FV524RX366 | ? | ? | Intel FW82801AA ICH / Intel N82802AB FWH / ITE IT8888F | ? | C-Media CMI8738 | Realtek RTL8139C Ethernet |
|[funworld/photoplysx.cpp](https://github.com/mamedev/mame/tree/master/src/mame/funworld/photoplysx.cpp) | CELERON SL6VR 2 GHz | I865G-based, Pm49FL004T-33JC | Intel 865G | Intel FW82801FR | Intel 865G + Extreme Graphics 2? | C-Media CMI9761A | Winbond W83627HF Super I/O / Realtek RTL8101L Ethernet / GNT FNW USB Token |
|[gaelco/gaelcopc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/gaelco/gaelcopc.cpp) | Pentium 3 or Celeron Socket 370? | _custom_ | Intel 82815 | Intel 82801 | nVidia GeForce 4 TI4200 (NV25) | RTM 560-25R | Intel 82562 LAN |
|[ice/frenzyxprss.cpp](https://github.com/mamedev/mame/tree/master/src/mame/ice/frenzyxprss.cpp) | Celeron SL5ZF Socket 370 | 694T Pro Ver 5 | Via VT82C686B | Via VT82C694T | InsideTNC IV011A a.k.a. GeForce2 MX/GTS (NV15/NV11) _superset?_ | Crystal CS4281-CM ||
|[jaleco/jaleco_vj_pc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/jaleco/jaleco_vj_pc.cpp) | _unknown, Pentium 1?_ | NMC-5VXC or EP-5BVPXB | Via VT82C585 Apollo VP,VPX,VPX-97 | Via VT82C586B | S3 Virge/DX Q5C2BB | | Winbond W83877F Super I/O |
|[konami/otomedius.cpp](https://github.com/mamedev/mame/tree/master/src/mame/konami/otomedius.cpp) | Intel Socket 478 Celeron SL6ZY | ? | Intel 82865G | Intel 82801EB ICH5 | ATI Radeon 9600XT | ? ||
|[merit/mtouchxl.cpp](https://github.com/mamedev/mame/tree/master/src/mame/merit/mtouchxl.cpp) | Intel 486DX4 | ? | SiS85C496 | SiS85C497 | Cirrus Logic GD-5440 _unconfirmed_ | CS4231 (Gravis Ultrasound MAX?) | |
|[midway/midqslvr.cpp](https://github.com/mamedev/mame/tree/master/src/mame/midway/midqslvr.cpp) (Quicksilver II) | Celeron (P2 equivalent) 333 MHz | Intel SE440BX-2 | Intel 82443BX | Intel i82371EB PIIX4 | Quantum Obsidian 3dfx Voodoo 2 | YMF740G (SE440BX on-board) | |
|[midway/midqslvr.cpp](https://github.com/mamedev/mame/tree/master/src/mame/midway/midqslvr.cpp) (Graphite) | Pentium III 733 MHz | BCM GT694VP | Via VT82C694X | Via VT82C686A | 3dfx Voodoo 3 | AC97 (VT82C686A on-board) or ES1373/CT5880 | SMC EZ Card 10 / SMC1208T Ethernet |
|[midway/pinball2k.cpp](https://github.com/mamedev/mame/tree/master/src/mame/midway/pinball2k.cpp) | Cyrix MediaGX SoC | ? | MediaGX | Cyrix CX5520 | MediaGX VGA | DCS2 custom ADSP-2104 | Prism custom PCI bridge / VS9824AG Super I/O, _unknown brand_ |
|[misc/astropc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/astropc.cpp) | Cyrix Media GXm (Pentium MMX core) | ? | | | Cyrix Media GXm 5530 VGA (gx86) | | |
|[misc/bntyhunt.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/bntyhunt.cpp) | Pentium III 1 GHz | ? | _Via based AGP_ | _Via based_ | nVidia GeForce 2 MX 200 (NV11) | Via VT82x ComboAudio a1u300a | |
|[misc/cavepc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/cavepc.cpp) | AMD Athlon 64 X2 5050e | Gigabyte GA-MA78GPM-UD2H _apparently_ | ? | ? | ATI Radeon HD 3200 | Realtek ALC1200 | Cave JVS "CV2000XP" |
|[misc/chameleonx1.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/chameleonx1.cpp) | Intel Pentium 4 Socket 478 | Asus P4B533-M | Intel 845E | Intel ICH4 | SUMA GFX 5600X 128MB SV3MDN0 a.k.a. nVidia GeForce FX 5600 (NV31) | Sound Blaster Live! 5.1 SB0220 | |
|[misc/comebaby.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/comebaby.cpp) | Intel Celeron Slot 1 633 MHz |PC Partner BXAS1-928 | Intel 82440BX | Intel I82371EB PIIX4 | 3dfx Voodoo 3 |OJU CTN CS-6500P with Cirrus Logic CS4281-CM | ITE 8671 Super I/O |
|[misc/ez2d.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/ez2d.cpp) (Amuseworld System IV, Ez2dancer 2nd Move) | Intel Celeron Socket 370 533 MHz |ASUS CUBX-103 | Intel i440BX-based | Intel i82371EB PIIX4-based | Leadtek Winfast 3D S325 32MB a.k.a. nVidia Riva TNT2 (NV5) | Sound Blaster Live CT4830 | Winbond W83977EF Super I/O / 3Com 3C90x EtherLink |
|[misc/funkball.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/funkball.cpp) | Cyrix MediaGX 233 MHz |VRender 2Beta Rev4 | Cyrix MediaGX | Cyrix CX5520 | MediaGX VGA (unused) / 3dfx Voodoo 1 | KS0164 MPU-401 based |  |
|[misc/gammagic.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/gammagic.cpp) | Pentium 1 133 MHz |MICRONICS M55Hi-Plus (with El Torito complaint BIOS) | Intel i430HX Tritorn II | Intel i82371SB PIIX3 | OAK SVGA PCI (unknown type) / 3dfx Voodoo 1 or 2 |Sound Blaster Vibra 16C  | Bally custom I/O board |
|[misc/gfamily.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/gfamily.cpp) | Intel Pentium 4 | ? | SiS651 | SiS962 | ? | ? | |
|[misc/globalvr.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/globalvr.cpp) | Intel Pentium 3 Socket 370? |? | Intel 8265G/PE/P / Intel 82875P GMCH | Intel 82801EB | nVidia Geforce 256 (NV10) _at very least_ | C-Media 3D Audio CMI8738 AC97 | Aladdin HASP USB or HASP PCMCIA |
|[misc/matrix.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/matrix.cpp) | Cyrix MediaGX GXm-266GP | GXM-530D | Media GXm | Cyrix GXm Cx5530  | Media GX VGA | ? | SMC FDC37C931 Super I/O |
|[misc/neomania.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/neomania.cpp) | _at least Pentium MMX_ | ? | ? | ? | _ATI mach 64-based_ | _Sound Blaster PCI-based_ | VGA/parallel port/sound passthru to JAMMA _NEO MANIA ADAPTER BOARD_ |
|[misc/odyssey.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/odyssey.cpp) (Thor) | Pentium 1 Socket 7 | Intel Advanced/ATX "Thor"
 | Intel 82437FX/82438FX i430FX Triton I | 82371FB PIIX | _Unknown_ | _Unknown_ | National Semiconductor PC87306B Super I/O |
|[misc/odyssey.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/odyssey.cpp) (Tucson) | Pentium 1 or MMX Socket 7 | Intel TC430HX "Tucson" | Intel 82439HX Triton II | Intel i82371SB PIIX3 | S3 Virge or Virge/DX on-board _, otherwise unknown_ | ? | National Semiconductor PC87306B Super I/O  |
|[misc/playcenter.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/playcenter.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/radikaldarts.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/radikaldarts.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/rawthrillspc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/rawthrillspc.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/rfslotspcpent.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/rfslotspcpent.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/savquest.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/savquest.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/silverball.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/silverball.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/skopro.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/skopro.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/startouch.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/startouch.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/voyager.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/voyager.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[misc/xtom3d.cpp](https://github.com/mamedev/mame/tree/master/src/mame/misc/xtom3d.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[namco/rbowlorama.cpp](https://github.com/mamedev/mame/tree/master/src/mame/namco/rbowlorama.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[pc/calchase.cpp](https://github.com/mamedev/mame/tree/master/src/mame/pc/calchase.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[pc/fruitpc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/pc/fruitpc.cpp) |<cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[pc/igspc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/pc/igspc.cpp) |<cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[pc/paokaipc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/pc/paokaipc.cpp) |<cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[pc/sis630.cpp](https://github.com/mamedev/mame/tree/master/src/mame/pc/sis630.cpp) (GameCristal) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[pc/quakeat.cpp](https://github.com/mamedev/mame/tree/master/src/mame/pc/quakeat.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[pc/queen.cpp](https://github.com/mamedev/mame/tree/master/src/mame/pc/queen.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[pc/newcanasta.cpp](https://github.com/mamedev/mame/tree/master/src/mame/pc/newcanasta.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[sega/chihiro.cpp](https://github.com/mamedev/mame/tree/master/src/mame/sega/chihiro.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[sega/lindbergh.cpp](https://github.com/mamedev/mame/tree/master/src/mame/sega/lindbergh.cpp) (Red) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[taito/taitotx.cpp](https://github.com/mamedev/mame/tree/master/src/mame/taito/taitotx.cpp) (Type X) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[taito/taitotx.cpp](https://github.com/mamedev/mame/tree/master/src/mame/taito/taitotx.cpp) (Type X+) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[taito/taitotx.cpp](https://github.com/mamedev/mame/tree/master/src/mame/taito/taitotx.cpp) (Type X7) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[taito/taitotx.cpp](https://github.com/mamedev/mame/tree/master/src/mame/taito/taitotx.cpp) (Type X2 & Satellite Terminal) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[taito/taitotx.cpp](https://github.com/mamedev/mame/tree/master/src/mame/taito/taitotx.cpp) (Type X Zero)| <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[taito/taitotx.cpp](https://github.com/mamedev/mame/tree/master/src/mame/taito/taitotx.cpp) (Type X3)| <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[taito/taitowlf.cpp](https://github.com/mamedev/mame/tree/master/src/mame/taito/taitowlf.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
|[unico/unianapc.cpp](https://github.com/mamedev/mame/tree/master/src/mame/unico/unianapc.cpp) | <cpuclass> |<motherboard> | <north> | <south> | <video> |<audio> | <extra> |
