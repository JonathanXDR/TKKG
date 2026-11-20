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

To extract files, first create a folder `tkkg-pc` on your Desktop:

```bash
mkdir -p ~/Desktop/tkkg-pc
```

Then extract one file, such as the readme:

```bash
tar -xf "$image" -C ~/Desktop/tkkg-pc LIESMICH.TXT
```

Or extract every file of the Windows part:

```bash
tar -xf "$image" -C ~/Desktop/tkkg-pc
```

The extracted files are read-only, as on the disc.

Text files on the Windows part use the Windows-1252 character set and Windows line endings. This command saves a UTF-8 copy with Unix line endings next to the original:

```bash
iconv -f WINDOWS-1252 -t UTF-8 ~/Desktop/tkkg-pc/LIESMICH.TXT | tr -d '\r' > ~/Desktop/tkkg-pc/LIESMICH-utf8.txt
```

The Unarchiver and `unar` can open these images too, but they only see the Windows part.

## Mac part (HFS)

hfsutils reads and copies files from classic HFS volumes. Install it with [Homebrew](https://brew.sh/):

```bash
brew install hfsutils
```

Remove write permission from the image, so that hfsutils opens it read-only:

```bash
chmod a-w "$image"
```

Then mount it. hfsutils reports the volume as locked, because it's read-only.

```bash
hmount "$image"
```

hfsutils finds the HFS partition by itself and keeps the mounted volume as its current volume until you release it. Paths use colons instead of slashes, and a path that starts with a colon is relative to the current folder. The following examples use the folder and file names of the TKKG 1 disc.

To list the top folder, including invisible files:

```bash
hls -la
```

To list the game folder:

```bash
hls -l ':TKKG 1'
```

`hls -l` shows each file's type and creator codes. The type `APPL` marks programs, and `TEXT` marks text files. To change into the game folder:

```bash
hcd ':TKKG 1'
```

### Copy files

To copy a file with its resource fork, as a MacBinary file:

```bash
hcopy -m 'Lies mich' ~/Desktop/Lies-mich.bin
```

To turn a MacBinary file back into a file with its resource fork, open it with The Unarchiver, or install `unar` with Homebrew:

```bash
brew install unar
```

This command then puts the file `Lies mich` on your Desktop:

```bash
unar -o ~/Desktop ~/Desktop/Lies-mich.bin
```

To copy a text file, `hcopy -t` converts it to Unix line endings and the ISO 8859-1 (Latin-1) character set:

```bash
hcopy -t 'Lies mich' ~/Desktop/Lies-mich.txt
```

This command saves a UTF-8 copy of it:

```bash
iconv -f ISO-8859-1 -t UTF-8 ~/Desktop/Lies-mich.txt > ~/Desktop/Lies-mich-utf8.txt
```

`hcopy` can't copy folders, but it copies several files at once into an existing folder. To copy all files of the current folder, first create a folder `tkkg-mac` on your Desktop:

```bash
mkdir -p ~/Desktop/tkkg-mac
```

Then copy the files into it. `-r` copies only the data fork, without conversion, so resource forks are lost. Use `hcopy -m` for files that need theirs. `hcopy` replaces spaces in the file names with underscores.

```bash
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
