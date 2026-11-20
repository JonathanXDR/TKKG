# Checksums

Use these values to check that a download is complete and unchanged. If an image from the links in the [setup guide](../README.md#2-download-the-games) has different values, download it again. Images from other sources can have different values even when they're intact.

## How to check

In Terminal, this command prints the SHA-1 of every disc image in the `TKKG` folder:

```bash
shasum ~/TKKG/*.iso
```

This command prints the size of every disc image in bytes:

```bash
stat -f '%z %N' ~/TKKG/*.iso
```

In the Finder, File > Get Info also shows the size in bytes.

## Disc images

For TKKG 10 and the German Identikit, the values belong to the disc image extracted from the archive.

| Game | Disc image | Size (bytes) | SHA-1 |
| --- | --- | --- | --- |
| TKKG 1 | `TKKG 01.iso` | 319,299,584 | `714f76495fa6e836da8503958b175ab8c0def656` |
| TKKG 2 | `TKKG 02.iso` | 394,524,672 | `dc29de0429091c6afdc0603f3a4d8d8390284c4c` |
| TKKG 3 | `TKKG 03.iso` | 701,933,568 | `5894f7999e7553b162019a31027e0bf588255376` |
| TKKG 4 | `TKKG 04.iso` | 705,468,416 | `8a784ec666c9de15ed2e7fb086afe0c8a62ff391` |
| TKKG 5 | `TKKG 05.iso` | 706,058,240 | `2d808e93247c42e219ea806ff9af69a1141042ab` |
| TKKG 6 | `TKKG 06.iso` | 415,098,880 | `a22d2e8bfb1b2e848f067845cdde75efd5ac3dcc` |
| TKKG 7 | `TKKG7.iso` | 537,102,336 | `babca4878e795612d17b7afbdc87866cc6974449` |
| TKKG 8 | `TKKG8.iso` | 575,387,648 | `10d662bbada9222361331c17ad935b7b9726d2d7` |
| TKKG 9 | `TKKG9.iso` | 529,373,184 | `bbf0a3cbecacf35a4cb39d7899e94ee03c28d56e` |
| TKKG 10 | `TKKG.iso` | 392,865,792 | `21f46144acbc41bd2e3d25941ab6f0515969a61b` |
| TKKG 11 | `TKKG11.iso` | 512,897,024 | `7a860358d966dac9a2003b6ccec5e3832dd25a84` |
| TKKG 12 | `TKKG12.iso` | 480,014,336 | `a8202c4b0693c0ed9adef7880f4b51ec605e207d` |
| TKKG 13 | `TKKG13.iso` | 617,869,312 | `d2b0b4a167f7afb4ab78ca1bcad030212713faa9` |
| TKKG 14 | `TKKG14.iso` | 519,098,368 | `f3827ef988129a9eda27898df7bb6e782fc77421` |
| Identikit (EN) | `Identikit.iso` | 49,698,816 | `eda168d745314ec2781f92e477c675bd2d5f4215` |
| Identikit (DE) | `TKKG_Identikit_Ger.iso` | 69,984,256 | `da9e518dcbf3dfb0077287d5b6dfdece729a0749` |

## Mac OS 9 virtual machine

`mac-os-9.2.1-utm.zip` has the SHA-256 `13d2bb7db75bc4e8e94e181dd5ded1484a22dd07d5fe91a6464cde338400f508`. To check it before you unpack it, run this command:

```bash
shasum -a 256 ~/Downloads/mac-os-9.2.1-utm.zip
```

If Safari has already unpacked the zip, it's no longer in your Downloads folder, so you can't check it.

## Incomplete copies

Don't use these copies:

- TKKG 10 from the Internet Archive items `tkkg-10` and `tkkg-10.-panik.im.-internat.-setup`. Its disc image `TKKG 10.iso`, 365,789,184 bytes with SHA-1 `80e0afd3878e6e3ab52f5f7aaa1519680904c960`, is missing its last 26.8 MB.
- TKKG 6 from Macintosh Repository, the archive `tkkg6.iso_.sit` with SHA-1 `86594f41e849da8781e53511be6790f7400d5805`. Its disc image `TKKG6.iso`, 415,827,968 bytes with SHA-1 `8a44c141a1342ed46f6f5b8ca528212a4dca1d5c`, is missing its last 13.8 MB and has damaged game files.
- TKKG 6 from the Internet Archive item [`tkkg-6`](https://archive.org/details/tkkg-6), not the intact `tkkg-06`. Its disc image `TKKG6.iso`, 388,743,168 bytes with SHA-1 `b439f3332533ba2bc540ac2f7e3c56f08c769737`, contains only the Windows version of the game.

## Readmes from earlier releases

The Internet Archive images of TKKG 1 to 3 are later releases with a shorter readme or none. These readmes in `content` come from the earlier releases on Macintosh Repository.

| Files | Source release | Disc image | SHA-1 |
| --- | --- | --- | --- |
| [`content/TKKG1/LIESMICH.TXT`](../content/TKKG1/LIESMICH.TXT) | [TKKG 1 on Macintosh Repository](https://www.macintoshrepository.org/5387-tkkg-1-jennifer-is-missing) | `TKKG 1.cdr` | `e4e150291e8c109bbf9f8fa6581abdee0502562b` |
| [`content/TKKG2/LIESMICH.TXT`](../content/TKKG2/LIESMICH.TXT), [`LIESMICH_MAC.TXT`](../content/TKKG2/LIESMICH_MAC.TXT) | [TKKG 2 on Macintosh Repository](https://www.macintoshrepository.org/4794-tkkg-2-deadly-chocolate) | `TKKG 2.cdr` | `7e913a188c7b2e5cb513fcff320dc32f3cd426b0` |
| [`content/TKKG3/LIESMICH.TXT`](../content/TKKG3/LIESMICH.TXT), [`LIESMICH_MAC.TXT`](../content/TKKG3/LIESMICH_MAC.TXT) | [TKKG 3 on Macintosh Repository](https://www.macintoshrepository.org/3393-tkkg-3-the-mystery-of-the-mayan-treasure) | `TKKG3.iso` | `ee0a8a30963d3b39f51434a920794dd33ae99641` |
