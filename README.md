I grew tired of having to randomly follow different guides (and possibly have to re-work my install): to setup Arch my normal way, so instead I figured I'd create this somewhat useful guide.

I'm not going into full detail of the steps performed, as they're listed on the guides referenced.

After this guide is complete, Arch with KDE Plasma for a DE will be setup!

This guide assumes you're installing from a USB Key.

**NOTE**: Following this guide WILL overwrite all MicroSD and Hard Drive contents.

![YOU HAVE BEEN WARNED gif](https://github.com/infinitechris/PineBookProArchSetup/assets/5414345/17a89e89-1f0a-4a6a-9a00-df8bdf4413ec)

Moving on.

- [ ] [How to Install Arch Linux - Step by Step Guide](https://itsfoss.com/install-arch-linux/)
- [ ] [How to Properly Install and Setup KDE Plasma on Arch Linux](https://itsfoss.com/install-kde-arch-linux/)
     - I prefer this DE for my use case
- [ ] How to install broadcom-wl (I need to find a guide for this)
- [ ] Any other guides used

## Prerequisites
- I prefer `axel` to `wget`, and I will be referencing it instead of `wget` in scripts. 
 - a USB card to install Arch onto (naturally) at least 8GB in size
 - Internet access

# USB Stick Setup
 - I am experimenting with [Headless SSH install of Arch](https://wiki.archlinux.org/title/Install_Arch_Linux_via_SSH#Prepare_cloud-init_configuration_files) to see if this alleviates most if not all of the manual entry on target machine
      - [Usb flash guide](https://wiki.archlinux.org/title/USB_flash_installation_medium#Using_the_ISO_as_is_(BIOS_and_UEFI)) used to make bootable usb disk
      - [iwctl](https://wiki.archlinux.org/title/Iwd#iwctl) on target machine will still need to be setup network access :(
           - Still needed to enter password to connect :( :(
      - `passwd` to set `root` password as not empty to allow SSH access
      - `os-prober error`: If you get the following error while configuring `grub`, you will need to resolve it for the system to be bootable

       grub-mkconfig -o /boot/grub/grub.cfg
       Generating grub configuration file ...
       Found linux image: /boot/vmlinuz-linux
       Found initrd image: /boot/initramfs-linux.img
       Found fallback initrd image(s) in /boot:  initramfs-linux-fallback.img
       Warning: os-prober will not be executed to detect other bootable partitions.
       Systems on them will not be added to the GRUB boot configuration.
       Check GRUB_DISABLE_OS_PROBER documentation entry.
       Adding boot menu entry for UEFI Firmware Settings ...
       done
     - You will need to edit `grub` config with `nano`

           nano /etc/default/grub
     - Press CTRL+W to find the line containing `#GRUB_DISABLE_OS_PROBER=false` and uncomment
     - Save this file and exit
     - re-run `grub-mkconfig -o /boot/grub/grub.cfg` again to resolve
     - I opt for just `X11` instead of `wayland-session` due to lack of comaptability with `VNC`

           pacman -S xorg plasma kde-applications
     - 30 is the `tesseract-eng` version
     - More TK
