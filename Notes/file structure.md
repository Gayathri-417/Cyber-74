
## Linux File System Structure Explained

> The Root Directory (/)

Everything in Linux starts from root (/).

/
├── bin -> usr/bin        # Essential command binaries
├── boot                  # Boot loader files (kernel, initrd)
├── dev                   # Device files
├── etc                   # Configuration files
├── home                  # User home directories
├── lib -> usr/lib        # Essential shared libraries
├── media                 # Mount points for removable media
├── mnt                   # Mount points for temporary filesystems
├── opt                   # Optional/add-on software
├── proc                  # Virtual filesystem for process info
├── root                  # Root user's home directory
├── sbin -> usr/sbin      # System administration binaries
├── tmp                   # Temporary files
├── usr                   # User programs and data
└── var                   # Variable data (logs, spool files)

## Detailed Breakdown of Important Directories

> /bin and /sbin - Essential Programs

ls /bin    # See basic commands (ls, cp, mv, cat)
ls /sbin   # See system commands (fdisk, ifconfig, reboot)
 View system administration commands
ls -la /sbin
 Commands like:
which fdisk              # Find partition tool
which ifconfig           # Network config (deprecated)
which ip                 # Modern network tool

> /boot

Contains files required to boot Linux.

Includes:

Kernel

Bootloader files

Linux commonly uses
GNU GRUB
to start the system.

 View boot-related files (might need sudo)
ls -la /boot
Check the kernel version
uname -r
 View kernel image
file /boot/vmlinuz-*

> /dev - Device Files

Contains device files.

Represents hardware as files.

Examples:

Hard disk
USB
Keyboard

 Explore device files
ls -la /dev
 Check specific devices
ls -la /dev/sda*        # Hard disk partitions
ls -la /dev/tty*        # Terminal devices
ls -la /dev/null        # The null device
 Test null device
echo "Hello" > /dev/null
cat /dev/null

> /etc - Configuration Files

A configuration file is a file that:

Stores system settings

Controls how programs run

Defines rules and options

Is usually a text file

It does NOT contain program code.
It contains instructions/settings for programs.

 Navigate to etc
cd /etc
 View important config files
head -5 passwd           # First 5 lines of user database
head -5 group            # Group information
cat hostname             # System name
cat hosts                # Hostname mappings
 List all config files
ls -la *.conf            # All config files

> /home - User Directories

Contains user personal files.

Each user gets their own folder.

Example:

/home/gayathri

Used for:
Documents
Downloads
Desktop files
Projects

 Go to home
cd /home
 List all users
ls -la
 Go to your home
cd ~
pwd                      # Shows /home/yourusername
 Create your project
mkdir -p ~/prjct
cd ~/prjct
pwd                      # Shows /home/yourusername/prjct

> /lib - Libraries

/lib contains essential shared libraries required for:

System booting

Running important commands in /bin and /sbin

These libraries are required by the kernel and basic system programs.

A library is a collection of pre-written code that programs use.

Instead of writing everything from scratch, programs use libraries.

 View shared libraries
ls -la /lib
 Check important libraries
ls -la /lib/*.so* | head -10  # First 10 shared objects

> /media & /mnt - Mount Points

In Linux, mounting means:

Attaching a storage device (USB, HDD, CD, etc.) to the Linux file system so you can access its files.

Linux does not use drive letters like Windows (C:, D:).
Everything is attached inside the root / directory.

/mnt is used for temporary manual mounting by system administrators.

 Mostly used when you mount something using the mount command manually.

 sudo mount /dev/sdb1 /mnt
  /dev/sdb1 → device
 /mnt → mount location

 ls /mnt                  # Often empty, used for temporary mounts
 mount | head -5          # See what's actually mounted

 /media – Automatic Mount Point

 /media is used for automatically mounted removable devices.

When you insert:

USB drive
External hard disk
CD/DVD

Linux automatically mounts it inside /media.

Example:

/media/gayathri/USB_DRIVE

This is handled by the system automatically.

ls /media                # Usually empty until you plug in USB

> /opt - Optional Software

 Check for installed optional software
ls /opt
 Many third-party applications install here

> /proc - Process Information

  /proc is a virtual filesystem created and managed by the Linux kernel.

  What is a Virtual Filesystem?

It looks like normal files and directories.

But the data is generated dynamically in memory (RAM) by the kernel.

Nothing is permanently stored there.

 Explore proc filesystem
ls /proc
 Check CPU info
cat /proc/cpuinfo | head -10
 Check memory
cat /proc/meminfo | head -10
 Check processes
ls /proc/$$              # Current shell process
cat /proc/$$/status      # Status of current shell

> /root - Root's Home

 /root is the home directory of the root user (superuser) in Linux.

It is different from /.

Root has:

Full permissions
Can modify any file
Can install/remove software
Can manage users
Can control system settings

 Try to view root's home (needs sudo)
sudo ls -la /root        # Will ask for password
