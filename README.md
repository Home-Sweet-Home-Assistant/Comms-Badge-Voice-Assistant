<p align="center">
  <img width="500" src="https://github.com/Home-Sweet-Home-Assistant/Comms-Badge-Voice-Assistant/assets/121906349/d02df3c1-0217-4f35-a088-20f73d5eb4e3" alt="Home Sweet Home Assistant" />
</p>

<h1 align="center">Comms Badge Voice Assistant</h1>

A wearable voice assistant satellite in the shape of a comms badge from the sci-fi TV series Farscape. This device is intended to be used in conjunction with [Home Assistant](https://www.home-assistant.io/) and [ESPHome](https://esphome.io/) to communicate with the [Assist voice assistant](https://www.home-assistant.io/voice_control/).

---

> [!important] 
> This project is currently a work-in-progress at a relatively early stage. I will continue to roll out files and documentation as soon as I feel that they are prepared well enough for public consumption. I have been largely learning as I go, and I am rather new to most of this. That being said, please take care of me, and please be kind when there are, inevitably, mistakes.

---

## Features
- **Wifi**
- **Capacitive Touch Sensor for Voice Assistant Activation**
- **Microphone and Speaker**
- **Battery Powered**
- **Rechargeable**
- **USB-C**
- **RGB Status LED**
- **Wake-Word-Controlled on USB Power**

## Design
The physical design of the Comms Badge is based on those from Farscape. It features a brass plate making up the front face of the Badge with a stainless steel wire mesh in the keyhole. The brass plate will also act as part of the capacitive touch sensor used to activate the voice assistant functions. A 3D-printed case makes up the body of the device, featuring holes for the slide switch and the USB-C port as well as stand-offs to support the PCB over the battery and into which the brass plate is screwed. Speaker fabric can be adhered to the underside of the brass plate to hide the contents; Red can be used to produce a faithful recreation or other colors can be used to customize the badges for different users.

The electronics inside are built around an ESP32-S3 microcontroller. The ESP32-S3 has many built-in functions that are being taken advantage of for this project, including the two I<sup>2</sup>S interfaces for the speaker and microphone, several touch-sensing IOs (though we only need one), WIFI and Bluetooth, and a USB Serial/JTAG controller. In addition, by adding extra flash and PSRAM, the ESP32-S3 should be able to handle on-device wake-word functionality that has recently been provided in [microWakeWord](https://github.com/kahrendt/microWakeWord).

---

## How to Make a Comms Badge
This project is still very much in progress, and I am currently awaiting the first PCBs and components to build an initial prototype. So that no one has to waste money building their own if there turn out to be any problems, I will hold off on publishing the PCB files until I am sure that they will work. In the mean time, I will provide the current schematic and case files and begin filling in the Wiki with instructions.

---

## Goals for the Future
- [ ] Make it work!
    - I know this should be obvious, but once I receive my PCBs and components, I still have to make sure that the design will actually work. This will involve testing and fiddling and, likely, revisions. This part has to be done first before I can move on to other goals.
- [ ] Make it smaller!
    - I feel like this is always the goal anymore, and while the XY dimensions won't change in order to best fit the original intention to mimic the Farscape comms badges, I did think of a couple of ways that I could possibly shrink the device thickness, which comes out to a somewhat clunky ~1/2", not including the pin.
- [ ] Make other designs
    - The first choice in series to base my idea of a wearable voice assistant is, of course, Star Trek. I didn't choose to pursue it as part of my final first design in part because it was too obvious, but primarily, it was that there are several different styles of Star Trek badges, none of which are especially friendly shapes to start from. My goal was to make a working design that could then be adapted into other shapes, and I fully intend to work on a Star Trek variant or two down the line.
    - In addition, if this project proves to be popular enough, I would like to make a completely original design that could be crowd-sourced into reality as a fully-built device for sale using Crowd Supply.
- [ ] Bluetooth, maybe?
   - I have seen the warning in the ESPHome documentation. I added 16Mb of flash and PSRAM each to my initial design in the hopes of leaving room for future expansion of capabilities. I have no real frame of reference, but I assume it's a bit overpowered for regular use. I reasoned that that extra overhead might make it possible to use the Comms Badge Voice Assistant with Bluetooth instead of WIFI, which I would personally prefer in most cases. It may or may not be possible, but I'd like to try eventually.

>     Audio and voice components consume a significant amount of resources (RAM, CPU) on the device.
>     **Crashes are likely to occur** if you include too many additional components in your device’s configuration. In particular, Bluetooth/BLE components are known to cause issues when used in combination with Voice Assistant and/or other audio components.
- [ ] Customization options
    - This may include custom voices or responses (who wouldn't want a response from Pilot on Moya), custom LED routines, custom initialization tones, basically whatever in the realm of possibilities people can think of that they might want to choose for themselves. Once we have a functional device, we can get into adding options for how it works.
