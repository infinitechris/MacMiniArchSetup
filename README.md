I grew tired of having to randomly follow different guides (and possibly have to re-work my install): to setup Arch my normal way, so instead I figured I'd create this somewhat useful guide.

I'm not going into full detail of the steps performed, as they're listed on the guides referenced.

After this guide is complete, Arch with KDE Plasma for a DE will be setup!

This guide assumes you're installing from a USB Key.

**NOTE**: Following this guide WILL overwrite all MicroSD and Hard Drive contents.

![YOU HAVE BEEN WARNED gif](https://github.com/infinitechris/PineBookProArchSetup/assets/5414345/17a89e89-1f0a-4a6a-9a00-df8bdf4413ec)

Moving on.

- [ ] [How to Install Arch Linux [Step by Step Guide]] (https://itsfoss.com/install-arch-linux/)
- [ ] [How to Properly Install and Setup KDE Plasma on Arch Linux](https://itsfoss.com/install-kde-arch-linux/)
     - I prefer this DE for my use case
- [ ] How to install broadcom-wl (I need to find a guide for this)
- [ ] 

## Prerequisites
- I prefer `axel` to `wget`, and I will be referencing it instead of `wget` in scripts. 
 - a USB card to install Arch onto (naturally) at least 8GB in size
 - Internet access

# USB Stick Setup
 - I am experimenting with [Headless SSH install of Arch](https://wiki.archlinux.org/title/Install_Arch_Linux_via_SSH#Prepare_cloud-init_configuration_files) to see if this alleviates most if not all of the manual entry on target machine
      - iwctl on target machine will still need to be setup network access :(
      - More TK
