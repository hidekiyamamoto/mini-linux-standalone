This is the home of standalone.io

standalone.io is a small debian linux live distro project.

It's based on ubuntu mini remix and it comes in different flavors:
All of the standalone.io iso are made to live boot, automatically login and then load
a script in the usb key itself, that can be customized without remastering the iso.
The only thing that differs between the flavors is the set of preinstalled packages.
we will soon publish a website where authenticated users can freely generate one iso per week....

standalone-headless - the most basic standalone.io iso
standalone-headless-ssmtp - preinstalled mail sending functionality
standalone-gui 490Mb [ssmtp fluxbox virtualbox-qt]

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
11 Create a new machineboot.txt file in the root of the usb key.
12 FINISH - you can boot a machine with the key and have your easily customizable script run at startup.



