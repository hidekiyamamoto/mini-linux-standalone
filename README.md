# standalone.io
ultra easily customizable - minimal linux distro for very easy automation experiments
and a LIVE DISTRO TO AUTOMATICALLY CREATE CUSTOMIZED LIVE DISTROS - with recipes :-)

It's based on ubuntu-mini-remix and it comes in different flavors:
All of the standalone.io iso are made to live boot, automatically login and then load
a script in the usb key itself, that can be customized without remastering the iso.

All the standalone.io iso , compared to ubuntu-mini-remix, have the following packages installed.
software-properties-common and ssmtp installed, plus the universe repo has been enabed.

The only thing that differs between the flavors is the set of preinstalled packages.
we will soon publish a website where authenticated users can freely generate one iso per week....
When gui is present in the flavor, it means xorg and fluxbox have been installed, and preconfigured
to launch automatically, the customizable boot script will run inside an xterm in the fluxbox shell.

- standalone.io : our most basic iso.
- standalone-nodejs : live nodejs http server.
- standalone-gui : live fluxbox.

----

#Examples

With standalone-gui + only virtualbox-qt package preinstalled I can have at my client a vmhost machine os being totally live, that means incorruptible, if i burn it on a disc for example. The boot script will try and start the machines, if an error is encounter (for example the disks are new and the machines have not been imported, or the machine is unable to start) it will move the machine folder to some dump storage and reimport the last backupped ova from a network drive, notifying via mail the fact, and try start it again... then when appropriate I run a task that tests the operability of services in the virtual machines i am am using, then shut them down and backup a new ova...
Customizing the sending account and smtp, the network path for the ovas and everything else COULDN't BE EASIER, as they are free text files in the root of the usb.


With standalone+nodejs I can have a live distro that will automatically boot and run a nodejs server file that I can modify as easily as modifing a file in the root of the usb key.


Basically when I need to make a test about some creative device, that is expected to behave exaclty the same every time it is booted.
For example i made a distro with preinstalled leap motion drivers and that would launch chromium in kiosk mode to a given url, with leap motion websocket activated.

----

Make your own :  in the meanwhile here is the procedure:
1 have a fairly clear _buntu matching the version you want to master live INSTALLED in some partition
  boot it and do the following:
2 download ubuntu mini remix
3 apt-get install customizer
4 sudo customizer-gui
5 Select iso and choose the ubuntu mini remix iso
6 upon completion click terminal and copy paste your version of the MAKESTANDALONE script and press ENTER
7 upon completion close terminal typing exit
8 IF desktop button is enabled click it, wait for the fluxbox desktop, then rightclick and exit
9 Click rebuild ISO
10 Using a tool like UUI master the iso in some usb key
11 Create a new machineboot.txt file in the root of the usb key. (this will be executed automatically)
12 FINISH - you can boot a machine with the key and have your easily customizable script run at startup.
