iOSintosh Windows 11 Development Tools

Overview

This directory documents the Windows development environment for iOSintosh.

Supported operating system: Windows 11, 64-bit.

Windows 10 is not supported by this project.

The initial goal is to prepare a repeatable, non-destructive workflow for inspecting the Motorola Moto G60 (XT2135-2).

1. Requirements

- A computer running Windows 11, 64-bit.
- A Motorola Moto G60 (XT2135-2).
- A suitable USB data cable.
- An internet connection for downloading development tools.
- Sufficient free disk space for development tools and research files.

Do not unlock the bootloader or modify device partitions as part of the initial setup.

2. Install Android Platform Tools

Download Android SDK Platform Tools from Google's official website:

https://developer.android.com/tools/releases/platform-tools

1. Download the Windows ZIP archive.

2. Extract it to a convenient folder, for example:
   
   "C:\Android\platform-tools"

3. Open that folder in File Explorer.

4. Click the address bar, type "cmd", and press Enter.

A Command Prompt window should open in the Platform Tools directory.

Check that ADB is available:

adb --version

Check that Fastboot is available:

fastboot --version

Record the versions in your development notes.

3. Inspect the phone with ADB

ADB can communicate with Android while the phone is running.

1. On the phone, open Settings.
2. Enable Developer options if necessary.
3. Enable USB debugging.
4. Connect the phone to the Windows 11 computer.
5. Accept the USB debugging authorization prompt on the phone, if shown.

In Command Prompt, run:

adb devices

If the phone is listed as "unauthorized", unlock the phone and accept its authorization prompt. If no device appears, check the USB cable, USB port, and device settings.

When the device is authorized, collect basic information:

adb shell getprop ro.product.model
adb shell getprop ro.product.device
adb shell getprop ro.build.version.release
adb shell getprop ro.product.cpu.abi

Save the output in your research notes.

4. Inspect Fastboot

Fastboot communicates with the device's bootloader rather than the normal Android system.

Only enter the bootloader using the documented procedure for your device.

Then run:

fastboot devices
fastboot getvar product
fastboot getvar unlocked

Some commands may return different results depending on the bootloader version. Record the exact output, including errors.

Do not run bootloader-unlock, erase, flash, or experimental boot commands during initial inspection.

Enabling OEM unlocking in Android settings does not itself unlock the bootloader. Unlocking may erase user data.

5. Troubleshooting

ADB does not list the phone

- Check that the phone is powered on and unlocked.
- Confirm USB debugging is enabled.
- Use a cable that supports data, not charging only.
- Try another USB port.
- Check for an authorization prompt on the phone.

Fastboot does not list the phone

- Confirm the phone is actually in its bootloader interface.
- Check the USB cable and port.
- Record any error messages.
- Investigate Windows device-driver requirements for the exact device.

Do not download drivers or utilities from untrusted sources.

A command is not recognized

Check that Command Prompt is open in the extracted Platform Tools folder. You can also use the full path to the executable.

6. Research notes

For each test, record:

- Date of the test.
- Windows 11 version.
- Platform Tools versions.
- Exact device model.
- Exact command entered.
- Full output or error message.
- Whether the result was reproduced.

Do not publish device serial numbers, account information, or other private identifiers.

7. Future tooling

The following command names are ideas for future iOSintosh software. They are not implemented commands:

iosintosh.exe inspect
iosintosh.exe verify "C:\Firmware\iOS18.ipsw"
iosintosh.exe devices

Do not attempt to use them until an actual implementation exists.

Future tools may help inspect device information, validate user-supplied files, and organize diagnostic output. File verification alone cannot establish that firmware or a kernel is compatible with the Moto G60.

Current status

- [ ] Windows 11 environment prepared.
- [ ] ADB version recorded.
- [ ] Fastboot version recorded.
- [ ] Device properties collected.
- [ ] Bootloader information recorded.
- [ ] Repeatable inspection procedure verified.

No functional iOSintosh loader or bootable image is provided by this guide.
