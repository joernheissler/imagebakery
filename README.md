# Create custom images for Revolution Pi

## Instructions

```
# Start an AWS EC2 ARM64 instance, https://wiki.debian.org/Cloud/AmazonEC2Image/Buster

# As root:
wget -qO- https://github.com/joernheissler/imagebakery/archive/refs/heads/minimal.tar.gz | tar -xvz
cd imagebakery-minimal
./build

# Result is raspios-buster-armhf-lite.img.zst
```

## Intended usage

### Download RaspiOS (previously called Raspbian) image
Works with both [RaspiOS](https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit) desktop and lite images.

*Raspberry Pi OS with desktop*
```
curl -O https://downloads.raspberrypi.org/raspios_armhf/images/raspios_armhf-2021-03-25/2021-03-04-raspios-buster-armhf.zip
unzip 2021-03-04-raspios-buster-armhf.zip
```

*Raspberry Pi OS Lite*
```
curl -O https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-03-25/2021-03-04-raspios-buster-armhf-lite.zip
unzip 2021-03-04-raspios-buster-armhf-lite.zip
```

### Customize for Revolution Pi
(requires root, an armhf system (RasPi or VM) and Internet connectivity;
to cross-build, apt-get install qemu-user-static binfmt-support;
custom packages can be placed in debs-to-install/):

`customize_image.sh <raspbian-image>`

### Collect sources on a physical medium for GPL compliance
(requires root and Internet connectivity):

`collect_sources.sh <raspbian-image> /media/usbstick`
