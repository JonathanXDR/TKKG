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
DEVICE=$(hdiutil attach ~/Downloads/TKKG1.cdr -nomount -imagekey diskimage-class=CRawDiskImage | head -1 | awk '{print $1}')

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
