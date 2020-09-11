

SkyHawk Recovery for SM-T295

First of all, many thanks to mehanik6@4PDA for providing the T295 device tree!!!

Skyhawk Setup use this guide to setup for skyhawk folder:

https://skyhawk-recovery-project.github.io/#/guide

You will need to add this file to your repo BEFORE you sync:

roomservice.xml file (click 'raw') to see file contents:

<?xml version="1.0" encoding="UTF-8"?>

<manifest>
  <project name="gcrutchr/android_device_samsung_gto" path="device/samsung/gto" revision="master" remote="github" />
</manifest>

mkdir .repo/local_manifests

copy the roomservice.xml contents (5 lines) to ~/skyhawk/.repo/local_manifests/roomservice.xml

cd ~/skyhawk

repo sync (will take awhile to sync) maybe go have a coffee somwhere

SkyHawk Build

cd skyhawk

move kernel folder to kernel.bak (do not need this folder) ex: mv kernel kernel.bak

type: source ./build/envsetup.sh

type: lunch

select omni_gto-eng

type: mka recoveryimage

If successful, recovery.img is in out/target/product/gto 

Copy recovery.img to your device

<b>SkyHawk Install</b>

Go to play store and install Official TWRP Manager

Open Official TWRP Manager

Select Flash Recovery

Select recovery.img on your device

Select Flash Recovery

After flash, shutdown device. Press Vol-Up + Pwr keys

You should get into SkyHawk Recovery

WHAT IS NOT WORKING:

MTP
