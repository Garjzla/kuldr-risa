# kuldr-risa
This script is used to install the Pantheon Desktop Environment on arch linux

arget.txt installs stable packages on Arch, while IVM.txt installs the latest release on Arch.
I've found that on some computers, the stable version has errors concerning "conflicting files",
so you should probably install with IVM( Install Via Medium.com/@helder.bertoldo's script (url below) ) if these errors appear. 

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

LightDM: Configuring the Login Manager

The login manager after it has been installed, needs a little adjustment, which is to add the elementary default Greeter (theme). To do this make sure you have installed the lightdm(without the -git extension) and the lightdm-pantheon-greeter-git .

Check available greeters

ls -1 /usr/share/xgreeters

Available Greteers

Elementary greeter should appear listed, if it is not, reinstall the package lightdm-pantheon-greeter-git

Changing the default Lightdm theme

Open the file /etc/lightdm/lightdm.conf

sudo nano /etc/lightdm/lightdm.conf

Locate the line #greeter-session=located in the session (next to line 108)

Note: It will only work if you exactly change the session session greeter-session!
Uncomment the line by removing the # character and assign the greeter elementary by default.

greeter-session = io.elementary.greeter 

Save and close the editor.

Note: You can edit the theme settings, such as wallpaper, the behavior of the num-lock key, among others, through the file

/etc/lightdm/io.elementary.greeter.conf

< from medium.com/@helder.bertoldo >

----------------------------------------------------------------------------------------------------------------------------------------

# install Pantheon theme icons
install Urutau icons

$ yay -S urutau-icons-git

$ gsettings set org.gnome.desktop.interface icon-theme "urutau-icons"

# etc
Also, use this tool to clone VHDs to physical disks and vice versa

https://www.easeus.com/partition-master/vhd-to-physical-disk.html


And read this to install Arch linux on a usb

http://valleycat.org/linux/arch-usb.html

Also, I found this helpful when accessing clouds on my arch.

https://rclone.org/
