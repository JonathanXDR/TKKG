# Checksums

Use these values to check that a download and its extracted disc image are complete and unchanged.

To get a file's SHA-1, open Terminal (Applications > Utilities), type `shasum` followed by a space, drag the file from the Finder onto the Terminal window and press Return. Terminal prints a 40-character value and then the file's path. For a large disc image this takes a few seconds. To see a file's size in bytes, select it in the Finder and choose File > Get Info. If a value differs from the table, download or extract the file again.

## Game downloads

The archive SHA-1 values are the ones Macintosh Repository lists on each download page. The TKKG 2 page names its archive `tkkg_2.cdr_.sit`, but Safari saves it as `tkkg2.cdr_.sit`. The disc image values were measured on the images that The Unarchiver extracts from those archives. TKKG 6 comes from the [Internet Archive item tkkg-06](https://archive.org/details/tkkg-06) as a plain disc image.

| Game | Archive | Archive SHA-1 | Disc image | Image size (bytes) | Image SHA-1 |
| --- | --- | --- | --- | --- | --- |
| TKKG 1 | `tkkg1.cdr_.sit` | `8ad5d14414b0acb1e44568e57f905749dbc07834` | `TKKG 1.cdr` | 303,118,336 | `e4e150291e8c109bbf9f8fa6581abdee0502562b` |
| TKKG 2 | `tkkg2.cdr_.sit` | `48bc804c16114d9a5ab825270f7a55ec3996f63a` | `TKKG 2.cdr` | 373,301,248 | `7e913a188c7b2e5cb513fcff320dc32f3cd426b0` |
| TKKG 3 | `tkkg3.iso_.sit` | `63d968629f335cbdc52e59fdf4d3e1ea820e9692` | `TKKG3.iso` | 709,691,392 | `ee0a8a30963d3b39f51434a920794dd33ae99641` |
| TKKG 4 | `tkkg4.cdr_.sit` | `babb772959417328fa91e60aba2f808174d9ae79` | `TKKG4.cdr` | 705,464,320 | `cff31b87738cadfd7e4e593e8e74742833538873` |
| TKKG 5 | `tkkg5.iso_.sit` | `b0bd5e2fe25acf04e3cec867e8511ccaf250ea44` | `TKKG5.iso` | 373,704,704 | `9b9b3285a65b147b3f7545e8baefc4c1323ab356` |
| TKKG 6 | none (Internet Archive) | none | `TKKG 06.iso` | 415,098,880 | `a22d2e8bfb1b2e848f067845cdde75efd5ac3dcc` |
| TKKG 7 | `tkkg7.iso_.sit` | `abe2e3226c332c3111c666d0221670fef177e4f9` | `TKKG7.iso` | 537,102,336 | `babca4878e795612d17b7afbdc87866cc6974449` |
| TKKG 8 | `tkkg8.iso_.sit` | `73923182e7d022f7f89aef5fbd624ddfe182d1ff` | `TKKG8.iso` | 575,387,648 | `10d662bbada9222361331c17ad935b7b9726d2d7` |
| TKKG 9 | `tkkg9.iso_.sit` | `bb1c3b07f8af2044b2fd2823e87a18f9acf577e5` | `TKKG9.iso` | 529,373,184 | `bbf0a3cbecacf35a4cb39d7899e94ee03c28d56e` |
| TKKG 10 | `TKKG10.iso_.sit` | `88687b0d85353a9a86cb89cf0349ed43b086e205` | `TKKG.iso` | 392,865,792 | `21f46144acbc41bd2e3d25941ab6f0515969a61b` |
| TKKG 11 | `TKKG11.iso_.sit` | `07564f7bc3a12a4682d17f5b2dff93263f21f8ad` | `TKKG11.iso` | 513,208,320 | `f73b452ba77e0125eb9684e44f05ccc25dd95ea3` |
| TKKG 12 | `TKKG12.iso_.sit` | `aed4566a51a4fe403bd45a76ff7b69d7dad8a4df` | `TKKG12.iso` | 480,014,336 | `a8202c4b0693c0ed9adef7880f4b51ec605e207d` |
| TKKG 13 | `TKKG13.iso_.sit` | `cfe6981a76da4932a9b72ce0b92e6c166ecc53e9` | `TKKG13.iso` | 617,869,312 | `d2b0b4a167f7afb4ab78ca1bcad030212713faa9` |
| TKKG 14 | `TKKG14.iso_.sit` | `872bcedb2094ec74ca67f6e8da0a256024e40071` | `TKKG14.iso` | 519,098,368 | `f3827ef988129a9eda27898df7bb6e782fc77421` |
| Identikit | `tkkg_identikit_ger.iso_.sit` | `38e5f72832c81a0425bc9dfdcaa96a4d065ba9d9` | `TKKG_Identikit_Ger.iso` | 69,984,256 | `da9e518dcbf3dfb0077287d5b6dfdece729a0749` |

Don't use the TKKG 6 download from Macintosh Repository. Its archive `tkkg6.iso_.sit` (SHA-1 `86594f41e849da8781e53511be6790f7400d5805`) contains a damaged `TKKG6.iso` of 415,827,968 bytes (SHA-1 `8a44c141a1342ed46f6f5b8ca528212a4dca1d5c`). Its Mac file system ends at byte 429,620,224, so the last 13.8 MB are missing. The intact `TKKG 06.iso` is a different edition with a smaller file system, which is why it is shorter.
