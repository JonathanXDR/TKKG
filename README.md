# TKKG on modern Macs

TKKG (Tim, Karl, Klößchen and Gaby) is a German youth detective series. Between 1997 and 2005, Tivola released 14 TKKG adventure games and the TKKG Identikit (Das Phantombild Programm) for Windows and classic Mac OS.

Current Macs can't run classic Mac OS. This guide shows how to play the original Mac versions in [UTM](https://getutm.app/), which emulates a PowerPC Mac running Mac OS 9.

## Contents

- [Requirements](#requirements)
- [Setup](#setup)
- [Playing](#playing)
- [Troubleshooting](#troubleshooting)
- [Original game documentation](#original-game-documentation)
- [Advanced topics](#advanced-topics)

## Requirements

- A Mac running macOS 12 Monterey or later
- About 8 GB of free disk space for all games
- For TKKG 10 only, a free [Macintosh Repository](https://www.macintoshrepository.org/) account

## Setup

You only need to set things up once. Keep the disc images and the Mac OS 9 virtual machine (VM) in a folder named `TKKG` in your home folder. iCloud Drive doesn't sync this folder, so macOS won't move the large files off your Mac to save space.

The Terminal commands in this guide are optional. To run one, open Terminal from Applications > Utilities, paste the command and press Return.

### 1. Install UTM

> [!IMPORTANT]
> You need UTM 5.0.9 (build 132) or later, because earlier versions have bugs that affect Mac OS 9. The Mac App Store version can lag behind, so use the free download.

Download UTM from [getutm.app](https://getutm.app/), open the DMG and drag UTM to your Applications folder. UTM > About UTM shows the version, for example 5.0.9 (132).

If you use [Homebrew](https://brew.sh/), you can install UTM with this command instead:

```bash
brew install --cask utm
```

### 2. Download the games

| Game | German title | Download | Languages |
| --- | --- | --- | --- |
| TKKG 1 | Katjas Geheimnis | [Internet Archive](https://archive.org/details/tkkg-01) | DE, EN |
| TKKG 2 | Tödliche Schokolade | [Internet Archive](https://archive.org/details/tkkg-02) | DE, EN |
| TKKG 3 | Der Schatz der Maya | [Internet Archive](https://archive.org/details/tkkg-03) | DE, EN |
| TKKG 4 | Das Rätsel der Villa Drachenkralle | [Internet Archive](https://archive.org/details/tkkg-4_202605) | DE, EN |
| TKKG 5 | Verrat an TKKG | [Internet Archive](https://archive.org/details/tkkg-05) | DE, EN |
| TKKG 6 | Der Fälscherbande auf der Spur | [Internet Archive](https://archive.org/details/tkkg-06) | DE, EN |
| TKKG 7 | Wer stoppt den Feuerteufel? | [Internet Archive](https://archive.org/details/tkkg-7_202201) | DE, EN |
| TKKG 8 | Das geheimnisvolle Testament | [Internet Archive](https://archive.org/details/tkkg-8_202201) | DE, EN |
| TKKG 9 | Voodoozauber | [Internet Archive](https://archive.org/details/tkkg-9_202201) | DE, EN |
| TKKG 10 | Panik im Internat | [Macintosh Repository](https://www.macintoshrepository.org/2997-tkkg-10-panik-im-internat) | DE |
| TKKG 11 | Film ab! | [Internet Archive](https://archive.org/details/tkkg-11) | DE |
| TKKG 12 | Alarm in der Geisterbahn | [Internet Archive](https://archive.org/details/tkkg-12) | DE |
| TKKG 13 | Zelle 13 | [Internet Archive](https://archive.org/details/tkkg-13) | DE |
| TKKG 14 | Gefährliche Ferien | [Internet Archive](https://archive.org/details/tkkg-14) | DE |
| Identikit | Das Phantombild Programm | [Internet Archive](https://archive.org/details/Identikit) (EN), [Macintosh Repository](https://www.macintoshrepository.org/4209-tkkg-identikit) (DE) | DE, EN |

DE is German and EN is English.

1. Create a folder named `TKKG` in your home folder. In the Finder, choose Go > Home, then File > New Folder.
2. For each game on the Internet Archive, open its link and click ISO IMAGE under Download Options. Move the downloaded disc image to the `TKKG` folder.
3. TKKG 10 and the German Identikit come from Macintosh Repository as `.sit` archives. For TKKG 10, sign in first, because guests can only download files under 100 MB. Open each archive with the free [The Unarchiver](https://theunarchiver.com/) and move the extracted disc image to the `TKKG` folder. The image of TKKG 10 is named `TKKG.iso`.

To download all Internet Archive images in Terminal instead, run this command. It downloads about 7 GB into the `TKKG` folder and creates the folder if needed:

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

> [!NOTE]
> macOS shows an error if you double-click one of these disc images, because it can't read their Mac part. Mac OS 9 in UTM reads them without problems, so don't convert them.

### 3. Add the Mac OS 9 virtual machine

The UTM project provides a preinstalled Mac OS 9.2.1 VM. The games are known to work in it with the settings below. The English Identikit is untested.

1. Download [`mac-os-9.2.1-utm.zip`](https://github.com/utmapp/vm-downloads/releases/download/mac-os-9.2.1/mac-os-9.2.1-utm.zip) (141 MB). If Safari doesn't unpack it automatically, double-click it.
2. Move `Mac OS 9.2.1.utm` from your Downloads folder to the `TKKG` folder, then double-click it. UTM opens and lists the VM.
3. Right-click the VM and choose Edit.
4. Under System, set CPU to `g3`. TKKG 12 quits after its intro on the default G4 processor.
5. Optionally, right-click Network in the sidebar and choose Remove. The games don't need a network, and Mac OS 9 no longer gets security updates.
6. Click Save.

### 4. Set up Mac OS 9

1. Select the VM in UTM and click Play. After a minute or two, the Mac OS 9 desktop appears with the hard disk "untitled".
2. If a setup assistant opens, quit it with Command-Q.
3. In the menu bar of the VM window, choose Apple menu > Control Panels > Monitors. Choose Thousands under Color Depth and 800 × 600 under Resolution, then close the window.
4. Optionally, set up a printer that saves to files. Do this before you play TKKG 6, which can freeze Mac OS 9 when it prints without a printer. Open the "untitled" hard disk, then Applications (Mac OS 9) > Utilities > Desktop Printer Utility. Choose Translator (PostScript) and create the desktop printer. Each print then saves a PostScript file in Mac OS 9.

## Playing

### Start a game

1. If Mac OS 9 isn't running, select the VM in UTM and click Play, then wait for the desktop.
2. If another game's disc is on the Mac OS 9 desktop, select it and press Command-E to eject it.
3. In UTM's main window, select the VM, click CD/DVD, choose Browse… and select the game's disc image in the `TKKG` folder. The disc appears on the Mac OS 9 desktop. If its window doesn't open, double-click it.
4. The first time you play TKKG 1 to 10 or the Identikit, drag the game folder, such as "TKKG 1", from the disc window onto the "untitled" hard disk. Don't copy the folder with an arrow in its name, such as "<- auf die Festplatte kopieren". It only points at the game folder. If the Finder asks whether to replace the folder, click Cancel.
5. For TKKG 6, first choose 256 under Color Depth in the Monitors control panel, because it doesn't switch by itself. Switch back to Thousands after you quit it.
6. Double-click the game's start icon. Its name contains "Start", such as "TKKG Start" or "Phantombild Start", or is the game number, such as "TKKG10". It's in the copied folder on the hard disk, or in the disc window for TKKG 11 to 14.

Leave the disc inserted while you play. If a game shows a TKKG membership card, click Neues Mitglied (new member) to start a new game, or Mitglied (member) to continue a saved one.

To switch games, quit the current game with its own exit button or menu, wait for the Mac OS 9 desktop, then repeat these steps.

### Quit

> [!WARNING]
> Quit each game from inside the game before you shut down Mac OS 9 or stop the VM. Otherwise, you can lose unsaved progress.

To finish, choose Special > Shut Down in Mac OS 9, then quit UTM. If you don't see the Special menu, click the desktop first.

The games save your progress inside the VM. To back it up, copy `Mac OS 9.2.1.utm` while the VM is shut down.

## Troubleshooting

### Mac OS 9 doesn't start, hangs or crashes with a sound error

Make sure you use UTM 5.0.9 or later. If Mac OS 9 still crashes with a sound error, stop the VM, right-click it and choose Edit. Right-click Sound in the sidebar, choose Remove and click Save. The games then play without sound.

If the VM window stays black apart from the clock in the menu bar, click inside the window.

### The disc doesn't appear in Mac OS 9

- Check that the CD/DVD row in UTM shows the image name and not "(empty)".
- Make sure you selected the `.iso` disc image and not a `.sit` archive.
- If the previous game's disc is still on the desktop, eject it and select the new image again.

### UTM reports "Operation not permitted" or "Failed to access drive image path"

UTM loses access to a disc image after you move or rename it. Click CD/DVD, choose Browse… and select the image again.

### Colours look wrong or a game complains about the display

In the Monitors control panel, choose Thousands and 800 × 600, or 256 colours for TKKG 6.

### TKKG 12 quits after the intro with "an error of type 3"

Shut down Mac OS 9 and set the CPU to `g3`, as described in [Add the Mac OS 9 virtual machine](#3-add-the-mac-os-9-virtual-machine).

### Graphics errors in the final game of TKKG 14

According to the TKKG 14 readme, pressing Command-Shift-0 or Command-Shift-minus during the final game fixes these errors.

### A game shows image noise or other errors

The disc image may be incomplete or damaged. Compare it with [Checksums](docs/checksums.md) and download it again from the link in [Download the games](#2-download-the-games).

### Mac OS 9 freezes when a game prints

Click Stop in UTM and confirm that you want to force stop the VM. You can lose progress made since you last quit the game. At the next start, let Disk First Aid finish checking the hard disk.

To prevent the freeze, set up the file printer described in [Set up Mac OS 9](#4-set-up-mac-os-9). The printouts of TKKG 1, 2 and 4 are also in the [`content`](content) folder as PDFs.

### The game runs slowly or the sound stutters

UTM emulates the PowerPC processor in software, so speed depends on your Mac. Close demanding apps and keep the VM window in front. More memory for the VM doesn't help.

## Original game documentation

The [`content`](content) folder has a folder for each game with the documentation from its original disc, mostly in German.

- `LIESMICH.TXT` is the readme. The English Identikit's readme is `README.TXT`, and the TKKG 6 readme is in the `TKKG7` folder, as on the original TKKG 7 disc.
- `LIESMICH_MAC.TXT` is the Mac readme of TKKG 1 to 3. The readmes of these three games hide hints far below the main text.
- `HILFE.PDF` is the help file. It contains the full solution for TKKG 1 to 9 and solution hints for TKKG 13 and 14, so read it only if you're stuck.
- `PRINT` holds the pages that TKKG 1, 2 and 4 can print, such as the decoder disc of TKKG 1, as PDFs and original PICT files. A `D` or `E` in the file name marks the German or English version. The PDF pages are larger than A4, so print them scaled to fit.
- `HTMLD` and `HTMLE` in `TKKG4` hold the web pages of the in-game archive computer in German and English. Open `INDEX.HTM` in a web browser.

## Advanced topics

- [Checksums](docs/checksums.md) lists the size and SHA-1 of every disc image and the known incomplete copies.
- [Accessing game data](docs/game-data.md) shows how to read files from the disc images on macOS without running the games.
- To install Mac OS 9 yourself instead of using the preinstalled VM, follow UTM's [Classic Mac OS guide](https://docs.getutm.app/guides/classic-macos/) and set the CPU to `g3`. Installing Mac OS 9.2.1 or 9.2.2 can freeze at "About 4 minutes" remaining because of [UTM issue #6936](https://github.com/utmapp/UTM/issues/6936).
