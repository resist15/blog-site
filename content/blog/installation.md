---
title: "Installation Guide For Project404 / ArrowOS"
dateString: Feb 2023
draft: false
tags: ["Project 404", "Arrow", "Dynamic",]
weight: 999999
---

## Download Links for Installation Media

- [TWRP Recovery]()
- [Disable Forced Encryption]()
- [AOSP Recovery]()

# Basic requirements

1. Read through the instructions at least once before actually following them, so as to avoid any problems due to any missed steps!

 2. Make sure your computer has adb and fastboot. Setup instructions can be found here.

 3. Enable USB debugging on your device.

4. Boot your device with the stock OS at least once and check every functionality. Make sure that you can send and receive SMS and place and receive calls          (also   via WiFi and LTE, if available), otherwise it won’t work on P404 either!

 5. ROM is provided as-is with no warranty. While we attempt to verify everything works you are installing this at your own risk!

# Installing a custom recovery using fastboot

- Download the Project 404 / ArrowOS  Recovery. Simply download the latest recovery file.
- Connect your device to your PC via USB if it isn’t already.
- If your device isn’t already in fastboot mode, on the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type: **adb reboot bootloader** You can also boot into fastboot mode via a key combination: With the device powered off, hold Volume Down + Power. Keep holding both buttons until the word “FASTBOOT” appears on the screen, then release.
- Flash recovery onto your device (replace <recovery_filename> with the actual filename!):
    **fastboot flash recovery <recovery_filename>.img**

# Installing Project 404 / ArrowOS With TWRP Recovery

- Boot Into **`Recommended`** TWRP Recovery
- If U Are Encrypted Format Data Is Necessary / Skip This Step If Already Decrypted
- Wipe -> Advanced Wipe -> Wipe Data + Dalvik + Cache
- Flash 404 Rom Package
- Mount Vendor and Flash DFE to Stay decrypted ( Optional )
- Reboot to System

# Installing Project 404 / ArrowOS With AOSP Recovery

- Boot into Project 404 recovery
- Select Factory reset" --> "Format data/factory reset. You phone should say that /data, /cache  have been formatted.
- Go back to main menu and select "Apply update" --> "Apply from ADB"
- Connect your phone to a computer
- Run adb sideload p404_rom_file_name.zip in your cmd/powershell/terminal and wait until it finishes.
- Reboot to system

### InShort For Dynamic

Partition scheme has been switched to retrofit dynamic partitioning. No actual re-partition is involved. Instead, the physical system cust and vendor partition is mapped together to form a logical "super" partition. The size of super partition equals the sum of the physical system cust and vendor partitions. After that, logical system and vendor partitions are created on top of this super partition. In this way, we are essentially redistributing space between the physical system cust and vendor partition to accommodate for the increase in size of system libraries and prebuilt apps.

# That's all folks
After you’ve double checked that you followed the steps precisely, didn’t skip any and still have questions or got stuck, feel free to ask on our [`Telegram group`](https://t.me/resist15_support).
