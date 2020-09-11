

<b>SkyHawk Recovery for SM-T295</b>

First of all, many thanks to mehanik6@4PDA for providing the T295 device tree!!!

<b>Skyhawk Setup:</b> use this guide to setup for skyhawk folder:

https://skyhawk-recovery-project.github.io/#/guide

You will need to add this file to your repo BEFORE you sync:

roomservice.xml file (click 'raw' - upper right corner of page) to see file contents:

<?xml version="1.0" encoding="UTF-8"?>

<manifest>
  <project name="gcrutchr/android_device_samsung_gto" path="device/samsung/gto" revision="master" remote="github" />
</manifest>

cd ~/skyhawk

mkdir .repo/local_manifests

create the roomservice.xml, with above contents (5 lines), in ~/skyhawk/.repo/local_manifests/roomservice.xml

cd ~/skyhawk

repo sync (will take awhile to sync) maybe go have a coffee somwhere

<b>SkyHawk Build</b>

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

<b>WHAT IS NOT WORKING:</b>

MTP
