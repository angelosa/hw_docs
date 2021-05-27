# Saturn/ST-V header info

On Saturn SW header is located in a root file (TODO: fill me)

On a ST-V cart SW header is located in the first 0x100 bytes in head of ic13 if available (interleaved) and first ROM if lies at 0x200000 of relative address.

## Format

From 0x00 to 0xbf all values are in ASCII, empty values are padded with 0x20 (empty space).

| rel location | description | typical values |
|--------------|-------------|----------------|
|0x00-0x0f|HW ID|STV: _SEGA ST-V(TITAN)_|
|0x10-0x1f|Manufacturer ID, usually prefixed with (C)|_(C)SUNSOFT_|
|0x20-0x29|Product ID, unused on STV?||
|0x2a-0x2f|Version number prefixed with a V|_V1.005_|
|0x30-0x37|Release date, in **%Y%m%d** format|_19950623_|
|0x38-0x3f|"Device invoice"|_CART-AM_|
||On STV carts: "CART-A" for (A)lone only cart, "CART-AM" for (A)lone + (M)ulti cart.||
||On Sports Fishing 2 (STV CD): "CD-1/1 C" ||
|0x40-0x49|Compatible area support: (J)apan, (U)sa & Canada, (E)urope, (T)aiwan & Philippines, (B)razil, (K)orea, (L)atin America, (A)sia PAL|_JUE_|
|0x4a-0x4f|Backup RAM info, unused on STV?||
|0x50-0x5f|"Reserved", Unused?||
|0x60-0x6f|Japanese game title|_SHANG.HAI BANRI_|
|0x70-0x7f|US game title|_TRIPLE THREAT_|
|0x80-0x8f|Euro game title|_TRIPLE THREAT_|
|0x90-0x9f|? game title||
|0xa0-0xaf|? game title||
|0xb0-0xbf|? game title||
|0xc0-0xc3|? used on STV|_0x28000000_|
|0xc8-0xcb|used on STV, cart crc32?|_0x158a6cf8_|
|0xe0-0xe3|On STV: Start pointer of program ROM space, relative to the ROM header mapping|_0x00001000_|
|0xe4-0xe7|Checksum on Saturn (check me), ? on STV (blanked mostly)||
|0xe8-0xeb|Initial Stack Pointer address for STV|_0x06100000_|

Other address in the 0xc0-0xff range are sometimes used, unknown purpose (TODO: check which)

Titles are displayed at POST for STV, routed by BIOS region.

If game is unsupported by the given region then last available game title is displayed with an **OPERATION OF THIS CARTRIDGE IS DISALLOWED IN THIS COUNTRY** message.

If game doesn't support Multi cart mode and BIOS is set to such then an **OPERATION OF THIS CARTRIDGE IS UNAVAILABLE WITH "MULTI-CART" mode** displays (and game test mode cannot be accessed).

## References

- [Preliminary Technical Bulletin #46. Data Cartridge Manual Ver. 1.00](https://antime.kapsi.fi/sega/files/ST-TECH-46.pdf)
