# KDE---For-Noobs

### Why? 
Used KDE Neon, means we get a modern DE with a Ubuntu base (Debian) and also wayland & x11 enabled. 

Flash the USB with Etcher, Rufus or Similar tool
Open boot options (f12, del, etc) > Boot from USB

If you're using old hardware and have early USB prot, this will take a while (basically copying/prep the whole ISO).

![load-34_128](https://github.com/user-attachments/assets/a5d39ff6-4dd3-4dca-b1c4-c2322579d2a5)
 
This can take up to 30mins to an hour. you don' thave to worry as it's installing a lot of necessary libraries and preparing it for the next steps.
Hence, why once you're in the rest will be quick.   

Let the installer do it's thing. 
Once you're in the desktop, Click install KDE

Make sure to install on the right target drive. (I like to keep a windows install on a seperate disk) 
If you're not sure: `lsblk`

Reboot but make sure to remove the USB and boot from the drive we just installed on. 

Note:
On even older hardware you might have to set the Sata to AHCI instead of RST. Issue is that if you cmos battery is dead every power-out this setting will be default... 
It will also most likely break everything. 
So make sure to change this before installing any OS if available. 

For the drives you have to make sure they are formated in a linux compatible format (ext4, XFS, and Btrfs). 


