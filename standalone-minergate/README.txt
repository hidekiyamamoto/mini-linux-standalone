#If you have doubts read documentation about how to create the MAKER MACHINE or MAKER ENVIRONMENT - btw it's a basic lubuntu 16.04, plus customizer-gui installed
#Instructions to make a MAKER UNIT are here https://github.com/hidekiyamamoto/standalone.io/blob/master/standalone-make-scripts/unitmaker.txt

#1 - Using customizer-gui in a maker unit you already prepared, start choosing the iso of UBUNTU MINI REMIX - I used 16.4 AMD64
# - Wait for unpacking then click TERMINAL and paste in one move what follows.

sudo apt-get update &&
sudo apt-get  -y install software-properties-common &&
sudo add-apt-repository "deb http://us.archive.ubuntu.com/ubuntu/ $(lsb_release -sc) universe multiverse" &&
sudo add-apt-repository "deb http://us.archive.ubuntu.com/ubuntu/ $(lsb_release -sc)-updates universe multiverse" &&
sudo apt-get update &&
sudo apt-get -y install ssmtp xorg fluxbox libproxy-tools network-manager-gnome firmware-b43-installer b43-fwcutter &&
sed -i -e 's/agetty --noclear/agetty -a root --noclear/g' /lib/systemd/system/getty@.service &&
echo -e "if [[ -z \$DISPLAY ]] && [[ \$(tty) = /dev/tty1 ]]; then" >> /root/.profile &&
echo -e "cp -r /etc/skel/.fluxbox /root" >> /root/.profile &&
echo -e "sed -i -e 's/# idesk/xterm -hold -e \/media\/cdrom\/machineboot.txt/g' /root/.fluxbox/startup"  >> /root/.profile &&
echo -e "  exec startx" >> /root/.profile &&
echo -e "fi" >> /root/.profile &&
echo -e "if [[ -z \$DISPLAY ]] && [[ \$(tty) = /dev/tty1 ]]; then" >> /etc/skel/.profile &&
echo -e "sed -i -e 's/# idesk/xterm -hold -e \/media\/cdrom\/machineboot.txt/g' /etc/skel/.fluxbox/startup"  >> /etc/skel/.profile &&
echo -e "  exec startx" >> /etc/skel/.profile &&
echo -e "fi" >> /etc/skel/.profile &&
exit

#2 - IMPORTANT!!!! NOW CLICK "DESKTOP" AT LEAST ONCE, then RIGHT CLICK IN THE DESKTOP -> EXIT

#3 - Download both minergate.deb and minergate-cli-release.deb from minergate website
#4 - For the two of them click "INSTALL DEB" in customizer-gui
#5 - Click REBUILD ISO and wait you should obtain an iso of about 500Mb
#6 - Using your favourite tool, burn the resulting iso to usb disk 
#7 - copy the four files machineboot.txt autoshut.txt wifi.txt and miner.txt to the root of the usb key
#8 - customize the username in miner.txt so that it will mine for you and not for me.
#END - NOW YOU CAN BOOT A CONNECTED PC WITH THIS USBKEY AND IT WILL MINE
# If you need wifi you have 20 secs to enter the password in the wifi applet before the miner starts automatically
# You can optionally start a shell (with right click menu) and type the following line to have the minergate gui popup
# minergate ENTER

----------------------------------------------------------------------------------------------

edit miner.txt to change the mined currency and the username
edit autoshut.txt to change the number of minutes for autoshutdown; 1440=24h
edit machineboot and remove the parentesis with autoshut to disable the automatic shutdown
