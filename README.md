# TKKG on modern Macs

TKKG (Tim, Karl, Klößchen and Gaby) is a German youth detective series. Between 1997 and 2005, Tivola released 14 TKKG adventure games for Windows and classic Mac OS, plus the TKKG Identikit (Das Phantombild Programm). Two later games, TKKG 15 and 16, came out for Windows only.

The Mac versions need classic Mac OS: the early games System 7.1 or later, the later ones at least Mac OS 8.1, 8.6 or 9.1, depending on the game. TKKG 11 to 14 also run on early Mac OS X, but only on PowerPC Macs. None of them run on current Macs.

This guide shows how to play the original game discs in [UTM](https://getutm.app/), which emulates a PowerPC Mac running Mac OS 9. UTM runs only on Apple devices, so the guide doesn't cover Windows or Linux.

The [`content`](content) folder holds the readme files, help files and printouts from the original discs.

## Contents

- [Requirements](#requirements)
- [Setup](#setup)
  1. [Install UTM and The Unarchiver](#1-install-utm-and-the-unarchiver)
  2. [Download the games](#2-download-the-games)
  3. [Extract the disc images](#3-extract-the-disc-images)
  4. [Add the Mac OS 9 virtual machine](#4-add-the-mac-os-9-virtual-machine)
  5. [Start Mac OS 9 and set the display](#5-start-mac-os-9-and-set-the-display)
- [Playing](#playing)
- [Troubleshooting](#troubleshooting)
- [Original game documentation](#original-game-documentation)
- [Advanced topics](#advanced-topics)

## Requirements

- A Mac with Apple silicon or an Intel processor, running macOS 12 Monterey or later (the minimum for UTM 5).
- About 11 GB of free disk space for all 15 games: 7.1 GB for the disc images, 3.2 GB for the downloaded archives (you can delete them once the images are extracted) and 0.5 GB for Mac OS 9.
- A free [Macintosh Repository](https://www.macintoshrepository.org/) account. Guests can only download files under 100 MB, and every game except the Identikit is larger.

## Setup

You do these five steps once. To start and switch games afterwards, see [Playing](#playing).

Keep the disc images and the Mac OS 9 virtual machine (VM) together in a folder named `TKKG` in your home folder. iCloud Drive doesn't sync this folder, so macOS won't move the large files off your Mac to save space.

Some steps also show a Terminal command as an alternative or as an optional check. To run one, open Terminal (Applications > Utilities), paste the command and press Return.

### 1. Install UTM and The Unarchiver

Use the free download of UTM, not the paid Mac App Store version. The App Store version has the same features, but its updates can arrive later. In November 2026 it was still at 5.0.8, which lacks the Mac OS 9 fixes from 5.0.9. In 5.0.8, Restart can end on a black screen, start-up sometimes hangs at "Starting Up…", and sound can fail or crackle.

1. Download UTM 5.0.9 (build 132) or later from [getutm.app](https://getutm.app/) or the [UTM releases on GitHub](https://github.com/utmapp/UTM/releases/latest).
2. Open the DMG and drag UTM to your Applications folder. UTM > About UTM shows the version with the build number in brackets, for example 5.0.9 (132).
3. Install [The Unarchiver](https://theunarchiver.com/), which is free and also available on the [Mac App Store](https://apps.apple.com/app/the-unarchiver/id425424353). All games except TKKG 6 come as StuffIt (`.sit`) archives, which the Archive Utility built into macOS can't open.

The earlier 5.0.9 builds 130 and 131 can crash a VM at start-up on macOS 14 and later.

If you use [Homebrew](https://brew.sh/), you can install both apps with one command instead:

```bash
brew install --cask utm the-unarchiver
```

### 2. Download the games

> [!WARNING]
> Get TKKG 6 from the Internet Archive, as linked in the table. The [TKKG 6 download from Macintosh Repository](https://www.macintoshrepository.org/3430-tkkg-6-the-forged-fifties) is damaged: in the game, the hotel reception shows noise bands, and other scenes can fail too. [Checksums](docs/checksums.md) has the details.

1. Sign in to Macintosh Repository.
2. For each game you want, open its download page in the table and download the archive. Your browser saves it in your Downloads folder.
3. For TKKG 6, download the disc image `TKKG 06.iso` from the Internet Archive page instead.

Members can download up to 20 files a day. According to the site's rules, downloads through a proxy, a download manager or a VPN that changes your IP address can fail.

| Game | German title | Download page | Disc image | Languages |
| --- | --- | --- | --- | --- |
| TKKG 1 | Katjas Geheimnis | [TKKG 1: Jennifer Is Missing](https://www.macintoshrepository.org/5387-tkkg-1-jennifer-is-missing) | `TKKG 1.cdr` | German, English |
| TKKG 2 | Tödliche Schokolade | [TKKG 2: Deadly Chocolate](https://www.macintoshrepository.org/4794-tkkg-2-deadly-chocolate) | `TKKG 2.cdr` | German, English |
| TKKG 3 | Der Schatz der Maya | [TKKG 3: The Mystery of the Mayan Treasure](https://www.macintoshrepository.org/3393-tkkg-3-the-mystery-of-the-mayan-treasure) | `TKKG3.iso` | German, English |
| TKKG 4 | Das Rätsel der Villa Drachenkralle | [TKKG 4: The Secret of Dragon Claw Manor](https://www.macintoshrepository.org/6174-tkkg-4-the-secret-of-dragon-claw-manor) | `TKKG4.cdr` | German, English |
| TKKG 5 | Verrat an TKKG | [TKKG 5: TKKG Betrayed](https://www.macintoshrepository.org/4717-tkkg-5-tkkg-betrayed) | `TKKG5.iso` | German, English |
| TKKG 6 | Der Fälscherbande auf der Spur | [TKKG 06 on the Internet Archive](https://archive.org/details/tkkg-06) | `TKKG 06.iso` | German, English |
| TKKG 7 | Wer stoppt den Feuerteufel? | [TKKG 7: Fire!](https://www.macintoshrepository.org/4043-tkkg-7-fire-) | `TKKG7.iso` | German, English |
| TKKG 8 | Das geheimnisvolle Testament | [TKKG 8: The Captain's Legacy](https://www.macintoshrepository.org/6187-tkkg-8-the-captain-s-legacy) | `TKKG8.iso` | German, English |
| TKKG 9 | Voodoozauber | [TKKG 9: Voodoo Magic](https://www.macintoshrepository.org/5744-tkkg-9-voodoo-magic) | `TKKG9.iso` | German, English |
| TKKG 10 | Panik im Internat | [TKKG 10: Panik im Internat](https://www.macintoshrepository.org/2997-tkkg-10-panik-im-internat) | `TKKG.iso` | German |
| TKKG 11 | Film ab! | [TKKG 11: Film Ab!](https://www.macintoshrepository.org/3133-tkkg-11-film-ab-) | `TKKG11.iso` | German |
| TKKG 12 | Alarm in der Geisterbahn | [TKKG 12: Alarm in der Geisterbahn](https://www.macintoshrepository.org/3884-tkkg-12-alarm-in-der-geisterbahn) | `TKKG12.iso` | German |
| TKKG 13 | Zelle 13 | [TKKG 13: Zelle 13](https://www.macintoshrepository.org/5302-tkkg-13-zelle-13) | `TKKG13.iso` | German |
| TKKG 14 | Gefährliche Ferien | [TKKG 14: Gefährliche Ferien](https://www.macintoshrepository.org/3506-tkkg-14-gefahrliche-ferien) | `TKKG14.iso` | German |
| Identikit | Das Phantombild Programm | [TKKG: Identikit](https://www.macintoshrepository.org/4209-tkkg-identikit) | `TKKG_Identikit_Ger.iso` | German |

The Macintosh Repository links use the site's page titles. TKKG 1 to 9 contain both the German and the English version on one disc.

### 3. Extract the disc images

1. Create a folder named `TKKG` in your home folder: in the Finder, choose Go > Home, then File > New Folder.
2. Double-click each `.sit` archive in your Downloads folder, for example `tkkg1.cdr_.sit`. The first time, The Unarchiver asks where to extract archives: choose Extract to Same Folder. The Mac App Store version of The Unarchiver then also asks for permission to use the folder: click Extract.
3. Move the extracted disc images, listed in the table above, to the `TKKG` folder. TKKG 10's image is named `TKKG.iso`. Move `TKKG 06.iso` there as well, because it needs no extracting.

To do steps 1 to 3 in Terminal instead, create the folder:

```bash
mkdir -p ~/TKKG
```

Install the command-line tool `unar`. Homebrew has it ready-made for Apple silicon Macs with macOS 15 or later. On other Macs, Homebrew needs Xcode to build it.

```bash
brew install unar
```

Extract every TKKG archive in your Downloads folder into the `TKKG` folder:

```bash
for f in ~/Downloads/[Tt][Kk][Kk][Gg]*.sit; do unar -o ~/TKKG "$f"; done
```

Move the TKKG 6 disc image there:

```bash
mv "$HOME/Downloads/TKKG 06.iso" ~/TKKG/
```

macOS shows an error when you double-click an image, because it can't read the classic Mac file system of these hybrid Mac and Windows discs. Mac OS 9 in UTM reads them without problems, so don't convert them. Keep the images in the `TKKG` folder: UTM remembers each image by its location, so after a move you have to select it in UTM again.

Optional, for both ways: before you delete the archives, check that every image is complete. This command prints the SHA-1 of all images in the `TKKG` folder. Compare the values with [Checksums](docs/checksums.md). Without Terminal, compare each image's size in File > Get Info instead. If an image doesn't match, extract its archive again, or download it again:

```bash
find ~/TKKG -maxdepth 1 -type f \( -name '*.iso' -o -name '*.cdr' \) -exec shasum {} +
```

Once all images are in the `TKKG` folder, you can delete the `.sit` archives.

### 4. Add the Mac OS 9 virtual machine

This guide uses the preinstalled Mac OS 9.2.1 VM that the UTM project published for its former gallery. All 15 discs ran in it with the settings below. UTM no longer updates this VM, but it still works.

Download [`mac-os-9.2.1-utm.zip`](https://github.com/utmapp/vm-downloads/releases/download/mac-os-9.2.1/mac-os-9.2.1-utm.zip) (141 MB) from the UTM project's [vm-downloads releases](https://github.com/utmapp/vm-downloads/releases/tag/mac-os-9.2.1).

Optional: to check the download before you unpack it, run this command. It should print `13d2bb7db75bc4e8e94e181dd5ded1484a22dd07d5fe91a6464cde338400f508`. If Safari has already unpacked the zip, it is no longer in your Downloads folder, so skip this check.

```bash
shasum -a 256 ~/Downloads/mac-os-9.2.1-utm.zip
```

Then add the VM to UTM:

1. If Safari hasn't already unpacked the download, double-click the zip file. You then have `Mac OS 9.2.1.utm` in your Downloads folder.
2. Move `Mac OS 9.2.1.utm` to the `TKKG` folder. UTM runs a VM from the place you open it, without copying it.
3. Double-click `Mac OS 9.2.1.utm`. UTM opens and lists the VM in its sidebar.
4. Select the VM and click Edit, the slider icon at the right end of the toolbar. You can also right-click the VM and choose Edit.
5. Under System, set CPU to `g3`.
6. Optional: right-click Network in the sidebar and choose Remove. The games don't use the network, and Mac OS 9 no longer gets security updates.
7. Click Save.

On the default G4 processor, TKKG 12 crashed right after its intro in testing. Leave the memory at 512 MB, because more memory doesn't make the emulation faster.

### 5. Start Mac OS 9 and set the display

1. Select the VM in UTM and click the Play button. Within a minute or two, the Mac OS 9 desktop appears, with the hard disk "untitled" in the top right corner.
2. On the first start, the Mac OS Setup Assistant opens, and possibly the AirPort Setup Assistant. The games need neither, so quit them with Command-Q.
3. Open the Apple menu > Control Panels > Monitors. Use the Apple logo at the left end of the menu bar inside the VM window, not the one in the macOS menu bar.
4. Choose Thousands under Color Depth and 800 × 600 under Resolution, then close the window with the box at its top left.
5. Optional, recommended before you play TKKG 6: set up a printer that saves to files. Some games can print, and Mac OS 9 froze when TKKG 6 printed while no printer was set up. Open the "untitled" hard disk, then Applications (Mac OS 9) > Utilities > Desktop Printer Utility. Choose Translator (PostScript) and create the desktop printer. Each print then asks for a file name and saves a PostScript file in Mac OS 9.

These display settings suit every game except TKKG 6, which needs 256 colours: [Start a game](#start-a-game) covers it. The mouse pointer moves freely between the VM window and the rest of your Mac.

To shut down the VM, choose Special > Shut Down in Mac OS 9. The Special menu belongs to the Finder: if you don't see it, click the desktop first.

## Playing

### Start a game

1. If another game's disc is on the Mac OS 9 desktop, eject it: drag its icon to the Trash in the bottom right corner of the desktop, or select it and press Command-E.
2. In UTM's main window, select the VM, click CD/DVD in its details, choose Browse… and select the game's disc image from the `TKKG` folder. This works while the VM is running or stopped. In a running VM's window, the Drives toolbar button offers the same: choose the CD/DVD drive, then Change.
3. In Mac OS 9, the disc appears on the desktop, for example as "TKKG 1". If its window doesn't open by itself, double-click the disc icon.
4. The first time you play TKKG 1 to 10 or the Identikit, drag the game folder named in the table below from the disc window onto the "untitled" hard disk icon. Ignore the empty folder "<- auf die Festplatte kopieren" ("copy to the hard disk"), whose name is an arrow that points at the game folder. If the Finder asks whether to replace an existing item, click Cancel to keep the copy you already have. TKKG 11 to 14 run from the disc and need no copying.
5. For TKKG 6 only: open the Apple menu > Control Panels > Monitors and choose 256 under Color Depth. TKKG 6 doesn't switch by itself.
6. Double-click the start icon from the table: in the copied folder on the hard disk for TKKG 1 to 10 and the Identikit, or in the disc window for TKKG 11 to 14.

| Game | Folder to copy once | Start icon | Display |
| --- | --- | --- | --- |
| TKKG 1 to 4 | TKKG 1, TKKG 2, TKKG 3, TKKG 4 | TKKG start | 256 colours, set by the game |
| TKKG 5 | TKKG 5 | TKKG Start | 256 colours, set by the game |
| TKKG 6 | TKKG 6 | TKKG-Start | 256 colours, set by you (step 5) |
| TKKG 7 to 9 | TKKG 7, TKKG 8, TKKG 9 | TKKG-Start | Thousands |
| TKKG 10 | TKKG10 | TKKG10 | Thousands, 800 × 600 or more |
| TKKG 11 to 14 | None (they start from the disc) | TKKG11, TKKG12, TKKG13, TKKG14 | Thousands, 800 × 600 or more |
| Identikit | Phantombild | Phantombild Start | Thousands |

The table shows the names on the discs. The original readme files sometimes spell them differently. TKKG 7 to 14 and the Identikit ran at Thousands in testing. Thousands is the Mac OS name for 32,768 colours, which most of their readme and help files ask for.

Leave the disc inserted while you play, because the games load pictures and sound from it. If a game opens with a TKKG membership card, click Neues Mitglied (new member) to start a new game. Next time, click Mitglied (member) and choose your name to continue where you left off.

### Switch games

1. Quit the game from inside the game, using its own exit button or menu, and wait until the Mac OS 9 desktop is back.
2. If you played TKKG 6, set Color Depth back to Thousands in the Monitors control panel.
3. Follow [Start a game](#start-a-game) from step 1. Skip the copy step for a game you have copied before.

### Quit and play again later

Always quit the game from inside it before you shut down Mac OS 9 or stop the VM. If you stop the VM while a game is running, you can lose progress: TKKG 6, for example, lost all progress made since it was last quit from inside the game.

To finish, choose Special > Shut Down in Mac OS 9, then quit UTM.

Next time, select the VM in UTM and click Play. UTM keeps the last disc inserted, so it appears on the desktop again. Start TKKG 1 to 10 and the Identikit from their folder on the hard disk, and TKKG 11 to 14 from the start icon on the disc.

The games save your progress inside the VM. To back it up, shut down the VM and copy `Mac OS 9.2.1.utm` in the Finder.

## Troubleshooting

### The VM doesn't start, or Mac OS 9 crashes at start-up with a sound error

The emulated sound device, Screamer, has known problems. Update to UTM 5.0.9 or later, which fixes several of them. If the problem stays, remove the sound device: if the VM is still running, click Stop in UTM, then select the VM, click Edit, right-click Sound in the sidebar, choose Remove and click Save. The games then play without sound.

### Mac OS 9 hangs at "Starting Up…" or after Restart

UTM 5.0.8 and earlier have two bugs that cause this ([UTM issue #8033](https://github.com/utmapp/UTM/issues/8033) and [UTM issue #7999](https://github.com/utmapp/UTM/issues/7999)). Update to UTM 5.0.9 or later. With an older version, stop the VM in UTM, start it again and use Shut Down instead of Restart.

If the VM window stays black apart from the menu bar clock after start-up, click inside the window.

### The disc doesn't appear in Mac OS 9

- Check that the CD/DVD row in UTM shows the image name and not "(empty)".
- Make sure you selected the extracted `.cdr` or `.iso` image and not the `.sit` archive.
- If the desktop still shows the previous game's disc, eject it in Mac OS 9 and select the new image again.
- If the extraction stopped early, the image is incomplete. Compare its size and SHA-1 with [Checksums](docs/checksums.md). If either differs, extract it again, or download it again.

### UTM reports "Operation not permitted" or "Failed to access drive image path"

UTM can only open files that you selected in UTM yourself. After you move or rename a disc image, UTM loses access to it. Click CD/DVD, choose Browse… and select the image again.

### UTM reports "IDE unit 0 is in use"

This happens after you add a drive to the VM. The UTM project built the preinstalled VM with an older UTM version that put each IDE drive on its own bus, so a newly added drive can claim a slot that is already taken. You don't need an extra drive, because the VM already has a CD/DVD drive. Open the VM settings, right-click the drive you added (the last IDE Drive under Drives), choose Delete, confirm with Delete and click Save.

If you do need another drive, click Update Interface on every IDE drive that shows this button, then click Save. This puts all drives on the current layout with two drives per bus.

### TKKG 12 quits after the intro with "an error of type 3"

The VM uses the default G4 processor. Shut down Mac OS 9 and set System > CPU to `g3` in the VM settings, as described in [Add the Mac OS 9 virtual machine](#4-add-the-mac-os-9-virtual-machine).

### Colours look wrong or a game complains about the display

Set the Monitors control panel to the values in the table under [Start a game](#start-a-game): 256 colours for TKKG 6, Thousands for TKKG 7 to 14 and the Identikit, and at least 800 × 600 for TKKG 10 to 14.

### TKKG 6 shows noise bands in the hotel reception

You are using the damaged image from Macintosh Repository. Replace it with the intact copy from the Internet Archive linked in [Download the games](#2-download-the-games).

### Mac OS 9 can freeze when a game prints

Mac OS 9 froze when TKKG 6 printed while no printer was set up. If this happens, click Stop in UTM and confirm that you want to force stop the VM. You can lose progress made since you last quit the game from inside it. At the next start, Disk First Aid checks the hard disk. Let it finish.

To prevent the freeze, set up the file printer described in step 5 of [Start Mac OS 9 and set the display](#5-start-mac-os-9-and-set-the-display). The printouts of TKKG 1, 2 and 4 are also in the [`content`](content) folder as PDFs.

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
| [`TKKG_Identikit`](content/TKKG_Identikit) | Readme. |

The folders contain these files:

- `LIESMICH.TXT` is the readme, stored here as UTF-8 text. Most readmes list system requirements, installation steps and the historical Tivola support contacts. The readmes of TKKG 1 to 3 hide hints far below the main text.
- `LIESMICH_MAC.TXT` is the Mac readme from the game folder on the discs of TKKG 1 to 3, also stored as UTF-8 text. It lists the Mac system requirements and installation steps. The Mac readmes of TKKG 10 to 14 and the Identikit have the same content as their `LIESMICH.TXT` (TKKG 11 to 14 store it as a PDF). The discs of TKKG 4 to 9 have no Mac readme.
- `HILFE.PDF` is the game's help file. For TKKG 1 to 9, it also covers system requirements and troubleshooting before the full solution. The solution gives away the whole case, so read it only if you are stuck. The Macintosh Repository discs of TKKG 1 to 3 have no help file, so the help files of these games come from later releases, listed in [Checksums](docs/checksums.md).
- `PRINT/PCT` holds the print pages as stored on the disc, in the Macintosh PICT format. `PRINT/PDF` holds PDF conversions of them. The PDF pages are larger than A4, so choose a scale-to-fit option when you print.
- `HTMLD` and `HTMLE` in `TKKG4` hold the web pages. Open their `INDEX.HTM` in a web browser. The pages refer to their files in lowercase, so they only work on a case-insensitive file system, which is the macOS default.

## Advanced topics

- [Checksums](docs/checksums.md): the SHA-1 of every archive, the size and SHA-1 of every disc image, and the sources of the TKKG 1 to 3 help files.
- [Accessing game data](docs/game-data.md): how to read files from the disc images on macOS without running the games, for example to extract pictures or sound.

### Install Mac OS 9 yourself

Instead of the preinstalled VM, UTM can create a new VM from a Mac OS 9 installer disc image that you provide: click + in UTM, choose Emulate > Classic Mac OS and select Power Macintosh G4 (1999, PPC). UTM's [Classic Mac OS guide](https://docs.getutm.app/guides/classic-macos/) describes the steps. Fresh installs of Mac OS 9.2.1 and 9.2.2 can freeze at "About 4 minutes" remaining. This bug, [UTM issue #6936](https://github.com/utmapp/UTM/issues/6936), is still open, so this guide uses the preinstalled VM. If you build your own VM, set the CPU to `g3` as well.
