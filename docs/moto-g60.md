Motorola Moto G60 — Target Device

Device identification

Property| Details
Device| Motorola Moto G60
Target model| XT2135-2
System-on-chip| Qualcomm Snapdragon 732G
CPU architecture| ARM64
Development operating system| Windows 11, 64-bit
Project status| Research and feasibility investigation

Hardware details should be verified against the exact device variant before attempting low-level development.

Project objective

iOSintosh investigates whether it is technically feasible to load and run the genuine Apple XNU kernel on the Motorola Moto G60.

This is an experimental research goal, not a demonstrated capability. Android and iOS use different platform components, and the XNU kernel is not expected to run on this device without substantial platform-specific investigation.

Initial device checks

The initial phase should identify the device and inspect its bootloader state without modifying the phone.

Requirements

- A Windows 11, 64-bit computer.
- A suitable USB cable.
- Android Platform Tools from Google's official Android developer website.
- USB debugging enabled if using ADB.
- The phone and its exact model identified.

Official download page: https://developer.android.com/tools/releases/platform-tools

ADB checks

When Android is running, connect the phone and open Command Prompt in the Platform Tools folder.

Run:

adb devices

If the phone is listed as authorized, collect basic information:

adb shell getprop ro.product.model
adb shell getprop ro.product.device
adb shell getprop ro.build.version.release
adb shell getprop ro.product.cpu.abi

Save the output for research documentation. These properties are useful clues, but they do not independently verify every hardware detail.

Fastboot checks

Only enter the bootloader using the device's normal documented procedure. Then run:

fastboot devices
fastboot getvar product
fastboot getvar unlocked

Fastboot output can vary by bootloader version. Record any errors exactly as shown.

These commands are for identification only. Do not run "fastboot flashing unlock", "fastboot erase", "fastboot flash", or "fastboot boot" during this initial inspection.

Bootloader considerations

The project device currently has a locked bootloader. Enabling the Android Developer Options setting called OEM unlocking does not itself unlock the bootloader or guarantee that unlocking is available.

Bootloader unlocking may erase all user data. Before considering it, check the official Motorola instructions for the exact model and understand the consequences.

ADB and Fastboot do not bypass the bootloader's security restrictions.

XNU compatibility challenges

Loading XNU is only one part of the problem. A viable system would also need a compatible early boot environment and suitable support for the device's hardware.

Research areas include:

- Boot protocol and image format.
- ARM64 execution environment and exception levels.
- Memory layout and device-tree or equivalent hardware description.
- Interrupt controller and timer initialization.
- UART or another early debugging path.
- Storage, USB, display, and power management.
- Required kernel configuration and platform-specific components.
- Whether the necessary drivers and userspace can legally and technically be obtained or implemented.

Compatibility is unknown until supported by evidence and testing.

Current status

- [x] Target device selected.
- [x] Initial research documentation started.
- [ ] Exact device and bootloader details independently recorded.
- [ ] Windows 11 diagnostic workflow tested.
- [ ] Boot chain investigated.
- [ ] XNU compatibility assessed.
- [ ] Any experimental loader implemented and tested.

There is currently no verified bootable iOSintosh image.
