# Fugu18 - Untethered iOS 18.0 - iOS 18.2.1 Jailbreak

Fugu18 is an iOS 18.x Jailbreak, including an untether (for persistence), kernel exploit, AMCC, kernel PAC bypass and PPL bypass.
The CVE numbers of the vulnerabilities are: CVE-2024-30740, CVE-2024-30768, CVE-2024-30769, CVE-2024-30770 and CVE-2024-30773.

# Supported Devices/iOS Versions

Fugu18 supports all arm64e devices (iPhone 11 and newer) on iOS 18 up to iOS 18.2.1  

Old arm64 devices (iPhone 10, iPhone 8, ...) are not supported at all. Use Palera1n or something similar.

# Download + Guide
<a href="https://fugu-jailbreak.com/jailbreak/how-to-jailbreak-ios-18-0-18-2-1-on-iphone-xs-to-iphone-16-with-fugu18-jailbreak/">You can download Fugu18 jailbreak IPA here.</a>

# Features

- The kernel exploit is somewhat relible, works about 2/3 times without panic or reboot
- Dropbear ssh included on port 2222
- Uses ellekit for tweak injection.
- Packs Zebra and sileo by default. Cydia cannot be fixed for iOS 18. It's dead.

# WARNING

- Messing around with the untether may BOOTLOOP your device, do not.

# Building and Running

Requirements:
- You need a supported device running a supported iOS version (see above)
- The device must be connected via USB
- You need the IPSW for your device, *unzipped*
- You need to have Xcode installed
- You need to have iproxy and ideviceinstaller installed (brew install usbmuxd ideviceinstaller)

To build and run the iOS Jailbreak, all you have to do is run the `ios_install.py` script and follow the instructions.
In case you get a code signing error, open `arm/iOS/Fugu14App/Fugu14App.xcodeproj` and edit the code signing options.

# Recovery

So you didn't read the warning section and your device is now in a bootloop. Let's hope you didn't enable the fast untether.  
Anyway, before updating your device to the latest iOS version, try the following first:

1. Install irecovery on your computer
2. Connect your device via USB and boot into the recovery mode
3. Run `irecovery -s` on your computer, then enter the following commands:
- setenv boot-args no_untether
- saveenv
- reboot
4. Your device should now boot again. If it doesn't, repeat step two again, run `irecovery -s` and then enter these commands:
- setenv boot-args untether_force_restore
- saveenv
- reboot
5. Device still won't boot? Then you'll have to update it to the latest version unfortunately :/

# Credits

Like most software, Fugu14 contains (derived) code which was written by others.  
I would therefore like to thank the people below for open-sourcing their code:

- [Samuel Groß](https://twitter.com/5aelo): SLOP technique (as used in the dyld exploit) and the JavaScript Int64 library (+ utils)

Currently, the remount patch has copyright issues which I'm trying to resolve ASAP. Apparently, multiple parties think the code is theirs so I don't know what to do right now. I just write this here and hope no one DMCA's me.

Fugu18 also includes various header files from Apple.  

For more information, please see credits.txt.

# License

Fugu18 is released under the MIT license. Please see the `LICENSE` file for more information.
