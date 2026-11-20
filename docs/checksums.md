# Checksums

Use these values to check that a downloaded disc image is complete and unchanged. If an image from the sources in the [setup guide](../README.md#2-download-the-games) has different values, it's damaged or incomplete: download it again. Images from other sources have different values, even when they're intact.

## How to check

Run these commands in Terminal (Applications > Utilities). The setup guide keeps the disc images in a folder named `TKKG` in your home folder. This command prints the SHA-1 of every disc image there:

```bash
shasum ~/TKKG/*.iso
```

Each output line starts with the 40-character SHA-1, followed by the file's path. For a large disc image, the calculation takes a few seconds.

This command prints the size in bytes of every disc image, followed by its path:

```bash
stat -f '%z %N' ~/TKKG/*.iso
```

Without Terminal, select an image in the Finder and choose File > Get Info to see its size in bytes.

## Disc images

The Internet Archive lists the same size and SHA-1 for each of its files. TKKG 10 and the German Identikit come from Macintosh Repository as StuffIt archives, and their values belong to the disc images that The Unarchiver extracts.

The games were tested with these images, with two exceptions. The English Identikit hasn't been tested. TKKG 11 was tested with the image `TKKG11.iso` from [Macintosh Repository](https://www.macintoshrepository.org/3133-tkkg-11-film-ab-) (513,208,320 bytes, SHA-1 `f73b452ba77e0125eb9684e44f05ccc25dd95ea3`). Its Mac files are identical to those on the Internet Archive image, and the two images differ only in parts that Mac OS 9 doesn't read.

| Game | Source | Disc image | Size (bytes) | SHA-1 |
| --- | --- | --- | --- | --- |
| TKKG 1 | [tkkg-01](https://archive.org/details/tkkg-01) | `TKKG 01.iso` | 319,299,584 | `714f76495fa6e836da8503958b175ab8c0def656` |
| TKKG 2 | [tkkg-02](https://archive.org/details/tkkg-02) | `TKKG 02.iso` | 394,524,672 | `dc29de0429091c6afdc0603f3a4d8d8390284c4c` |
| TKKG 3 | [tkkg-03](https://archive.org/details/tkkg-03) | `TKKG 03.iso` | 701,933,568 | `5894f7999e7553b162019a31027e0bf588255376` |
| TKKG 4 | [tkkg-4_202605](https://archive.org/details/tkkg-4_202605) | `TKKG 04.iso` | 705,468,416 | `8a784ec666c9de15ed2e7fb086afe0c8a62ff391` |
| TKKG 5 | [tkkg-05](https://archive.org/details/tkkg-05) | `TKKG 05.iso` | 706,058,240 | `2d808e93247c42e219ea806ff9af69a1141042ab` |
| TKKG 6 | [tkkg-06](https://archive.org/details/tkkg-06) | `TKKG 06.iso` | 415,098,880 | `a22d2e8bfb1b2e848f067845cdde75efd5ac3dcc` |
| TKKG 7 | [tkkg-7_202201](https://archive.org/details/tkkg-7_202201) | `TKKG7.iso` | 537,102,336 | `babca4878e795612d17b7afbdc87866cc6974449` |
| TKKG 8 | [tkkg-8_202201](https://archive.org/details/tkkg-8_202201) | `TKKG8.iso` | 575,387,648 | `10d662bbada9222361331c17ad935b7b9726d2d7` |
| TKKG 9 | [tkkg-9_202201](https://archive.org/details/tkkg-9_202201) | `TKKG9.iso` | 529,373,184 | `bbf0a3cbecacf35a4cb39d7899e94ee03c28d56e` |
| TKKG 10 | [Macintosh Repository](https://www.macintoshrepository.org/2997-tkkg-10-panik-im-internat) | `TKKG.iso` | 392,865,792 | `21f46144acbc41bd2e3d25941ab6f0515969a61b` |
| TKKG 11 | [tkkg-11](https://archive.org/details/tkkg-11) | `TKKG11.iso` | 512,897,024 | `7a860358d966dac9a2003b6ccec5e3832dd25a84` |
| TKKG 12 | [tkkg-12](https://archive.org/details/tkkg-12) | `TKKG12.iso` | 480,014,336 | `a8202c4b0693c0ed9adef7880f4b51ec605e207d` |
| TKKG 13 | [tkkg-13](https://archive.org/details/tkkg-13) | `TKKG13.iso` | 617,869,312 | `d2b0b4a167f7afb4ab78ca1bcad030212713faa9` |
| TKKG 14 | [tkkg-14](https://archive.org/details/tkkg-14) | `TKKG14.iso` | 519,098,368 | `f3827ef988129a9eda27898df7bb6e782fc77421` |
| Identikit (English) | [Identikit](https://archive.org/details/Identikit) | `Identikit.iso` | 49,698,816 | `eda168d745314ec2781f92e477c675bd2d5f4215` |
| Identikit (German) | [Macintosh Repository](https://www.macintoshrepository.org/4209-tkkg-identikit) | `TKKG_Identikit_Ger.iso` | 69,984,256 | `da9e518dcbf3dfb0077287d5b6dfdece729a0749` |

## Macintosh Repository archives

These are the SHA-1 values that Macintosh Repository lists for its two downloads. If you still have the archives in your Downloads folder, this command prints their SHA-1:

```bash
shasum ~/Downloads/*.sit
```

| Game | Archive | SHA-1 |
| --- | --- | --- |
| TKKG 10 | `TKKG10.iso_.sit` | `88687b0d85353a9a86cb89cf0349ed43b086e205` |
| Identikit (German) | `tkkg_identikit_ger.iso_.sit` | `38e5f72832c81a0425bc9dfdcaa96a4d065ba9d9` |

## Incomplete copies

Don't use these copies:

- The TKKG 10 image on the Internet Archive (items `tkkg-10` and `tkkg-10.-panik.im.-internat.-setup`): `TKKG 10.iso`, 365,789,184 bytes, SHA-1 `80e0afd3878e6e3ab52f5f7aaa1519680904c960`. Its file systems end at byte 392,598,528, so the last 26.8 MB are missing.
- The TKKG 6 download on Macintosh Repository: the archive `tkkg6.iso_.sit` (SHA-1 `86594f41e849da8781e53511be6790f7400d5805`) contains `TKKG6.iso`, 415,827,968 bytes, SHA-1 `8a44c141a1342ed46f6f5b8ca528212a4dca1d5c`. Its Mac file system ends at byte 429,620,224, so the last 13.8 MB are missing, and several game files on it contain runs of zero bytes.
- The TKKG 6 item [`tkkg-6`](https://archive.org/details/tkkg-6) on the Internet Archive (not `tkkg-06`): `TKKG6.iso`, 388,743,168 bytes, SHA-1 `b439f3332533ba2bc540ac2f7e3c56f08c769737`. It contains only the Windows part of the disc, so it has no Mac version of the game.

## Readmes from earlier releases

The Internet Archive images of TKKG 1 to 3 are later releases. TKKG 1 has a shorter readme without the hidden hints, and TKKG 2 and 3 have no readme. These readmes in `content` come from the earlier releases on Macintosh Repository. The Mac readme of TKKG 1 is on both releases.

| Files | Source release | Disc image | SHA-1 |
| --- | --- | --- | --- |
| [`content/TKKG1/LIESMICH.TXT`](../content/TKKG1/LIESMICH.TXT) | [TKKG 1 on Macintosh Repository](https://www.macintoshrepository.org/5387-tkkg-1-jennifer-is-missing) | `TKKG 1.cdr` | `e4e150291e8c109bbf9f8fa6581abdee0502562b` |
| [`content/TKKG2/LIESMICH.TXT`](../content/TKKG2/LIESMICH.TXT), [`LIESMICH_MAC.TXT`](../content/TKKG2/LIESMICH_MAC.TXT) | [TKKG 2 on Macintosh Repository](https://www.macintoshrepository.org/4794-tkkg-2-deadly-chocolate) | `TKKG 2.cdr` | `7e913a188c7b2e5cb513fcff320dc32f3cd426b0` |
| [`content/TKKG3/LIESMICH.TXT`](../content/TKKG3/LIESMICH.TXT), [`LIESMICH_MAC.TXT`](../content/TKKG3/LIESMICH_MAC.TXT) | [TKKG 3 on Macintosh Repository](https://www.macintoshrepository.org/3393-tkkg-3-the-mystery-of-the-mayan-treasure) | `TKKG3.iso` | `ee0a8a30963d3b39f51434a920794dd33ae99641` |
