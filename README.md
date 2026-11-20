# TKKG on modern Macs

TKKG (Tim, Karl, Klößchen and Gaby) is a German youth detective series. Between 1997 and 2005, Tivola released 14 TKKG adventure games for Windows and classic Mac OS, plus the TKKG Identikit (Das Phantombild Programm). Two later games, TKKG 15 and 16, came out for Windows only.

The Mac versions need classic Mac OS. The early games need System 7.1 or later, and the later ones need at least Mac OS 8.1, 8.6 or 9.1, depending on the game. TKKG 11 to 14 also run on early Mac OS X, but only on PowerPC Macs. None of them run on current Macs.

This guide shows how to play the original game discs in [UTM](https://getutm.app/), which emulates a PowerPC Mac running Mac OS 9. UTM runs only on Apple devices, so the guide doesn't cover Windows or Linux.

The [`content`](content) folder holds the readme files, help files and printouts from the original discs.

## Contents

- [Requirements](#requirements)
- [Setup](#setup)
- [Playing](#playing)
- [Troubleshooting](#troubleshooting)
- [Original game documentation](#original-game-documentation)
- [Advanced topics](#advanced-topics)

## Requirements

- A Mac with Apple silicon or an Intel processor, running macOS 12 Monterey or later, the minimum for UTM 5.
- About 8 GB of free disk space: 7.5 GB for the disc images of all games, including both Identikit editions, and 0.5 GB for Mac OS 9.
- For TKKG 10 only, a free [Macintosh Repository](https://www.macintoshrepository.org/) account. Its archive is larger than 100 MB, the limit for guests.

## Setup

You do these four steps once. To start and switch games afterwards, see [Playing](#playing).

Keep the disc images and the Mac OS 9 virtual machine (VM) together in a folder named `TKKG` in your home folder. iCloud Drive doesn't sync this folder, so macOS won't move the large files off your Mac to save space.

Some steps also show a Terminal command as an alternative or as an optional check. To run one, open Terminal from Applications > Utilities, paste the command and press Return.

### 1. Install UTM

> [!IMPORTANT]
> Use the free download of UTM, not the paid Mac App Store version. The App Store version has the same features, but in November 2026 it was still at 5.0.8, which lacks the Mac OS 9 fixes from 5.0.9.

1. Download UTM 5.0.9 (build 132) or later from [getutm.app](https://getutm.app/) or the [UTM releases on GitHub](https://github.com/utmapp/UTM/releases/latest).
2. Open the DMG and drag UTM to your Applications folder. UTM > About UTM shows the version with the build number in brackets, for example 5.0.9 (132).

The earlier 5.0.9 builds 130 and 131 can crash a VM at start-up on macOS 14 and later.

If you use [Homebrew](https://brew.sh/), you can install UTM with this command instead:

```bash
brew install --cask utm
```

### 2. Download the games

Most games come from the Internet Archive as disc images that UTM uses directly. TKKG 10 and the German edition of the Identikit come from Macintosh Repository as `.sit` StuffIt archives. The Internet Archive has no complete copy of TKKG 10 and only the English edition of the Identikit.

| Game | German title | Download | Disc image | Languages |
| --- | --- | --- | --- | --- |
| TKKG 1 | Katjas Geheimnis | [Internet Archive](https://archive.org/details/tkkg-01) | `TKKG 01.iso` | DE, EN |
| TKKG 2 | Tödliche Schokolade | [Internet Archive](https://archive.org/details/tkkg-02) | `TKKG 02.iso` | DE, EN |
| TKKG 3 | Der Schatz der Maya | [Internet Archive](https://archive.org/details/tkkg-03) | `TKKG 03.iso` | DE, EN |
| TKKG 4 | Das Rätsel der Villa Drachenkralle | [Internet Archive](https://archive.org/details/tkkg-4_202605) | `TKKG 04.iso` | DE, EN |
| TKKG 5 | Verrat an TKKG | [Internet Archive](https://archive.org/details/tkkg-05) | `TKKG 05.iso` | DE, EN |
| TKKG 6 | Der Fälscherbande auf der Spur | [Internet Archive](https://archive.org/details/tkkg-06) | `TKKG 06.iso` | DE, EN |
| TKKG 7 | Wer stoppt den Feuerteufel? | [Internet Archive](https://archive.org/details/tkkg-7_202201) | `TKKG7.iso` | DE, EN |
| TKKG 8 | Das geheimnisvolle Testament | [Internet Archive](https://archive.org/details/tkkg-8_202201) | `TKKG8.iso` | DE, EN |
| TKKG 9 | Voodoozauber | [Internet Archive](https://archive.org/details/tkkg-9_202201) | `TKKG9.iso` | DE, EN |
| TKKG 10 | Panik im Internat | [Macintosh Repository](https://www.macintoshrepository.org/2997-tkkg-10-panik-im-internat) | `TKKG.iso` | DE |
| TKKG 11 | Film ab! | [Internet Archive](https://archive.org/details/tkkg-11) | `TKKG11.iso` | DE |
| TKKG 12 | Alarm in der Geisterbahn | [Internet Archive](https://archive.org/details/tkkg-12) | `TKKG12.iso` | DE |
| TKKG 13 | Zelle 13 | [Internet Archive](https://archive.org/details/tkkg-13) | `TKKG13.iso` | DE |
| TKKG 14 | Gefährliche Ferien | [Internet Archive](https://archive.org/details/tkkg-14) | `TKKG14.iso` | DE |
| Identikit | Das Phantombild Programm | [Internet Archive](https://archive.org/details/Identikit) (EN), [Macintosh Repository](https://www.macintoshrepository.org/4209-tkkg-identikit) (DE) | `Identikit.iso` (EN), `TKKG_Identikit_Ger.iso` (DE) | DE, EN |

DE stands for German and EN for English. TKKG 1 to 9 contain both language versions on one disc. The two Identikit editions are separate discs.

1. Create a folder named `TKKG` in your home folder. In the Finder, choose Go > Home, then File > New Folder.
2. For each game with an Internet Archive link in the table, open the link and click ISO IMAGE under Download Options. Move the downloaded disc image from your Downloads folder to the `TKKG` folder.

For TKKG 10 and the German Identikit, continue with these steps:

1. Install [The Unarchiver](https://theunarchiver.com/), which is free and also available on the [Mac App Store](https://apps.apple.com/app/the-unarchiver/id425424353). The Archive Utility built into macOS can't open StuffIt archives.
2. Open the Macintosh Repository link in the table and download the archive. For TKKG 10, sign in first, because its archive is larger than 100 MB, the limit for guests.
3. Double-click the archive. The first time, The Unarchiver asks where to extract archives. Choose Extract to Same Folder. The Mac App Store version of The Unarchiver then also asks for permission to use the folder. Click Extract.
4. Move the extracted disc image to the `TKKG` folder.

According to the rules of Macintosh Repository, downloads through a proxy, a download manager or a VPN that changes your IP address can fail.

> [!NOTE]
> macOS shows an error when you double-click a disc image, because it can't read the classic Mac file system of these hybrid Mac and Windows discs. Mac OS 9 in UTM reads them without problems, so don't convert them.

To download all Internet Archive images into the `TKKG` folder in Terminal instead, run this command. It downloads about 7 GB and creates the folder if needed:

```bash
curl -L --fail --create-dirs --output-dir ~/TKKG \
  -o "TKKG 01.iso" "https://archive.org/download/tkkg-01/TKKG%2001.iso" \
  -o "TKKG 02.iso" "https://archive.org/download/tkkg-02/TKKG%2002.iso" \
  -o "TKKG 03.iso" "https://archive.org/download/tkkg-03/TKKG%2003.iso" \
  -o "TKKG 04.iso" "https://archive.org/download/tkkg-4_202605/TKKG%2004.iso" \
  -o "TKKG 05.iso" "https://archive.org/download/tkkg-05/TKKG%2005.iso" \
  -o "TKKG 06.iso" "https://archive.org/download/tkkg-06/TKKG%2006.iso" \
  -o "TKKG7.iso" "https://archive.org/download/tkkg-7_202201/TKKG7.iso" \
  -o "TKKG8.iso" "https://archive.org/download/tkkg-8_202201/TKKG8.iso" \
  -o "TKKG9.iso" "https://archive.org/download/tkkg-9_202201/TKKG9.iso" \
  -o "TKKG11.iso" "https://archive.org/download/tkkg-11/TKKG11.iso" \
  -o "TKKG12.iso" "https://archive.org/download/tkkg-12/TKKG12.iso" \
  -o "TKKG13.iso" "https://archive.org/download/tkkg-13/TKKG13.iso" \
  -o "TKKG14.iso" "https://archive.org/download/tkkg-14/TKKG14.iso" \
  -o "Identikit.iso" "https://archive.org/download/Identikit/Identikit.iso"
```

To extract the Macintosh Repository archives in Terminal instead of The Unarchiver, install the command-line tool `unar`. Homebrew has it ready-made for Apple silicon Macs with macOS 15 or later. On other Macs, Homebrew needs Xcode to build it.

```bash
brew install unar
```

This command extracts the TKKG archives in your Downloads folder into the `TKKG` folder:

```bash
for f in ~/Downloads/[Tt][Kk][Kk][Gg]*.sit; do unar -o ~/TKKG "$f"; done
```

Keep the images in the `TKKG` folder. UTM remembers each image by its location, so after a move you have to select it in UTM again.

You can check that every image is complete. This command prints the SHA-1 of every disc image in the `TKKG` folder:

```bash
shasum ~/TKKG/*.iso
```

Compare the values with [Checksums](docs/checksums.md). Without Terminal, select each image in the Finder and compare its size in bytes in File > Get Info instead. If an image doesn't match, download it again. For TKKG 10 and the German Identikit, try extracting the archive again first.

Once all images are in the `TKKG` folder, you can delete the `.sit` archives.

### 3. Add the Mac OS 9 virtual machine

This guide uses the preinstalled Mac OS 9.2.1 VM that the UTM project published for its former gallery. Every game ran in it with the settings below. Only the English Identikit is untested. UTM no longer updates this VM, but it still works.

Download [`mac-os-9.2.1-utm.zip`](https://github.com/utmapp/vm-downloads/releases/download/mac-os-9.2.1/mac-os-9.2.1-utm.zip) (141 MB) from the UTM project's [vm-downloads releases](https://github.com/utmapp/vm-downloads/releases/tag/mac-os-9.2.1).

To check the download before you unpack it, you can run this command. It should print `13d2bb7db75bc4e8e94e181dd5ded1484a22dd07d5fe91a6464cde338400f508`. If Safari has already unpacked the zip, it is no longer in your Downloads folder, so skip this check.

```bash
shasum -a 256 ~/Downloads/mac-os-9.2.1-utm.zip
```

Then add the VM to UTM:

1. If Safari hasn't already unpacked the download, double-click the zip file. You then have `Mac OS 9.2.1.utm` in your Downloads folder.
2. Move `Mac OS 9.2.1.utm` to the `TKKG` folder. UTM runs a VM from the place you open it, without copying it.
3. Double-click `Mac OS 9.2.1.utm`. UTM opens and lists the VM in its sidebar.
4. Select the VM and click Edit, the slider icon at the right end of the toolbar. You can also right-click the VM and choose Edit.
5. Under System, set CPU to `g3`.
6. Optionally, right-click Network in the sidebar and choose Remove. The games don't use the network, and Mac OS 9 no longer gets security updates.
7. Click Save.

On the default G4 processor, TKKG 12 crashed right after its intro in testing. Leave the memory at 512 MB, because more memory doesn't make the emulation faster.

### 4. Start Mac OS 9 and set the display

1. Select the VM in UTM and click the Play button. Within a minute or two, the Mac OS 9 desktop appears, with the hard disk "untitled" in the top right corner.
2. On the first start, the Mac OS Setup Assistant opens, and possibly the AirPort Setup Assistant. The games need neither, so quit them with Command-Q.
3. Open the Apple menu > Control Panels > Monitors. Use the Apple logo at the left end of the menu bar inside the VM window, not the one in the macOS menu bar.
4. Choose Thousands under Color Depth and 800 × 600 under Resolution, then close the window with the box at its top left.
5. Optionally, set up a printer that saves to files. Some games can print, and Mac OS 9 froze when TKKG 6 printed while no printer was set up, so do this before you play TKKG 6. Open the "untitled" hard disk, then Applications (Mac OS 9) > Utilities > Desktop Printer Utility. Choose Translator (PostScript) and create the desktop printer. Each print then asks for a file name and saves a PostScript file in Mac OS 9.

These display settings suit every game except TKKG 6, which needs 256 colours. [Start a game](#start-a-game) covers that. The mouse pointer moves freely between the VM window and the rest of your Mac.

To shut down the VM, choose Special > Shut Down in Mac OS 9. The Special menu belongs to the Finder, so if you don't see it, click the desktop first.

## Playing

### Start a game

1. If another game's disc is on the Mac OS 9 desktop, eject it. Drag its icon to the Trash in the bottom right corner of the desktop, or select it and press Command-E.
2. In UTM's main window, select the VM, click CD/DVD in its details, choose Browse… and select the game's disc image from the `TKKG` folder. This works while the VM is running or stopped. In a running VM's window, you can also click the Drives toolbar button, choose the CD/DVD drive, then choose Change.
3. In Mac OS 9, the disc appears on the desktop, for example as "TKKG 1". If its window doesn't open by itself, double-click the disc icon.
4. The first time you play TKKG 1 to 10 or the Identikit, drag the game folder named in the table below from the disc window onto the "untitled" hard disk icon. Ignore the empty folder whose name is an arrow, "<- auf die Festplatte kopieren" or "<- Copy on the hard drive...". It only points at the game folder. If the Finder asks whether to replace an existing item, click Cancel to keep the copy you already have. TKKG 11 to 14 run from the disc and need no copying.
5. For TKKG 6 only, open the Apple menu > Control Panels > Monitors and choose 256 under Color Depth, because TKKG 6 doesn't switch by itself.
6. Double-click the start icon from the table. For TKKG 1 to 10 and the Identikit, it's in the copied folder on the hard disk. For TKKG 11 to 14, it's in the disc window.

| Game | Folder to copy once | Start icon | Display |
| --- | --- | --- | --- |
| TKKG 1 to 4 | TKKG 1, TKKG 2, TKKG 3, TKKG 4 | TKKG start | 256 colours, set by the game |
| TKKG 5 | TKKG 5 | TKKG Start | 256 colours, set by the game |
| TKKG 6 | TKKG 6 | TKKG-Start | 256 colours, set by you (step 5) |
| TKKG 7 to 9 | TKKG 7, TKKG 8, TKKG 9 | TKKG-Start | Thousands |
| TKKG 10 | TKKG10 | TKKG10 | Thousands, 800 × 600 or more |
| TKKG 11 to 14 | None (they start from the disc) | TKKG11, TKKG12, TKKG13, TKKG14 | Thousands, 800 × 600 or more |
| Identikit | Identikit (EN), Phantombild (DE) | Identikit Start (EN), Phantombild Start (DE) | Thousands |

The table shows the names on the discs. The original readme files sometimes spell them differently. TKKG 7 to 14 and the German Identikit ran at Thousands in testing. Thousands is the Mac OS name for 32,768 colours. Most readme and help files of these games ask for it, including the English Identikit's readme.

Leave the disc inserted while you play, because the games load pictures and sound from it. If a game opens with a TKKG membership card, click Neues Mitglied (new member) to start a new game. Next time, click Mitglied (member) and choose your name to continue where you left off.

### Switch games

1. Quit the game from inside the game, using its own exit button or menu, and wait until the Mac OS 9 desktop is back.
2. If you played TKKG 6, set Color Depth back to Thousands in the Monitors control panel.
3. Follow [Start a game](#start-a-game) from step 1. Skip the copy step for a game you have copied before.

### Quit and play again later

> [!WARNING]
> Always quit the game from inside it before you shut down Mac OS 9 or stop the VM. If you stop the VM while a game is running, you can lose progress. In testing, TKKG 6 lost everything played since its last quit from inside the game.

To finish, choose Special > Shut Down in Mac OS 9, then quit UTM.

Next time, select the VM in UTM and click Play. UTM keeps the last disc inserted, so it appears on the desktop again. Start TKKG 1 to 10 and the Identikit from their folder on the hard disk, and TKKG 11 to 14 from the start icon on the disc.

The games save your progress inside the VM. To back it up, shut down the VM and copy `Mac OS 9.2.1.utm` in the Finder.

## Troubleshooting

### The VM doesn't start, or Mac OS 9 crashes at start-up with a sound error

The emulated sound device, Screamer, has known problems. Update to UTM 5.0.9 or later, which fixes several of them. If the problem stays, remove the sound device. If the VM is still running, click Stop in UTM. Then select the VM, click Edit, right-click Sound in the sidebar, choose Remove and click Save. The games then play without sound.

### Mac OS 9 hangs at "Starting Up…" or after Restart

UTM 5.0.8 and earlier have two bugs that cause this, [UTM issue #8033](https://github.com/utmapp/UTM/issues/8033) and [UTM issue #7999](https://github.com/utmapp/UTM/issues/7999). Update to UTM 5.0.9 or later. With an older version, stop the VM in UTM, start it again and use Shut Down instead of Restart.

If the VM window stays black apart from the menu bar clock after start-up, click inside the window.

### The disc doesn't appear in Mac OS 9

- Check that the CD/DVD row in UTM shows the image name and not "(empty)".
- Make sure you selected the `.iso` disc image and not a `.sit` archive.
- If the desktop still shows the previous game's disc, eject it in Mac OS 9 and select the new image again.
- If a download or extraction stopped early, the image is incomplete. Compare its size and SHA-1 with [Checksums](docs/checksums.md). If either differs, download it again.

### UTM reports "Operation not permitted" or "Failed to access drive image path"

UTM can only open files that you selected in UTM yourself. After you move or rename a disc image, UTM loses access to it. Click CD/DVD, choose Browse… and select the image again.

### UTM reports "IDE unit 0 is in use"

This happens after you add a drive to the VM. The UTM project built the preinstalled VM with an older UTM version, which put each IDE drive on its own bus. A newly added drive can then claim a slot that is already taken. You don't need an extra drive, because the VM already has a CD/DVD drive.

> [!CAUTION]
> UTM permanently deletes the disk image of a drive you delete. If you delete the VM's hard disk instead of the drive you added, you lose Mac OS 9 and all game progress.

Open the VM settings. The drive you added is the last IDE Drive under Drives. Right-click it, choose Delete, confirm with Delete and click Save.

If you do need another drive, click Update Interface on every IDE drive that shows this button, then click Save. This puts all drives on the current layout with two drives per bus.

### TKKG 12 quits after the intro with "an error of type 3"

The VM uses the default G4 processor. Shut down Mac OS 9 and set System > CPU to `g3` in the VM settings, as described in [Add the Mac OS 9 virtual machine](#3-add-the-mac-os-9-virtual-machine).

### Colours look wrong or a game complains about the display

Set the Monitors control panel to the values in the table under [Start a game](#start-a-game). TKKG 6 needs 256 colours, TKKG 7 to 14 and the Identikit need Thousands, and TKKG 10 to 14 need at least 800 × 600.

### TKKG 6 shows noise bands in the hotel reception

You are using a damaged copy of the disc, such as the one on Macintosh Repository. Download TKKG 6 from the Internet Archive as linked in [Download the games](#2-download-the-games), and compare its SHA-1 with [Checksums](docs/checksums.md).

### Mac OS 9 can freeze when a game prints

Mac OS 9 froze when TKKG 6 printed while no printer was set up. If this happens, click Stop in UTM and confirm that you want to force stop the VM. You can lose progress made since you last quit the game from inside it. At the next start, Disk First Aid checks the hard disk. Let it finish.

To prevent the freeze, set up the file printer described in step 5 of [Start Mac OS 9 and set the display](#4-start-mac-os-9-and-set-the-display). The printouts of TKKG 1, 2 and 4 are also in the [`content`](content) folder as PDFs.

### Graphics errors in the final game of TKKG 14

TKKG 14's readme says that pressing Command-Shift-0 or Command-Shift-minus during the final game (Finalspiel) fixes these errors.

### The game runs slowly or the sound stutters

UTM emulates the PowerPC processor in software on a single core, so speed depends on your Mac. Close demanding apps and keep the VM window in front, because macOS can slow down apps in the background. UTM 5.0.9 also fixes crackling sound while the Mac is busy. Raising the VM's memory doesn't help.

## Original game documentation

The [`content`](content) folder holds documentation copied from the original discs. The files are in German unless noted. In printout names, a `D` marks the German version and an `E` the English one, for example `SZ28D1.pdf` and `SZ28E1.pdf`.

| Folder | Contents |
| --- | --- |
| [`TKKG1`](content/TKKG1) | Help file with the solution. Windows and Mac readmes, both with hidden hints. Printouts: decoder disc with assembly instructions, Oma Peper's chocolate cake recipe (German and English). |
| [`TKKG2`](content/TKKG2) | Help file with the solution. Windows and Mac readmes, both with hidden hints. Printout: Sauerlich's special biscuits recipe (German and English). |
| [`TKKG3`](content/TKKG3) | Help file with the solution. Windows and Mac readmes, both with hidden hints. |
| [`TKKG4`](content/TKKG4) | Help file with the solution. Web pages from the in-game city archive computer (`HTMLD` German, `HTMLE` English). Printouts: piano basics, "Für Elise" sheet music, Oma Peper's nut cake recipe (German and English). |
| [`TKKG5`](content/TKKG5) | Help file with the solution. |
| [`TKKG6`](content/TKKG6) | Help file with the solution. The TKKG 6 readme is in `TKKG7`. |
| [`TKKG7`](content/TKKG7) | Help file with the solution. The readme belongs to TKKG 6: the original TKKG 7 disc contains the same mix-up and has no readme of its own. |
| [`TKKG8`](content/TKKG8) | Help file with the solution, readme. |
| [`TKKG9`](content/TKKG9) | Help file with the solution. |
| [`TKKG10`](content/TKKG10), [`TKKG11`](content/TKKG11), [`TKKG12`](content/TKKG12) | Readme. |
| [`TKKG13`](content/TKKG13), [`TKKG14`](content/TKKG14) | Help file with solution hints, readme. |
| [`TKKG_Identikit`](content/TKKG_Identikit) | Readme of the German edition (`LIESMICH.TXT`) and of the English edition (`README.TXT`, in English). |

The folders contain these files:

- `LIESMICH.TXT` is the readme, stored here as UTF-8 text. Most readmes list system requirements, installation steps and the historical Tivola support contacts. The readmes of TKKG 1 to 3 hide hints far below the main text. They come from earlier releases of these games. On the Internet Archive images, TKKG 1 has a shorter readme without the hints, and TKKG 2 and 3 have none. [Checksums](docs/checksums.md) lists the sources.
- `README.TXT` in `TKKG_Identikit` is the readme of the English Identikit edition, also stored as UTF-8 text.
- `LIESMICH_MAC.TXT` is the Mac readme from the game folder on the discs of TKKG 1 to 3, also stored as UTF-8 text. It lists the Mac system requirements and installation steps. The Mac readmes of TKKG 10 to 14 and both Identikit editions have the same content as their Windows readme. TKKG 11 to 14 store it as a PDF. The discs of TKKG 4 to 9 have no Mac readme.
- `HILFE.PDF` is the game's help file. For TKKG 1 to 9, it also covers system requirements and troubleshooting before the full solution. The solution gives away the whole case, so read it only if you are stuck.
- `PRINT/PCT` holds the print pages as stored on the disc, in the Macintosh PICT format. `PRINT/PDF` holds PDF conversions of them. The PDF pages are larger than A4, so choose a scale-to-fit option when you print.
- `HTMLD` and `HTMLE` in `TKKG4` hold the web pages. Open their `INDEX.HTM` in a web browser. The pages refer to their files in lowercase, so they only work on a case-insensitive file system, which is the macOS default.

## Advanced topics

- [Checksums](docs/checksums.md): the size and SHA-1 of every disc image, the two Macintosh Repository archives, incomplete copies, and the sources of the TKKG 1 to 3 readmes.
- [Accessing game data](docs/game-data.md): how to read files from the disc images on macOS without running the games, for example to extract pictures or sound.

### Install Mac OS 9 yourself

Instead of the preinstalled VM, UTM can create a new VM from a Mac OS 9 installer disc image that you provide. Click + in UTM, choose Emulate > Classic Mac OS and select Power Macintosh G4 (1999, PPC). UTM's [Classic Mac OS guide](https://docs.getutm.app/guides/classic-macos/) describes the steps. Fresh installs of Mac OS 9.2.1 and 9.2.2 can freeze at "About 4 minutes" remaining. This bug, [UTM issue #6936](https://github.com/utmapp/UTM/issues/6936), is still open, so this guide uses the preinstalled VM. If you build your own VM, set the CPU to `g3` as well.
