# Getting Started with OPK on a Raspberry Pi

## Overview

- Required hardware
- Preparing an SD card
- Preparing a custom autorun.sh script
- Setting up a Phant account
- Troubleshooting your connection

## Required Hardware

- Raspberry Pi (link to sources)
- Wifi dongle (link to sources)
- SD card (link to sources)
- Sensor (for this tutorial, temper1 ... but soon, 1-wire)

## Preparing an SD card

Download the latest OPK SD card image here:

Then follow your favorite procedure for burning the image to an SD card.  
- Adafruit tutorial for Windows: https://learn.adafruit.com/adafruit-raspberry-pi-lesson-1-preparing-and-sd-card-for-your-raspberry-pi/making-an-sd-card-using-a-windows-vista-slash-7
- Adafruit tutorial for Mac: https://learn.adafruit.com/adafruit-raspberry-pi-lesson-1-preparing-and-sd-card-for-your-raspberry-pi/making-an-sd-card-using-a-mac
- Raspberry Pi tutorial
- Linux tutorial

```
sudo -i
df -h
umount /dev/X <-- where X is /mmcblk.. or /sdX
zcat 20150512-pirateship.img.gz > /dev/mmcblk0 <-- or whatever above volume was

```


## Setting up the remote database (phant)

Navigate to:

Create a new 'data stream', with the parameters you're interested in.

When you're done, you'll be shown a page with information about your stream.

Make note of the public and private keys; but also download the 'keys_*.json' file locally.


## Preparing your 'sensor recipe' (autorun.sh)

Look at existing recipes here:

If you want to create a recipe from scratch, go here:

In either case, you'll end up with a file, **autorun.sh**, which you will download to your laptop / computer.

You'll want to fill in the specific terms for the various items you're interested in measuring -- e.g. 'temp', 'humidity', etc.

NOTE: these terms must match those in your Phant database, above.

NOTE: The sensor recipe should include these measurement terms, but also the URL.
