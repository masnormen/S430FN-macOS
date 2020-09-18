# ASUS VivoBook S430FN Hackintosh Setup

This repository contains files intended for use on ASUS VivoBook S430FN running macOS Catalina 10.15.6 using OpenCore bootloader.

## ⚠️️️ WARNING

The EFI files provided in this repository is **only for ASUS S430FN laptops and can't be used for other laptops**. Even having the same device as me doesn't guarantee that it will work out of the box. You should try and configure it further by yourself.

The concepts of EFI, OpenCore, ACPI, SSDTs (.aml and .dsl files), kexts, and any other Hackintosh-related knowledge is required to use this setup.

# Hardware

|Name|Description|Notes
:-:|:-:|:-:
|Laptop|Asus VivoBook S430FN
|CPU|Intel(R) Core(TM) i5-8265U CPU @ 1.60GHz
|Generation|8th Gen / Whiskey Lake (≈Coffee Lake)
|Integrated GPU|Intel(R) UHD Graphics 620 2048 MB
|Discrete GPU|NVIDIA MX150 (unusable)
|Wi-Fi|Intel(R) Wireless-AC 9560|Usable with itlwm.kext
|Sound Card|Realtek ALC256 (ALC3246)|layout=21
|Trackpad|ELAN1200|VoodooI2C driver
|SMBIOS|MacbookPro15,4
|macOS|macOS Catalina 10.15.6
|Bootloader|OpenCore 0.5.9|with OpenCanopy (GUI) enabled by default

## Tested and working
- [x] Integrated GPU (Intel)
- [x] Audio & headphone jack
- [x] USB 3.1 and 2.0 Ports
- [x] WiFi & Bluetooth (see notes below)
- [x] Battery stats
- [x] Trackpad
- [x] Sleep & wake (though it is slow)
- [x] Sound Fn keys
- [x] Display brightness Fn keys
- [x] Backlit keyboard (Using Fn + F6 & F7)

## Not tested
- [ ] USB-C Port
- [ ] Micro SD card reader
- [ ] iCloud and any Apple-exclusive features, because I don't really use iServices

## Not working
- [ ] HDMI Output
- [ ] Trackpad disable/enable (PrtSrc) - used to be working
- [ ] Fingerprint reader
- [ ] NVIDIA MX150 (Discrete GPU will **never** work on Hackintosh)

# Version history

- 1.2 / Sep 18 2020: Rolled back some kext's update which is to blame for the battery drainage issue.
- 1.1 / Sep 2 2020: Updated all kexts, included AsusSMCDaemon & Heliport
- 1.0 / Jul 7 2020: First version

# Important Notes

### **Intel Wi-Fi**
[itlwm](https://github.com/OpenIntelWireless/itlwm) driver is **under development**. Please expect to get 60-80% of the transfer speed on Windows (which is still pretty good tho). Let us appreciate and help the [developer](https://github.com/OpenIntelWireless/) to maintain the project. Report any errors and bug to them. I also packed this Hackintosh setup with [HeliPort](https://github.com/OpenIntelWireless/HeliPort), its GUI companion app.
### **AsusSMCDaemon**
Please refer [here](https://github.com/hieplpvip/AsusSMC/wiki/Installation-Instruction) if you want to use keyboard backlight.
### **Bluetooth tethering**
Tethering using Bluetooth is really slow from my experience and not worth the struggle. Instead of wasting your precious time, I suggest you to just use USB tethering and install [HoRNDIS](https://joshuawise.com/horndis).
### **Battery drain problem**
Hackintoshes don't run on Apple's official hardware, therefore the battery consumption is not optimized. You can **undervolt** your CPU & GPU to get more battery life using using [VoltageShift](https://github.com/sicreative/VoltageShift). Only do this if you know what you're doing. My optimal setting is `-100 -80 -100 0 0 0 0 0 0 15`.

## Lastly,
I really really suggest you to learn how to set up your own system and configure it according to your own needs. You can learn more at [Dortania](https://dortania.github.io/getting-started/).

We need more maintainer and issues report to make this Hackintosh setup better. Please make a PR if you do have an improvement to my setup. Thank you.
