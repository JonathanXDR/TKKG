# Accessing game data

These steps read files from the TKKG disc images on macOS without running the games, for example to look at the readme files or extract pictures and sound. They never change the contents of the images.

## How the discs are built

Every TKKG disc is a hybrid CD with two file systems:

- A Mac part in the classic HFS format (Mac OS Standard). It holds the Mac programs and readmes, along with Mac-only file information such as resource forks and file types.
- A Windows part in the ISO 9660 format. It holds the Windows programs and readmes.

Most game files, such as pictures, sound and other game data, appear in both parts.

macOS 10.15 Catalina and later can't mount classic HFS volumes, so double-clicking an image only shows an error. Use macOS's own tools for the Windows part and [hfsutils](https://www.mars.org/home/rob/proj/hfs/) for the Mac part.

The examples use `TKKG 1.cdr` in the current folder. Replace it with the path to your image, and keep the quotes when the name contains spaces.

## Windows part (ISO 9660)

### Extract files with tar

The `tar` command built into macOS reads ISO 9660 images. To list all files on the Windows part:

```sh
tar -tf "TKKG 1.cdr"
```

To extract one file, or everything, into a new folder:

```sh
mkdir -p tkkg1
tar -xf "TKKG 1.cdr" -C tkkg1 LIESMICH.TXT
tar -xf "TKKG 1.cdr" -C tkkg1
```

The extracted files are read-only, as on the CD.

Text files on the Windows part use the Windows-1252 character set and Windows line endings. To convert one to UTF-8 with Unix line endings:

```sh
iconv -f WINDOWS-1252 -t UTF-8 tkkg1/LIESMICH.TXT | tr -d '\r' > LIESMICH.txt
```

The Unarchiver and `unar` can open these images too, but they only see the Windows part.

### Mount the Windows part as a volume

To browse the Windows part in the Finder, attach the image without mounting it, then mount it read-only. You don't need administrator rights, because you own the mount folder.

```sh
mkdir -p ~/tkkg-iso
device=$(hdiutil attach -readonly -nomount "TKKG 1.cdr" | head -n 1 | awk '{print $1}')
mount -t cd9660 -o rdonly "$device" ~/tkkg-iso
```

The first line of the `hdiutil` output names the whole disk device, for example `/dev/disk4`. Mount that device, because the ISO 9660 file system starts at the beginning of the image.

When you're done, unmount it and detach the image:

```sh
umount ~/tkkg-iso
hdiutil detach "$device"
```

If you opened a new Terminal window in the meantime, `$device` is empty. Run `hdiutil info` to find the `/dev/disk` name of the image and pass it to `hdiutil detach`.

On macOS 27, `hdiutil attach` and `hdiutil detach` print a deprecation warning but still work. The new equivalents are `diskutil image attach --readOnly --noMount "TKKG 1.cdr"` and `diskutil eject "$device"`.

## Mac part (HFS)

hfsutils reads and copies files from classic HFS volumes. Install it with [Homebrew](https://brew.sh/):

```sh
brew install hfsutils
```

Remove write permission from the image first. hfsutils then opens the volume read-only and reports it as locked.

```sh
chmod a-w "TKKG 1.cdr"
hmount "TKKG 1.cdr"
```

hfsutils finds the HFS partition by itself and keeps the mounted volume as its current volume until you run `humount`. Paths use colons instead of slashes, and a path that starts with a colon is relative to the current folder.

To list the top folder, including invisible files, then list a game folder and change into it:

```sh
hls -la
hls -l ':TKKG 1'
hcd ':TKKG 1'
```

To copy a file with its resource fork, as a MacBinary file:

```sh
hcopy -m 'Lies mich' ~/Desktop/Lies-mich.bin
```

To copy a text file with converted line endings and characters, then turn it into UTF-8:

```sh
hcopy -t 'Lies mich' ~/Desktop/Lies-mich.txt
iconv -f ISO-8859-1 -t UTF-8 ~/Desktop/Lies-mich.txt > ~/Desktop/Lies-mich-utf8.txt
```

To release the image:

```sh
humount
```

- `hls -l` shows each file's type and creator codes. The type `APPL` marks programs, and `TEXT` marks text files.
- `hcopy` can't copy folders, but it copies several files at once into an existing folder. For example, `hcopy -r '*' ~/Desktop/tkkg1-mac/` copies all files of the current folder. hcopy replaces spaces in file names with underscores.
- `hcopy -m` keeps the resource fork by writing a MacBinary (`.bin`) file. `unar` or The Unarchiver turns it back into a file with its resource fork.
- `hcopy -t` converts Mac line endings and characters to Unix line endings and ISO 8859-1 (Latin-1).
- `hcopy -r` copies only the data fork, without any conversion. Mac text copied this way is in the Mac OS Roman character set: convert it with `iconv -f MACINTOSH -t UTF-8` and `tr '\r' '\n'`.

Run `chmod u+w "TKKG 1.cdr"` afterwards if you want the image writable again.
