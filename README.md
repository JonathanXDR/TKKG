# TKKG on modern Macs

TKKG (Tim, Karl, Klößchen and Gaby) is a German youth detective series. Between 1997 and 2005, Tivola released 14 TKKG adventure games for Windows and classic Mac OS, plus the TKKG Identikit (Das Phantombild Programm). Two later games, TKKG 15 and 16, came out for Windows only.

The Mac versions run on classic Mac OS: the early games from System 7.1, the later ones from Mac OS 8.1 to 9.1, depending on the game. TKKG 11 to 14 also run on early Mac OS X, but only on PowerPC Macs. None of them run on current Macs. This guide sets up [UTM](https://getutm.app/) to emulate a PowerPC Mac with Mac OS 9 and runs the original game discs in it. UTM runs only on Apple devices, so the guide doesn't cover Windows or Linux.

The [`content`](content) folder holds the readme files, help files and printouts from the original discs.

## Contents

- [Requirements](#requirements)
- [1. Install UTM and The Unarchiver](#1-install-utm-and-the-unarchiver)
- [2. Download the games](#2-download-the-games)
- [3. Set up Mac OS 9](#3-set-up-mac-os-9)
- [4. Start a game](#4-start-a-game)
- [5. Switch games and quit](#5-switch-games-and-quit)
- [Troubleshooting](#troubleshooting)
- [Original readmes, help files and printouts](#original-readmes-help-files-and-printouts)
- [Accessing game data](#accessing-game-data)

## Requirements

- A Mac with Apple silicon or an Intel processor, running macOS 12 Monterey or later (the minimum for UTM 5).
- About 11 GB of free disk space for all 15 games: 7.1 GB for the disc images, 3.2 GB for the downloaded archives (you can delete them after extracting) and 0.5 GB for Mac OS 9.
- A free [Macintosh Repository](https://www.macintoshrepository.org/) account. Guests can only download files under 100 MB, and every game except the Identikit is larger.

## 1. Install UTM and The Unarchiver

1. Install UTM 5.0.9 (build 132) or later. Download it from [getutm.app](https://getutm.app/) or the [UTM releases on GitHub](https://github.com/utmapp/UTM/releases/latest), open the DMG and drag UTM to your Applications folder. With [Homebrew](https://brew.sh/), run `brew install --cask utm` instead. UTM > About UTM shows the version with the build number in brackets, for example 5.0.9 (132). The earlier 5.0.9 builds 130 and 131 can crash a VM at start-up on macOS 14 and later.
2. Install [The Unarchiver](https://theunarchiver.com/), which is free and also available on the [Mac App Store](https://apps.apple.com/app/the-unarchiver/id425424353). Most games come as StuffIt (`.sit`) archives, which the Archive Utility built into macOS can't open.

> [!TIP]
> UTM is also sold on the Mac App Store. That version has the same features, but its updates can arrive later than the free download. In November 2026 it was still at 5.0.8, which lacks the Mac OS 9 fixes from 5.0.9. In 5.0.8, Restart can end on a black screen, start-up sometimes hangs at "Starting Up…", and sound can fail or crackle.

## 2. Download the games

[Macintosh Repository](https://www.macintoshrepository.org/) offers each game as a StuffIt archive that holds one disc image. Sign in before you download. Members can download up to 20 files a day. According to the site's rules, downloads through a proxy, a download manager or a VPN that changes your IP address can fail.

TKKG 6 is the exception: its Macintosh Repository copy is damaged, so get it from the Internet Archive.

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

> [!WARNING]
> Don't use the [TKKG 6 download from Macintosh Repository](https://www.macintoshrepository.org/3430-tkkg-6-the-forged-fifties). Its `TKKG6.iso` is incomplete: the file ends about 13.8 MB before the end of its own file system, and several game files on it contain runs of zero bytes. In the game, the hotel reception shows noise bands, and other scenes can fail too. The intact `TKKG 06.iso` from the Internet Archive is 415,098,880 bytes, and `shasum "TKKG 06.iso"` prints `a22d2e8bfb1b2e848f067845cdde75efd5ac3dcc`.

To extract the disc images:

1. Double-click each `.sit` archive, for example `tkkg1.cdr_.sit`. The first time, The Unarchiver asks where to extract archives: choose Extract to Same Folder. The Mac App Store version of The Unarchiver then asks for permission to use the folder: click Extract.
2. Check that you got the disc image listed in the table. TKKG 10's image is named `TKKG.iso`. The TKKG 6 download from the Internet Archive is already a disc image and needs no extracting. [Checksums](docs/checksums.md) lists the SHA-1 of every archive and the size and SHA-1 of every disc image, so you can check that nothing is damaged.
3. Move the images to a folder where they can stay. UTM remembers each image by its location, so after a move you have to choose it again.
4. Delete the `.sit` archives after you have extracted all images.

On the command line, `unar tkkg1.cdr_.sit` does the same. Homebrew's `brew install unar` has it ready-made for Apple silicon Macs with macOS 15 or later. On other Macs, Homebrew needs Xcode to build it.

The images are hybrid Mac and Windows discs. Don't convert them. macOS shows an error when you double-click one, because current macOS versions can't read the classic Mac file system on these discs. Mac OS 9 in UTM reads them without problems.

## 3. Set up Mac OS 9

This guide uses the preinstalled Mac OS 9.2.1 virtual machine (VM) that the UTM project published for its former gallery. All 15 discs ran in it with the settings below.

1. Download [`mac-os-9.2.1-utm.zip`](https://github.com/utmapp/vm-downloads/releases/download/mac-os-9.2.1/mac-os-9.2.1-utm.zip) (141 MB) from the UTM project's [vm-downloads releases](https://github.com/utmapp/vm-downloads/releases/tag/mac-os-9.2.1). UTM no longer updates this VM, but it still works. To check the download, run `shasum -a 256 mac-os-9.2.1-utm.zip` in Terminal. It should print `13d2bb7db75bc4e8e94e181dd5ded1484a22dd07d5fe91a6464cde338400f508`.
2. Double-click the zip file to unpack it. You get `Mac OS 9.2.1.utm`. If Safari has already unpacked it, you find `Mac OS 9.2.1.utm` in your Downloads folder.
3. Move `Mac OS 9.2.1.utm` to the folder where you want to keep it. UTM runs a VM from the place you open it, without copying it.
4. Double-click `Mac OS 9.2.1.utm`. UTM opens and lists the VM in its sidebar.
5. Select the VM and click the Edit button (the slider icon at the right end of the toolbar), or right-click the VM and choose Edit. Change these settings, then click Save:
   - System: set CPU to `g3`. The default is a G4 processor, on which TKKG 12 crashed right after its intro in testing. With the G3, all 15 discs ran.
   - Network (optional): right-click Network in the sidebar and choose Remove. The games don't use the network, and Mac OS 9 no longer gets security updates.

   Leave the memory at 512 MB. More memory doesn't make the emulation faster.
6. Click the Play button. Within a minute or two, the Mac OS 9 desktop appears, with the hard disk "untitled" in the top right corner. On the first start, the Mac OS Setup Assistant opens, and possibly the AirPort Setup Assistant. The games need neither, so quit them with Command-Q. You can move the mouse pointer in and out of the VM window without capturing it.
7. Open the Apple menu > Control Panels > Monitors. Use the Apple menu of Mac OS 9, the Apple logo at the left end of the menu bar inside the VM window, not the one in the macOS menu bar. Choose Thousands under Color Depth and 800 × 600 under Resolution, then close the window with the box at its top left.
8. Optional: set up a printer that saves to files. Some games can print, and Mac OS 9 froze when TKKG 6 printed while no printer was set up. Open the "untitled" hard disk, then Applications (Mac OS 9) > Utilities > Desktop Printer Utility. Choose Translator (PostScript) and create the desktop printer. Each print then asks for a file name and saves a PostScript file in Mac OS 9.

TKKG 10 to 14 need at least 800 × 600. TKKG 7 to 14 and the Identikit ran at Thousands in testing, and most of their readme and help files ask for 32,768 colours. TKKG 1 to 5 switch to 256 colours themselves. TKKG 6 needs 256 colours set by hand, as described in [Start a game](#4-start-a-game).

To stop the VM, choose Special > Shut Down in Mac OS 9. The Special menu belongs to the Finder: if you don't see it, click the desktop first.

### Alternative: install Mac OS 9 yourself

Skip this if you use the preinstalled VM. UTM can also create a new VM from a Mac OS 9 installer disc image that you provide: click + in UTM, choose Emulate > Classic Mac OS and select Power Macintosh G4 (1999, PPC). UTM's [Classic Mac OS guide](https://docs.getutm.app/guides/classic-macos/) describes the steps. Fresh installs of Mac OS 9.2.1 and 9.2.2 can freeze at "About 4 minutes" remaining. This bug, [UTM issue #6936](https://github.com/utmapp/UTM/issues/6936), is still open, so this guide uses the preinstalled VM. If you build your own VM, set the CPU to `g3` as well.

## 4. Start a game

1. If another game's disc is on the Mac OS 9 desktop, eject it first, as described in [Switch games and quit](#5-switch-games-and-quit). Then select the VM in UTM's main window, click CD/DVD in its details, choose Browse… and select the game's disc image. This works while the VM is running or stopped. In a running VM's window, the Drives toolbar button offers the same: choose the CD/DVD drive, then Change.
2. In Mac OS 9, the disc appears on the desktop, named after the game, for example "TKKG 1". If its window doesn't open by itself, double-click the disc icon.
3. For TKKG 6 only: open the Apple menu > Control Panels > Monitors and choose 256 under Color Depth. TKKG 6 needs 256 colours and doesn't switch by itself. Switch back to Thousands for the other games.
4. The first time you play TKKG 1 to 10 or the Identikit, install it: drag the game folder from the disc window onto the "untitled" hard disk icon. Ignore the folder "<- auf die Festplatte kopieren" ("copy to the hard disk"). It is empty, and its name is an arrow that points at the game folder. Copy each game only once. If the Finder asks whether to replace an existing item, click Cancel to keep the copy you already have. TKKG 11 to 14 need no installation.
5. Start the game. For TKKG 1 to 10 and the Identikit, open the copied folder on the hard disk and double-click the start icon. For TKKG 11 to 14, double-click the start icon in the disc window.

   | Game | Folder to copy | Start icon |
   | --- | --- | --- |
   | TKKG 1 to 4 | TKKG 1, TKKG 2, TKKG 3, TKKG 4 | TKKG start |
   | TKKG 5 | TKKG 5 | TKKG Start |
   | TKKG 6 to 9 | TKKG 6, TKKG 7, TKKG 8, TKKG 9 | TKKG-Start |
   | TKKG 10 | TKKG10 | TKKG10 |
   | Identikit | Phantombild | Phantombild Start |
   | TKKG 11 to 14 | None (they start from the disc) | TKKG11, TKKG12, TKKG13, TKKG14 |

   The original readme files sometimes spell these names differently. The table shows the names on the discs.
6. Leave the disc inserted while you play. The games load pictures and sound from it.

If a game opens with a TKKG membership card, click Neues Mitglied (new member) to start a new game. Next time, click Mitglied (member) and choose your name to continue where you left off.

## 5. Switch games and quit

- Quit each game from inside the game, using its own exit button or menu, and wait until the Mac OS 9 desktop is back. If you stop the VM while a game is running, you can lose progress. TKKG 6, for example, lost everything since it was last quit from inside the game.
- To change discs, eject the current one in Mac OS 9: drag the disc icon to the Trash in the bottom right corner of the desktop, or select it and press Command-E. Then choose the next image as in step 1 of [Start a game](#4-start-a-game). Skip the installation for a game you have installed before.
- Shut down Mac OS 9 with Special > Shut Down before you quit UTM.
- To play again later, start the VM. UTM keeps the last disc inserted, so it appears on the desktop again. For TKKG 1 to 10 and the Identikit, start the game from its folder on the hard disk. For TKKG 11 to 14, use the start icon on the disc.
- The games save your progress inside the VM. To back it up, shut down the VM and copy `Mac OS 9.2.1.utm` in the Finder.

## Troubleshooting

### TKKG 12 quits after the intro with "an error of type 3"

The VM uses the default G4 processor. Shut down Mac OS 9 and set System > CPU to `g3` in the VM settings, as in step 5 of [Set up Mac OS 9](#3-set-up-mac-os-9).

### UTM reports "Operation not permitted" or "Failed to access drive image path"

UTM can only open files that you selected in UTM yourself. After you move or rename a disc image, UTM loses access to it. Click CD/DVD, choose Browse… and select the image again.

### UTM reports "IDE unit 0 is in use"

This happens after you add a drive to the VM. The UTM project built the preinstalled VM with an older UTM version that put each IDE drive on its own bus, so a newly added drive can claim a slot that is already taken. You don't need an extra drive, because the VM already has a CD/DVD drive. Open the VM settings, right-click the drive you added (the last IDE Drive under Drives), choose Delete, confirm with Delete and click Save.

If you do need another drive, click Update Interface on every IDE drive that shows this button, then click Save. This puts all drives on the current layout with two drives per bus.

### The VM doesn't start, or Mac OS 9 crashes at start-up with a sound error

The emulated sound device, Screamer, has known problems. Update to UTM 5.0.9 or later, which fixes several of them. If the problem stays, remove the sound device: in the VM settings, right-click Sound and choose Remove. The games then play without sound.

### Mac OS 9 hangs at "Starting Up…" or after Restart

UTM 5.0.8 and earlier have two bugs that cause this ([UTM issue #8033](https://github.com/utmapp/UTM/issues/8033) and [UTM issue #7999](https://github.com/utmapp/UTM/issues/7999)). Update to UTM 5.0.9 or later. With an older version, stop the VM in UTM, start it again and use Shut Down instead of Restart.

If the VM window stays black apart from the menu bar clock after start-up, click inside the window.

### The disc doesn't appear in Mac OS 9

- Check that the CD/DVD row in UTM shows the image name and not "(empty)".
- Make sure you selected the extracted `.cdr` or `.iso` image and not the `.sit` archive.
- If the desktop still shows the previous game's disc, eject it in Mac OS 9 and select the new image again.
- If the extraction stopped early, the image is incomplete. Compare its size and SHA-1 with [Checksums](docs/checksums.md), then extract it again, or download it again.

### Colours look wrong or a game complains about the display

Set the Monitors control panel to the values the game needs: 256 colours for TKKG 6, Thousands for TKKG 7 to 14 and the Identikit, and at least 800 × 600 for TKKG 10 to 14.

### TKKG 6 shows noise bands in the hotel reception

You are using the damaged image from Macintosh Repository. Replace it with the intact copy from the Internet Archive, as described in the warning under [Download the games](#2-download-the-games).

### Mac OS 9 can freeze when a game prints

Mac OS 9 froze when TKKG 6 printed while no printer was set up. If this happens, click Stop in UTM and confirm that you want to force stop the VM. You can lose progress since you last quit the game from inside it. At the next start, Disk First Aid checks the hard disk. Let it finish.

To prevent the freeze, set up the file printer from step 8 of [Set up Mac OS 9](#3-set-up-mac-os-9). The printouts of TKKG 1, 2 and 4 are also in the [`content`](content) folder as PDFs.

### Graphics errors in the final game of TKKG 14

TKKG 14's readme says that pressing Command-Shift-0 or Command-Shift-minus during the final game (Finalspiel) fixes these errors.

### The game runs slowly or the sound stutters

UTM emulates the PowerPC processor in software on a single core, so speed depends on your Mac. Close demanding apps and keep the VM window in front, because macOS can slow down apps in the background. UTM 5.0.9 also fixes crackling sound while the Mac is busy. Raising the VM's memory doesn't help.

## Original readmes, help files and printouts

The [`content`](content) folder holds documentation copied from the original discs. The files are in German unless noted. In printout names, a `D` marks the German version and an `E` the English one, for example `SZ28D1.pdf` and `SZ28E1.pdf`.

| Folder | Contents |
| --- | --- |
| [`TKKG1`](content/TKKG1) | Help file with the solution. Windows and Mac readmes, both with hidden hints. Printouts: decoder disc with assembly instructions, Oma Peper's chocolate cake recipe (German and English). |
| [`TKKG2`](content/TKKG2) | Help file with the solution. Windows and Mac readmes, both with hidden hints. Printout: Sauerlich's special biscuits recipe (German and English). |
| [`TKKG3`](content/TKKG3) | Help file with the solution. Windows and Mac readmes, both with hidden hints. |
| [`TKKG4`](content/TKKG4) | Help file with the solution. Web pages from the in-game city archive computer (`HTMLD` German, `HTMLE` English). Printouts: piano basics, "Für Elise" sheet music, Oma Peper's nut cake recipe (German and English). |
| [`TKKG5`](content/TKKG5), [`TKKG6`](content/TKKG6), [`TKKG9`](content/TKKG9) | Help file with the solution. |
| [`TKKG7`](content/TKKG7) | Help file with the solution. The readme belongs to TKKG 6: the original TKKG 7 disc contains the same mix-up. |
| [`TKKG8`](content/TKKG8) | Help file with the solution, readme. |
| [`TKKG10`](content/TKKG10), [`TKKG11`](content/TKKG11), [`TKKG12`](content/TKKG12) | Readme. |
| [`TKKG13`](content/TKKG13), [`TKKG14`](content/TKKG14) | Help file with solution hints, readme. |
| [`TKKG_Identikit`](content/TKKG_Identikit) | Readme. |

- `LIESMICH.TXT` is the readme, stored here as UTF-8 text. Most readmes list system requirements, installation steps and the historical Tivola support contacts. The readmes of TKKG 1 to 3 hide hints far below the main text.
- `LIESMICH_MAC.TXT` is the Mac readme from the game folder on the discs of TKKG 1 to 3, also stored as UTF-8 text. It lists the Mac system requirements and installation steps. The Mac readmes of TKKG 10 to 14 and the Identikit have the same content as their `LIESMICH.TXT` (TKKG 11 to 14 store it as a PDF). The discs of TKKG 4 to 9 have no Mac readme.
- `HILFE.PDF` is the game's help file. For TKKG 1 to 9, it also covers system requirements and troubleshooting before the full solution. The solution gives away the whole case, so read it only if you are stuck. The Macintosh Repository discs of TKKG 1 to 3 have no help file, so the help files of these games come from later releases, listed in [Checksums](docs/checksums.md).
- `PRINT/PCT` holds the print pages as stored on the disc, in the Macintosh PICT format. `PRINT/PDF` holds PDF conversions of them. The PDF pages are larger than A4, so choose a scale-to-fit option when you print.
- Open `INDEX.HTM` in `TKKG4/HTMLD` or `TKKG4/HTMLE` in a web browser to see the web pages. The pages refer to their files in lowercase, so they only work on a case-insensitive file system, which is the macOS default.

## Accessing game data

To read files from the disc images on macOS without running the games, for example to extract pictures or sound, see [Accessing game data](docs/game-data.md).
