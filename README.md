# Script for the Agon 1 case adapted for Ubuntu 20.04

## Description

The argon one case is a solid case for the Raspberry Pi 4
(see https://www.argon40.com/argon-one-raspberry-pi-4-case.html)

This script has been adapted from https://download.argon40.com/argon1.sh which is
designed to work with Raspbian (Raspberry OS), to work with Ubuntu 20.04.

There are mainly three changes compared to the original:
1. need to use python3 everywhere since python2 support for GPIO has been nuked
   in Ubuntu 20.04.
2. reading the temperature cannot be done using vcgencmd, but we can use the sysfs
   instead
3. the list of packages on which the script depends has been adapted to Ubuntu 20.04

## Install 

```bash
cd /tmp/
wget https://raw.githubusercontent.com/meuter/argon-one-case-ubuntu-20.04/master/argon1.sh
# inspect script if you're paranoid
chmod a+x argon1.sh
sudo ./argon1.sh
```

## Usage

The script will generate a bunch of scripts and config files. The main commands are
- `argonone-config` to config the fan behaviour
- `argonone-uninstall` to remove all the scripts and services (conf file remains though)

I also added a custom command:
- `argonone-tempmon` which monitors the temerature using the linux sysfs.

## Warning

This has been developped in an afternoon, and has been only tested on my Raspberry Pi 4. No issues so far, but big disclaimer nontheless: use at your own risk. 



