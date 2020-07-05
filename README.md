# ASUS VivoBook S430FN Hackintosh Files

This repository contains files intended for use on ASUS VivoBook S430FN running macOS Catalina 10.15.5 using OpenCore bootloader.

⚠️️️ **WARNING** ⚠️️️
The EFI files provided in this repository is **only for ASUS S430FN laptops** and **can't be used for other laptops**. Even having the same device as me doesn't guarantee that it will work out of the box. You should try and configure it further by yourself.

**Before** you proceed to make a Hackintosh machine, I really, really beg you to at least learn and understand the concepts of EFI, OpenCore, ACPI, SSDTs (.aml and .dsl files), kexts, and any other Hackintosh-related knowledge.

# Hardware

|Name|Description|Notes
:-:|:-:|:-:
|Laptop|Asus VivoBook S430FN
|CPU|Intel(R) Core(TM) i5-8265U CPU @ 1.60GHz
|Generation|8th Gen / Whiskey Lake (≈Coffee Lake)
|Integrated GPU|Intel(R) UHD Graphics 620 2048 MB
|Discrete GPU|NVIDIA MX150 (unusable)
|SSD|INTELSSDPEKNW (512GB)
|Wi-Fi|Intel(R) Wireless-AC 9560|Usable with itlwm.kext
|Bluetooth|Available
|Sound Card|Realtek ALC256 (ALC3246)|layout=21
|Trackpad|ELAN1200|VoodooI2C driver
|SMBIOS|MacbookPro15,4
|Bootloader|OpenCore 0.5.9|with OpenCanopy (GUI) enabled by default

## Tested and working
- [x] Integrated GPU (Intel)
- [x] Audio & headphone jack
- [x] USB 3.1 and 2.0 Ports
- [x] WiFi & Bluetooth (see notes below)
- [x] Battery stats
- [x] Trackpad (see notes below)
- [x] Sleep & wake
- [x] Sound Fn keys (+, -, mute)
- [x] Display brightness Fn keys (+, -)
- [x] Backlit keyboard Fn keys (16 levels) (Using F6 & F7)
- [x] Trackpad disable/enable (PrtSrc)

## Not tested
- [ ] HDMI Output
- [ ] USB-C Port
- [ ] Micro SD card reader
- [ ] iCloud and any Apple-exclusive features, because I don't really use iServices

## Not working
- [ ] Fingerprint reader
- [ ] NVIDIA MX150 (Discrete GPU will **never** work on Hackintosh)

## ⚠️️️ Important Notes

- **Intel Wi-Fi**
[itlwm](https://github.com/OpenIntelWireless/itlwm) driver is **under heavy development**. It can cause a kernel panic but very seldom. Please expect to get 60-80% of the transfer speed on Windows (which is still pretty good tho). Let us appreciate and help the [developer](https://github.com/OpenIntelWireless/) to maintain the project. Report any errors and bug to them. To get the latest commit and improvements, I really suggest you to compile itlwm yourself. I also recommend to use it with [HeliPort](https://github.com/OpenIntelWireless/HeliPort), its GUI companion app.

- **Bluetooth tethering**
AFAIK, tethering using Bluetooth is really slow from my experience and not worth the struggle. Instead of wasting your precious time, I suggest you to just use USB tethering and install [HoRNDIS](https://joshuawise.com/horndis).

- **Trackpad**
Sometimes the trackpad stops working randomly. At verbose boot it will show "stuck at busy _timeout_ [0]." To fix this, you can try to invalidate the kext cache, clear NVRAM, and do a restart (or two). Although I don't really know what causes this problem.

- **Battery drain problem**
Hackintoshes don't run on Apple's official hardware, therefore the battery consumption is not optimized. You can **undervolt** your CPU & GPU to get more battery life using using [VoltageShift](https://github.com/sicreative/VoltageShift). Only do this if you know what you're doing. My optimal setting is `-100 -80 -100 0 0 0 0 0 0 15`.

## Lastly,
I really really suggest you to learn how to set up your own system and configure it according to your own needs. You can learn more at [Dortania OpenCore Guide](https://dortania.github.io/vanilla-laptop-guide/).

Please let me know if you can do any improvement to my setup. Thank you.