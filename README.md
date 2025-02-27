# KDE/Windows---For-Noobs

### Why? 
Used KDE Neon, means we get a modern DE with a Ubuntu base (Debian) and also wayland & x11 enabled. 

All you need is 2 drives, 1 usb and any kind of hardware really. 
Make sure you have the windows install already done on one drive. You can also use this to format the other drive easily. 
Go to search menu > Create and format disk partitions or type in console: `diskmgmt.msc`

For the drives you have to make sure they are formated in a linux compatible format (ext4, XFS, and Btrfs). 

---
### Start
Flash the USB with Etcher, Rufus or Similar tool
Open boot options (f12, del, etc) > Boot from USB

If you're using old hardware and have early USB prot, this will take a while (basically copying/prep the whole ISO).
Also make sure to use motherboard ports directly as it's more likely to actually detect the media. 

![load-34_128](https://github.com/user-attachments/assets/a5d39ff6-4dd3-4dca-b1c4-c2322579d2a5)
 
This can take up to 30mins to an hour. You don' thave to worry as it's installing a lot of necessary libraries and preparing it for the next steps.
Hence, why once you're in, the rest will be quick. This is a "live image" meaning you actually already have a lot of utilities included.   

Let the installer do it's thing. It might reset your screen a couple of times (or change resolutions). 
It might also stop spinning totally at the very end, again just be patient.

Once you're in the desktop, in the launch menu: Click Install System
Let it load. 

**Make sure to install on the right target drive.**

(I like to keep a windows install on a seperate disk) 
If you're not sure: `lsblk`
If it's not in the list the drive is not formatted in the right format. 

**Reboot but make sure to remove the USB and boot from the drive we just installed on.** 

Note:
On even older hardware you might have to set the Sata to AHCI instead of RST. Issue is that if you cmos battery is dead every power-out this setting will be default... 
It will also most likely break everything. 
So make sure to change this before installing any OS if available. 

---

### When the installer is done. 

It has created your file system, password, etc
This means you can reboot and remove the USB.
There should be a screen that says "Please remove the installation medium , then press ENTER:" 

Remove it, if your enter key doesn't work you can hard shutdown. 

Now go back to BIOS settings: 
Change to boot from the KDE Neon drive. 

What is cool is that KDE includes a friendly boot manager that can preserve the W11/W10 install and show it to us whenever we start the machine. 

---

Now we can start making the system our own. 
First we need to connect to update. So we if you're using a cable and it's old hardware again you might have to check it's properly plugged in and click bottom right network > Configure network Connections

Then add, generate a random mac adress and toggle automatic connection. If it doesnt work try deleting the device and creating it again.  
Now there should be a little update icon in the bottom right. Click it and click update all. 

Reboot again.

Now depending on your hardware you might need to jump some hoops. For me it's a Nvidia card so I will install their drivers. 

---
### NVIDIA GPUS
In the log-out screen you can find a small switch to x11.

Then since this is based on Ubuntu it will make our lives easier: `ubuntu-drivers devices`
This will give you a recommended version for your hardware.  

Then `sudo apt install nvidia-driver-XXX`
This might ask you to enroll a key. 

Set a 8 char password. 
**(Careful bios is bad at language input default is often US)**

Once this is done reboot.
This should directly make you enroll your MOK key. 

Press ENROLL, then continue, then yes, then pw, then reboot again. 

---

Now we are in x11 with Nvidia support :)
You can check it works with the Nvidia settings pannel which should show your GPU - 0, if you have an integrated graphics card aswell you might needs a few extra steps to make sure it uses the right one. 

We can also check using `nvidia-smi`.

---
### AMD GPUS
But the process would just be easier with AMD and functional almost instantly as it's integrated by default into kde with AMDGPU. 
The only thing you might need `sudo apt install mesa-utils` to get full compatibility. 

---

Now you're all good to go for dev, gaming, whatever it is. 
For FireFox I recommend getting AdGuard and Plasma Integration so that it works perfectly with media. This also means most systems will work out of the box with keyboard keys to play/pause, volume, etc


---

### Results 
![Untitled](https://github.com/user-attachments/assets/c79aa5f3-61c2-4aae-afaf-5ef1932e6507)

Now you can use both systems freely whenever you start the machine. Simple up and down pick. 

The grub command line tool let's you add more if you ever decided to hop. 


---

### Updates

KDE has a neat manager that can do most of the work for you. 
What I recommend doing is install all then select action > Restart

This will make sure get you to get to a applying updates screen. I don't know why not enabled by default. 

See full guide here: [Full Guide](https://github.com/h8d13/LSK---Linux-Starter-Kit)
