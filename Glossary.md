# List of Definitons and Terms of commands

##iwctl## – interactive Wi-Fi control tool (from iwd).

device list – list Wi-Fi devices (e.g., wlan0)

station wlan0 scan – scan for networks

station wlan0 get-networks – show discovered SSIDs

station wlan0 connect "SSID" – connect to a network

ping -c 3 host – send 3 ICMP echo requests to test reachability.

1.1.1.1 tests raw connectivity; archlinux.org tests DNS.

timedatectl set-ntp true – enable NTP time sync.

fdisk /dev/nvme0n1 – partition disk (interactive).

g create GPT, n new partition, t type, w write.

mkfs.fat -F32 /dev/nvme0n1p1 – make FAT32 filesystem (EFI).

-F32 → FAT32
    -FAT32 is a widely compatible storage format used on storage devices like USB drives, memory cards, etc.

mkfs.ext4 /dev/nvme0n1p2 – make ext4 filesystem for root.

mkswap /dev/... / swapon – create/enable swap (optional).

mount SRC DST – mount filesystem at directory.
mkdir -p /mnt/boot – create directory (with parents).
umount -R /mnt – unmount recursively (all submounts).

pacstrap -K /mnt pkg… – install packages into /mnt.

-K – copy host’s pacman keyring.

genfstab -U /mnt >> /mnt/etc/fstab – generate fstab using UUIDs and append.

arch-chroot /mnt – change root into installed system.

ln -sf A B – create/update symlink; -s symbolic, -f force.

hwclock --systohc – write system time to hardware clock.

locale-gen – generate locales per /etc/locale.gen.

bootctl install – install systemd-boot into EFI.

blkid /dev/... – show block device IDs (UUID/PARTUUID).

PARTUUID – the partition’s GUID; stable across reformat.

nano FILE – simple terminal editor.

Save: Ctrl+O, Enter; Exit: Ctrl+X.

pacman – Arch package manager.

-S – sync/install packages from repos

-Sy – refresh package databases

-Syu – refresh + upgrade all packages

-Syyu – force double refresh + upgrade (use if mirrors break)

-Rns – remove package + dependencies + configs

-Qs – search installed packages

-Ss – search in repos

sudo – run a single command with root privileges.

Uses /etc/sudoers (edit with visudo).

useradd -m -G wheel -s /bin/bash NAME – create user.

-m make home dir, -G groups, -s shell.

passwd – set a password.

visudo – safely edit sudoers file.

Enable: %wheel ALL=(ALL) ALL.

systemctl – manage services (systemd).

enable – start at boot

start – start now

enable --now – both (only on a real booted system, not chroot)

disable --now – stop and disable

status NAME – show service status

ufw – uncomplicated firewall.

enable – turn firewall on

status verbose – show rules & state

default deny incoming – block unsolicited inbound

default allow outgoing – allow outbound

auditd – Linux audit daemon (service name).
rkhunter --check – scan for rootkits.
freshclam – update ClamAV virus definitions.
clamscan -r PATH – recursive scan.

reflector … --save /etc/pacman.d/mirrorlist – write a refreshed mirrorlist.

sddm – display manager (login screen) for KDE.

Enable with systemctl enable --now sddm.

pipewire, wireplumber – modern audio server + session manager.
bluedevil – KDE Bluetooth integration.

cat FileName – print file contents to stdout.
echo Text | tee FILE – write TEXT to FILE (with sudo).

Kitty config - ~/.config/kitty/kitty.conf

background_opacity 0.85 - transparency

background - background color