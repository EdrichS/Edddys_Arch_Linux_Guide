# List of Definitons and Terms of commands

### **arch-chroot /mnt**
- change root into installed system.

### **auditd**
- Linux audit daemon (service name).

### **blkid /dev/...**
- show block device IDs (UUID/PARTUUID).  
- **PARTUUID**: the partition’s GUID; stable across reformat.

### **bluedevil**
- KDE Bluetooth integration.

### **bootctl install**
- install systemd-boot into EFI.

### **cat FileName**
- print file contents to stdout.

### **clamscan -r PATH**
- recursive scan.

### **device list**
- list Wi-Fi devices (e.g., wlan0).

### **echo Text | tee FILE**
- write TEXT to FILE (with sudo).

### **fdisk /dev/nvme0n1**
- partition disk (interactive).  
- **g** create GPT, **n** new partition, **t** type, **w** write.

### **freshclam**
- update ClamAV virus definitions.

### **genfstab -U /mnt >> /mnt/etc/fstab**
- generate fstab using UUIDs and append.

### **hwclock --systohc**
- write system time to hardware clock.

### **iwctl**
- interactive Wi-Fi control tool (from iwd).

### **ln -sf A B**
- create/update symlink; -s symbolic, -f force.

### **locale-gen**
- generate locales per /etc/locale.gen.

### **mkfs.ext4 /dev/nvme0n1p2**
- make ext4 filesystem for root.

### **mkfs.fat -F32 /dev/nvme0n1p1**
- make FAT32 filesystem (EFI).  
- -F32 == FAT32  
- **FAT32** is a widely compatible storage format used on storage devices like USB drives, memory cards, etc.

### **mkdir -p /mnt/boot**
- create directory (with parents).

### **mount SRC DST**
- mount filesystem at directory.

### **nano FILE**
- simple terminal editor.  
- **Save** = Ctrl+O then Enter
- **Exit** = Ctrl+X.

### **pacman**
- Arch package manager.  
  - **-S** = sync/install packages from repos  
  - **-Sy** = refresh package databases  
  - **-Syu** = refresh + upgrade all packages  
  - **-Syyu** = force double refresh + upgrade (use if mirrors break)  
  - **-Rns** = remove package + dependencies + configs  
  - **-Qs** = search installed packages  
  - **-Ss** = search in repos

### **pacstrap -K /mnt pkg…**
- install packages into /mnt.  
- **-K** = copy host’s pacman keyring.

### **passwd**
- set a password.

### **ping -c 3 archlinux.org**
- **ping** = sends ICMP echo requests to test reachability and connection.
- **-c 3** = c means count , 3 sends exactly 3 pings; without -c, ping will keep running until manually stopped  
- **archlinux.org** is the target host we're pinging.

### **pipewire, wireplumber**
- modern audio server + session manager.

### **reflector … --save /etc/pacman.d/mirrorlist**
- write a refreshed mirrorlist.

### **rkhunter --check**
- scan for rootkits.

### **sddm**
- display manager (login screen) for KDE.  
- Enable with **systemctl enable --now sddm**.

### **station wlan0 connect "SSID"**
- connect to a network.

### **station wlan0 get-networks**
- show discovered SSIDs.

### **station wlan0 scan**
- scan for networks.

### **sudo**
- run a single command with root privileges.  
- Uses **/etc/sudoers** (edit with visudo).

### **systemctl**
- manage services (systemd).  
  - **enable** = start at boot  
  - **start** = start now  
  - **enable --now** = both (only on a real booted system, not chroot)  
  - **disable --now** = stop and disable  
  - **status NAME** = show service status

### **timedatectl set-ntp true**
- enable NTP time sync.

### **ufw**
- uncomplicated firewall.  
  - **enable** = turn firewall on  
  - **status verbose** = show rules & state  
  - **default deny incoming** = block unsolicited inbound  
  - **default allow outgoing** = allow outbound

### **umount -R /mnt**
- unmount recursively (all submounts).

### **useradd -m -G wheel -s /bin/bash NAME**
- **useradd** = creates new user  
- **-m** = makes the newly made user a home directory
- **-G wheel** = adds the newly made user to the wheel group
- **-s** = sets the newly made user's login shell 
- **/bin/bash** = specifies that the newly made user uses bash when logging in
- **NAME** = the name of the newly made user. This can be changed to whatever you want