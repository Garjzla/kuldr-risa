# kuldr-risa
This script is used to install the Pantheon Desktop Environment on arch linux

arget.txt installs stable packages on Arch, while IVM.txt installs the latest release on Arch.
I've found that on some computers, the stable version has errors concerning "conflicting files",
so you should probably install with IVM( Install Via Medium.com/@helder.bertoldo script (url below) ) if these errors appear. 

# References

https://wiki.archlinux.org/index.php/Pantheon

https://medium.com/@helder.bertoldo/arch-linux-e-pantheon-combina%C3%A7%C3%A3o-perfeita-ca8f5945ae

# How to Run.txt
------------------------------------------------------------------------------------------------------------------------------------

First, install yay

$ sudo pacman -S git

$ git clone https://aur.archlinux.org/yay.git

$ cd yay

$ makepkg -si

-------------------------------------------------------------------------------------------------------------------------------------

Download the scripts

$ git clone https://github.com/Du-Brisingr-Arget/kuldr-risa.git

-------------------------------------------------------------------------------------------------------------------------------------

Then, run either

$ bash install.txt

or

$ sh install.txt

in the kuldr-risa directory

--------------------------------------------------------------------------------------------------------------------------------------

Configure Pantheon via switchboard and its plugs (switchboard-plug-*), which must be installed separately. 

Not all of gnome-control-center's settings panels have been ported. 

In addition, except plank, all the Pantheon components store their configuration in the org.pantheon or io.elementary gsettings keys, which can be edited with dconf-editor.

< from the Arch Wiki >

----------------------------------------------------------------------------------------------------------------------------------------

Terminal Opacity

To make pantheon-terminal (semi-)transparent, set the dconf key org.pantheon.terminal.settings.opacity to your desired opacity

< from the Arch Wiki >

----------------------------------------------------------------------------------------------------------------------------------------

config display manager

$ sudo nano /etc/lightdm/lightdm.conf

Find the following line:

#greeter-session=example-gtk-gnome

And, uncomment and change it as shown below.

greeter-session=lightdm-pantheon-greeter

Then, start and enable lightdm login manager to start at boot as shown below.

$ sudo systemctl start lightdm.service

$ sudo systemctl enable lightdm.service

----------------------------------------------------------------------------------------------------------------------------------------

# etc
Also, use this tool to clone VHDs to physical disks and vice versa

https://www.easeus.com/partition-master/vhd-to-physical-disk.html


And read this to install Arch linux on a usb

http://valleycat.org/linux/arch-usb.html

Also, I found this helpful when accessing clouds on my arch.

https://rclone.org/
