# TKKG Games - Complete Setup and Access Guide

This comprehensive guide covers how to play the classic TKKG adventure games and access their data files. The TKKG series consists of 14 main games plus an additional Identikit tool, originally released for classic Mac systems. There are also two additional games that were released for Windows, but this guide focuses on the Mac versions.

> [!IMPORTANT]  
> This guide is specifically written for **macOS** as the host system. The tools used (UTM, The Unarchiver) and setup procedures are macOS-specific. Users on Windows or Linux will need to find alternative tools and may need to adapt the instructions accordingly.

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Playing the Games](#playing-the-games)
- [Game Documentation and Manuals](#game-documentation-and-manuals)
- [System Requirements](#system-requirements)
- [Troubleshooting](#troubleshooting)
- [Accessing Game Data (For Developers)](#accessing-game-data-for-developers)

## Playing the Games

### Step 1: Download the Games

The TKKG games were originally distributed on CD-ROM for classic Macintosh systems in the 1990s and early 2000s. These games are now preserved as disc images on the Macintosh Repository, a digital preservation archive for vintage Mac software.

> [!NOTE]  
> You'll need a free account on Macintosh Repository to download files larger than 100 MB. Each TKKG game exceeds this size limit, so account creation is mandatory.

**Complete Game List:**

- [TKKG 1: Jennifer is Missing](https://www.macintoshrepository.org/5387-tkkg-1-jennifer-is-missing)
- [TKKG 2: Deadly Chocolate](https://www.macintoshrepository.org/4794-tkkg-2-deadly-chocolate)
- [TKKG 3: The Mystery of the Mayan Treasure](https://www.macintoshrepository.org/3393-tkkg-3-the-mystery-of-the-mayan-treasure)
- [TKKG 4: The Secret of Dragon Claw Manor](https://www.macintoshrepository.org/6174-tkkg-4-the-secret-of-dragon-claw-manor)
- [TKKG 5: TKKG Betrayed](https://www.macintoshrepository.org/4717-tkkg-5-tkkg-betrayed)
- [TKKG 6: The Forged Fifties](https://www.macintoshrepository.org/3430-tkkg-6-the-forged-fifties)
- [TKKG 7: Fire!](https://www.macintoshrepository.org/4043-tkkg-7-fire-)
- [TKKG 8: The Captain's Legacy](https://www.macintoshrepository.org/6187-tkkg-8-the-captain-s-legacy)
- [TKKG 9: Voodoo Magic](https://www.macintoshrepository.org/5744-tkkg-9-voodoo-magic)
- [TKKG 10: Panik im Internat](https://www.macintoshrepository.org/2997-tkkg-10-panik-im-internat)
- [TKKG 11: Film ab!](https://www.macintoshrepository.org/3133-tkkg-11-film-ab-)
- [TKKG 12: Alarm in der Geisterbahn](https://www.macintoshrepository.org/3884-tkkg-12-alarm-in-der-geisterbahn)
- [TKKG 13: Zelle 13](https://www.macintoshrepository.org/5302-tkkg-13-zelle-13)
- [TKKG 14: Gefährliche Ferien](https://www.macintoshrepository.org/3506-tkkg-14-gefahrliche-ferien)
- [TKKG Identikit](https://www.macintoshrepository.org/4209-tkkg-identikit)

> [!TIP]
> Start with TKKG 1 if you're new to the series. The games follow a chronological storyline featuring the four main characters: Tim, Karl, Klösschen, and Gaby.

### Step 2: Extract the Game Files

The games are downloaded as `.sit` files (StuffIt archives), which was a popular compression format for classic Mac files. Modern systems can't open these natively, so we need specialized software.

1. Download [The Unarchiver](https://theunarchiver.com/) - a free Mac application that can handle various vintage archive formats including StuffIt
2. Install The Unarchiver on your system
3. Use The Unarchiver to extract the downloaded `.sit` files
4. After extraction, you should have game files with `.cdr` (CD-ROM image) or `.iso` (International Organization for Standardization disc image) extensions

> [!NOTE]  
> The extracted files are disc images - exact digital copies of the original game CDs. These contain all the game data, audio, and program files as they existed on the original media.

### Step 3: Set Up the Emulation Environment

Since these games were designed for classic Macintosh systems running Mac OS 8 or 9 in the late 1990s and early 2000s, they cannot run on modern macOS versions due to fundamental architectural changes. That means we need to emulate the original environment by using a virtual machine. A Virtual Machine (VM) is a software simulation of a physical computer and allows us to run a complete operating system within our current OS. So we'll be essentially running a virtual classic Mac computer inside your modern Mac.

#### Download UTM

[UTM](https://mac.getutm.app/) is a powerful virtualization app for macOS that can emulate different computer architectures, including the PowerPC processors that classic Macs used.

1. Download UTM from the official website
2. Install UTM on your system (requires macOS 11.0 or later)

#### Download macOS 9.2.2 VM

Rather than installing Mac OS 9 from scratch (which would require original installation media and complex setup), we use a pre-configured virtual machine.

1. Download the macOS 9.2.2 UTM file from [Archive.org](https://archive.org/download/mac-os-ppc-utm-vms)
2. Extract the downloaded zip file
3. Open the extracted VM file with UTM

> [!NOTE]  
> This VM comes pre-installed with Mac OS 9.2.2, which was one of the last and most stable versions of classic Mac OS. It provides the best compatibility with late-era classic Mac games like TKKG.

### Step 4: Configure the Virtual Machine

Now we need to make the TKKG game accessible to our virtual classic Mac. In emulation, we simulate hardware components including CD-ROM drives. By "mounting" a game disc image as a virtual drive, the emulated Mac OS thinks a physical game CD has been inserted.

1. **Open UTM** and locate your macOS 9.2.2 VM
2. **Right-click the VM** and select "Edit"
3. **Add a new drive:**
   - Click the "+" button to add hardware
   - Select "Drive"
   - **Interface**: Choose "IDE" (the standard interface for CD-ROM drives in that era)
   - **Type**: Set to "Disk Image"
   - Click "Browse" and select one of your extracted TKKG game files (`.cdr` or `.iso`)
4. **Save the VM configuration**

> [!TIP]
> You can change which game disc is "inserted" by editing the VM configuration and selecting a different game file. This simulates swapping CDs in a physical drive.

### Step 5: Start Playing

1. **Start the VM** in UTM
2. **Wait for macOS 9.2.2 to boot** - This may take a minute or two as it emulates vintage hardware
3. **Look for the game drive** that should appear as an icon on the Mac OS 9 desktop
4. **Double-click the game icon** to launch it

> [!NOTE]  
> The games will run at their original speed and resolution. You may notice the interface looks dated - this is authentic to the original 1990s-2000s Mac gaming experience.

## Game Documentation and Manuals

For your convenience, all documentation from each TKKG game has been extracted from the original game files and is available in this repository. This includes README files and all printable materials in both their original format and as converted PDFs.

> [!TIP]
> These files were originally only accessible by mounting the game disc images and extracting them manually. By providing them here, players can access important game information without needing to perform the technical extraction process described in the developer section.

### What's Included

**README Files** - Text files (typically named `LIESMICH.TXT` or similar) containing:

- Installation instructions for the original versions
- Technical requirements and display settings recommendations
- Gameplay hints and walkthrough tips
- Contact information for technical support (historical reference)

**Printable Materials** - Available in two formats:

- **Original PCT files** - The native Macintosh picture format as stored on the game CDs
- **Converted PDF files** - Modern, easily viewable versions of the same content

The printable materials may include reference cards, hint guides, decoder wheels, maps, or other supplementary materials designed to be printed and used while playing.

### File Organization

Look for files organized by game number in the repository inside the `contents/` directory:

- `TKKG1/` - Documentation for "Jennifer is Missing"
- `TKKG2/` - Documentation for "Deadly Chocolate"
- And so on through TKKG14 and the Identikit tool

Check these folders for the specific documentation corresponding to each game you're playing.

## System Requirements

**Host System Requirements:**

- **macOS 10.15 or later** (for UTM compatibility)
- **Apple Silicon or Intel processor** with virtualization support
- **At least 4 GB RAM** (2 GB for your system + 256 MB for the VM)
- **Several GB of free disk space** (each game is 100+ MB, plus VM overhead)

**Virtual Machine Specifications:**

- **PowerPC emulation** (handled automatically by UTM)
- **256 MB RAM allocated to VM** (sufficient for Mac OS 9 and games)
- **IDE CD-ROM drive emulation** for game disc access

## Troubleshooting

### "IDE unit 0 is in use" Error

This error occurs when UTM detects a conflict in the virtual hardware configuration, typically when drive interfaces aren't properly updated after configuration changes.

**Solution:**

1. **Go to VM settings** in UTM
2. **Check each configured drive** (including the system drive and your game drive)
3. **Look for "Update Interface" buttons** on each drive configuration
4. **Click "Update Interface"** wherever this button appears
5. **Save configuration and try starting the VM again**

> [!TIP]
> This error often appears after adding or changing virtual drives. The "Update Interface" button refreshes the virtual hardware configuration to resolve conflicts.

### Game Drive Not Appearing

**Possible causes and solutions:**

- **Incorrect file format:** Ensure the game file has a `.cdr` or `.iso` extension
- **Interface misconfiguration:** Verify the drive is configured as IDE interface
- **VM restart needed:** Try restarting the virtual machine
- **Corrupted extraction:** Re-extract the game from the original `.sit` file
- **File path issues:** Make sure the game file path doesn't contain special characters

### Performance Issues

If games run slowly or audio stutters:

- **Allocate more RAM** to the VM (try 512 MB instead of 256 MB)
- **Close unnecessary applications** on your host Mac
- **Check Activity Monitor** for high CPU usage from other processes

---

## Accessing Game Data (For Developers)

This section is intended for developers, researchers, or enthusiasts interested in examining the original game files, extracting assets, or understanding the game's internal structure. By mounting the disc images on a modern system, you can access all the original game data without needing to run the actual games.

> [!WARNING]  
> The following procedures involve mounting disc images and require administrative privileges. Ensure you understand the commands before executing them.

### Mounting Game Images

The TKKG games are distributed as disc images (`.cdr` or `.iso` files) that contain the complete game data as it appeared on the original CDs. To access this data on modern systems, they need to be mounted to a virtual drive.

First, create a directory, where the game data will be mounted.

```bash
mkdir -p ~/TKKG1
```

Next, use the `hdiutil` command to attach the disc image and mount it. This command will create a virtual drive that you can access like any other disk on your system. In this example, we'll mount the first TKKG game located at `~/Downloads/TKKG1.cdr`.

> [!TIP]  
> Replace the path in the example with the actual path to your extracted game files. The file extension might be `.iso` instead of `.cdr` depending on the game you picked.

```bash
# Attach the disc image
DEVICE=$(hdiutil attach ~/Downloads/TKKG1.cdr -nomount | head -1 | awk '{print $1}')

# Mount using the assigned device
sudo mount -t cd9660 $DEVICE ~/TKKG1
```

> [!NOTE]  
> The `head -1` command ensures we only get the first device name (the main disk), not the individual partitions that might also be listed.

#### Unmounting After Use

When you're finished accessing the game data, properly unmount the images:

```bash
sudo umount ~/TKKG1
hdiutil detach $DEVICE
```
