# Accessing game data

This page shows how to read files from the TKKG disc images on macOS without running the games, for example to look at the readme files or extract pictures and sound. The commands never change the contents of the images.

## How the discs are built

Every TKKG disc is a hybrid CD with two file systems:

- A Mac part in the classic HFS format (Mac OS Standard). It holds the Mac programs and readmes, along with Mac-only file information such as resource forks and file types.
- A Windows part in the ISO 9660 format. It holds the Windows programs and readmes.

Most game files, such as pictures, sound and other game data, appear in both parts.

macOS 10.15 Catalina and later can't mount classic HFS volumes, so double-clicking an image only shows an error. Use macOS's own tools for the Windows part and [hfsutils](https://www.mars.org/home/rob/proj/hfs/) for the Mac part.

## Choose a disc image

The commands below use the shell variable `image`, which holds the path of the disc image. This example selects TKKG 1 in the `TKKG` folder that the [setup guide](../README.md#setup) uses. For another disc, change the file name inside the quotes:

```bash
image="$HOME/TKKG/TKKG 01.iso"
```

Run all following commands in the same Terminal window, because a new window doesn't know the variable. The file and folder names in the examples, such as `LIESMICH.TXT`, `TKKG 1` and `Lies mich`, come from the TKKG 1 disc. For another disc, take the names from the `tar -tf` or `hls` listing.

## Windows part (ISO 9660)

### Extract files with tar

The `tar` command built into macOS reads ISO 9660 images. To list all files on the Windows part:

```bash
tar -tf "$image"
```

To extract one file into a new folder `tkkg-pc` on your Desktop:

```bash
mkdir -p ~/Desktop/tkkg-pc
tar -xf "$image" -C ~/Desktop/tkkg-pc LIESMICH.TXT
```

To extract every file of the Windows part:

```bash
mkdir -p ~/Desktop/tkkg-pc
tar -xf "$image" -C ~/Desktop/tkkg-pc
```

The extracted files are read-only, as on the disc.

Text files on the Windows part use the Windows-1252 character set and Windows line endings. This command saves a UTF-8 copy with Unix line endings next to the original:

```bash
iconv -f WINDOWS-1252 -t UTF-8 ~/Desktop/tkkg-pc/LIESMICH.TXT | tr -d '\r' > ~/Desktop/tkkg-pc/LIESMICH-utf8.txt
```

The Unarchiver and `unar` can open these images too, but they only see the Windows part.

### Mount the Windows part as a volume

To browse the Windows part in the Finder, attach the image without mounting it, then mount it read-only. You don't need administrator rights, because you own the mount folder.

```bash
mkdir -p ~/tkkg-iso
device=$(hdiutil attach -readonly -nomount "$image" | head -n 1 | awk '{print $1}')
mount -t cd9660 -o rdonly "$device" ~/tkkg-iso
```

The first line of the `hdiutil` output names the whole disk device, for example `/dev/disk4`. The commands mount that device, because the ISO 9660 file system starts at the beginning of the image.

The Windows part now appears in the `tkkg-iso` folder in your home folder. This command opens it in the Finder:

```bash
open ~/tkkg-iso
```

When you're done, unmount it and detach the image:

```bash
umount ~/tkkg-iso
hdiutil detach "$device"
```

If you opened a new Terminal window in the meantime, the `device` variable is empty. This command lists the attached images with their device names:

```bash
hdiutil info
```

Then detach the image. Replace `diskN` with the first `/dev/disk` name listed below the image's `image-path` line, for example `disk4`:

```bash
hdiutil detach /dev/diskN
```

On macOS 27, `hdiutil attach` and `hdiutil detach` print a deprecation warning but still work. To use the new `diskutil image` commands instead, mount the image with these commands:

```bash
mkdir -p ~/tkkg-iso
device=$(diskutil image attach --readOnly --noMount "$image" | head -n 1 | awk '{print $1}')
mount -t cd9660 -o rdonly "$device" ~/tkkg-iso
```

To unmount it and eject the image:

```bash
umount ~/tkkg-iso
diskutil eject "$device"
```

## Mac part (HFS)

hfsutils reads and copies files from classic HFS volumes. Install it with [Homebrew](https://brew.sh/):

```bash
brew install hfsutils
```

Remove write permission from the image, then mount it. Because the image is read-only, hfsutils opens the volume read-only and reports it as locked.

```bash
chmod a-w "$image"
hmount "$image"
```

hfsutils finds the HFS partition by itself and keeps the mounted volume as its current volume until you release it. Paths use colons instead of slashes, and a path that starts with a colon is relative to the current folder. The following examples use the folder and file names of the TKKG 1 disc.

To list the top folder, including invisible files:

```bash
hls -la
```

To list the game folder and change into it:

```bash
hls -l ':TKKG 1'
hcd ':TKKG 1'
```

`hls -l` shows each file's type and creator codes. The type `APPL` marks programs, and `TEXT` marks text files.

### Copy files

To copy a file with its resource fork, as a MacBinary file:

```bash
hcopy -m 'Lies mich' ~/Desktop/Lies-mich.bin
```

The Unarchiver or `unar` turns a MacBinary file back into a file with its resource fork. This command puts the file `Lies mich` on your Desktop:

```bash
unar -o ~/Desktop ~/Desktop/Lies-mich.bin
```

`hcopy -t` converts Mac line endings and characters to Unix line endings and ISO 8859-1 (Latin-1). To copy a text file this way and turn it into UTF-8:

```bash
hcopy -t 'Lies mich' ~/Desktop/Lies-mich.txt
iconv -f ISO-8859-1 -t UTF-8 ~/Desktop/Lies-mich.txt > ~/Desktop/Lies-mich-utf8.txt
```

To copy only the data fork, without any conversion, use `hcopy -r`. Mac text copied this way stays in the Mac OS Roman character set with Mac line endings, so convert it like this:

```bash
hcopy -r 'Lies mich' ~/Desktop/Lies-mich.raw
iconv -f MACINTOSH -t UTF-8 ~/Desktop/Lies-mich.raw | tr '\r' '\n' > ~/Desktop/Lies-mich-mac.txt
```

`hcopy` can't copy folders, but it copies several files at once into an existing folder. These commands copy all files of the current folder into `tkkg-mac` on your Desktop. `hcopy` replaces spaces in the file names with underscores.

```bash
mkdir -p ~/Desktop/tkkg-mac
hcopy -r '*' ~/Desktop/tkkg-mac/
```

### Release the image

When you're done, release the image:

```bash
humount
```

If you want to make the image writable again, run this command. If you opened a new Terminal window in the meantime, set `image` again as in [Choose a disc image](#choose-a-disc-image) first.

```bash
chmod u+w "$image"
```
