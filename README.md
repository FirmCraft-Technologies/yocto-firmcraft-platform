# Yocto FirmCraft Platform
Yocto FirmCraft Platform is a professionally structured **BSP (Board Support Package)** build environment that supports **Raspberry Pi 4/5** and **BeagleBone Black**, built on top of the Yocto Project Scarthgap release.

This platform is ideal for embedded Linux product development and is optimized for industrial and automotive-grade solutions.

## ✅ Key Features
Based on Yocto Scarthgap (4.3) release

Pre-integrated support for:

Raspberry Pi 4 (RPI4)

BeagleBone Black (BBB)

Fully integrated meta-firmcraft-bsp layer

Custom splash screen, branding, and wallpaper

OTA update infrastructure (hooks included)

Ready-to-flash SD card images

## 📦 Included Layers
```poky``` (Scarthgap)

```meta-openembedded``` (meta-oe, meta-python, meta-networking, meta-multimedia)

```meta-raspberrypi```

```meta-beagleboard```

```meta-arm / meta-arm-toolchain```

```meta-ti / meta-ti-bsp / meta-beagle```

```meta-qt6``` (optional if using Qt6-based UI)

```meta-firmcraft-bsp``` (custom platform enhancements)

## 🚀 Quick Start
1. Clone and Initialize
```bash
repo init -u git@github.com:FirmCraft-Technologies/yocto-firmcraft-platform.git
repo sync
```
2. Setup the Build Environment
```bash
source sources/poky/oe-init-build-env <build-dir>
cd <build-dir>
```
3. Add Required Layers
```bash
bitbake-layers add-layer ../sources/meta-openembedded/meta-oe
bitbake-layers add-layer ../sources/meta-openembedded/meta-python
bitbake-layers add-layer ../sources/meta-openembedded/meta-networking
bitbake-layers add-layer ../sources/meta-openembedded/meta-multimedia
bitbake-layers add-layer ../sources/meta-raspberrypi
bitbake-layers add-layer ../sources/meta-arm/meta-arm-toolchain
bitbake-layers add-layer ../sources/meta-arm/meta-arm
bitbake-layers add-layer ../sources/meta-ti/meta-ti-bsp
bitbake-layers add-layer ../sources/meta-ti/meta-beagle
bitbake-layers add-layer ../sources/meta-qt6
bitbake-layers add-layer ../sources/meta-firmcraft-bsp
```
# 🛠️ Build Your Image
For Raspberry Pi 4:

```bash
MACHINE="rpi4" bitbake firmcraft-image
```
For BeagleBone Black:

```bash
MACHINE="beaglebone" bitbake firmcraft-image
```
## 📂 Output Image Location
After build, you’ll find the output images under:

```bash
<build-dir>/tmp/deploy/images/<machine>/
```
Example for Raspberry Pi:
```
build/tmp/deploy/images/rpi4/
```
## 💾 Flashing the Image
Use bmaptool or dd to flash the .wic image to an SD card:

Using bmaptool (Recommended):
```bash
sudo bmaptool copy firmcraft-image-rpi4.wic.gz /dev/sdX
```
Using dd (Legacy):
```bash
gunzip firmcraft-image-rpi4.wic.gz
sudo dd if=firmcraft-image-rpi4.wic of=/dev/sdX bs=4M status=progress conv=fsync
```
Replace /dev/sdX with your actual SD card device.

## 📞 Support
For commercial support, custom BSP development, or product integration services, reach out to:

**FirmCraft Technologies**
📧 **info@firmcraft.in**
🌐 https://www.firmcraft.in

