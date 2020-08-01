# NimbusPi

NimbusPi is a collection of projection mapping, VJ, and lighting design tool built for the Raspberry Pi. 

## Overview
NimbusPi images currently contains 2 separate applications, ShaderMapper and FlowMapper. You can easily switch between these applications, but only 1 may be run at a time. See the feature sets for each below:

##### ShaderMapper (Note: USB Microphone Recomended)
- Multi object quad and grid warping with masking
- Content generated live by sound reactive GLSL Fragement Shaders (limit: simultaneous playback of 2x shaders, applied to up to 4 objects)
- Ability to record Artnet/DMX and playback at a variable rate or driven by audio amplitude.

##### FlowMapper (Note: USB Webcam Required)
- Multi object quad and grid warping, no masking
- Content generated by applying effects to a local webcam stream
- Effects include time delay, brightness and movement thresholds, kaleidoscoping, and color mixing.
- Works very well for live "Light Painting" installations

## Installation

Just download the latest image [here](http://www.nimbuslaboratory.com/NimbusPi.img) and then burn to an SD card using [Raspberry Pi Imager](https://www.raspberrypi.org/downloads/) or an alternative of your choosing. These images should work on both the Pi 3b+ and Pi 4, although the apps run substantially smoother on a Pi 4.

## Usage Instructions

![NimbusPi User Guide](http://www.nimbuslaboratory.com/NimbusPi%20User%20Guide.jpg)

### Local Development

The code based is based around [Three.js](https://threejs.org/) and designed primarily to be run as a local web app. Most features will work on any machine capable of running a simple webserver, php, and chrome. Features related to DMX typically require additional configuration to proxy the [OLA](https://www.openlighting.org/ola/tutorials/ola-on-raspberry-pi/) port (9090) to your web port.

For local development there is no build process, just clone this repo to your webserver's root directoy. But do note that these apps use WebRTC's `getUserMedia`, and thus must either be hosted locally or on a site with TLS/SSH enabled.

### Building Images

To build your own image, you must be setup to run [packer-builder-arm-image](https://github.com/solo-io/packer-builder-arm-image). Once this is done, simply run a packer build using the [packer template file found here](https://github.com/mshortMob/NimbusPi/blob/master/packer/build.json).

