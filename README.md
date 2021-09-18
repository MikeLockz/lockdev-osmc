# lockdev-osmc

Instructions for fresh install of OSMC, RetroArch, IAGL, Bluetooth controller, VNC

## Install OSMC
1. Flash OSMC to sd card
1. Boot up Pi
1. Follow OSMC install instructions
1. Get IP address of install
1. SSH like `ssh osmc@192.168.0.xxx` - password is `osmc`

## Install VNC
1. [Install VNC](https://discourse.osmc.tv/t/howto-install-a-vnc-server-on-the-raspberry-pi-currently-not-working-on-the-pi-4/1517)
1. Change video setting in `sudo nano config.txt`
1. Prepend `f` to kms like `dtoverlay=vc4-fkms-v3d,cma-512` and save file
1. Reboot pi `sudo reboot now`
1. Will need to connect via VNC like `192.168.0.xxx:5900`

## Add more packages to get installed
1. sudo apt update
1. deb http://ftp.debian.org/debian/ buster-updates main contrib non-free
1. Save and exit
1. sudo apt update

## Disable gpg validation
1. sudo nano /etc/apt/apt.conf.d/99allow_unauth
1. APT { Get { AllowUnauthenticated "1"; }; };
1. sudo reboot now

## Install xpadneo bluetooth controller drivers
1. `sudo apt-get install dkms rbp464-headers-`uname -r` (rpi 4)
1. `sudo ln -s "/usr/src/rbp464-headers-`uname -r`" "/lib/modules/`uname -r`/build"`
1. https://github.com/atar-axis/xpadneo

## Setup emulator
1. https://www.reddit.com/r/RetroArch/comments/l158qt/best_performing_retroarch_build_on_a_raspberry_pi/
