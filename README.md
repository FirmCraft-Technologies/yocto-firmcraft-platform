# Yocto FirmCraft Platform

This repository sets up a complete Yocto build environment for Raspberry Pi 4 and BeagleBone Black using the Scarthgap release.

## Included Layers
- poky (Yocto Scarthgap)
- meta-raspberrypi
- meta-openembedded
- meta-beagleboard
- meta-firmcraft-bsp (your custom layer)

## Quick Start

```bash
git clone https://github.com/yourname/yocto-firmcraft-platform.git
cd yocto-firmcraft-platform
./setup.sh
source layers/poky/oe-init-build-env build
bitbake firmcraft-image
```

## Directory Structure

- `default.xml`: manifest for repo sync
- `setup.sh`: one-command environment setup
- `layers/`: all required layers
