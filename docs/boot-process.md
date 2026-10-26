iOSintosh Boot Process Research

Purpose

This document describes the boot process that iOSintosh must investigate to determine whether the genuine Apple XNU kernel could run on a Motorola Moto G60 (XT2135-2).

This is a research plan, not a working boot implementation.

No successful XNU boot on the target device has been demonstrated, and no verified iOSintosh boot image currently exists.

1. Understand the existing boot chain

The Moto G60 uses a Qualcomm Snapdragon 732G platform and a device-specific boot chain.

Before developing a loader, research must establish:

- How the device's bootloader loads operating-system images.
- Which image formats and boot protocols the device accepts.
- Which bootloader security restrictions are enforced.
- How memory is initialized and described to the operating system.
- Which execution environment is available to a subsequent kernel.
- Which debugging methods are available during early startup.

Do not assume that a generic EFI image or an image built for another Android device will work.

2. Establish a safe development environment

Development is intended for Windows 11, 64-bit only.

The initial workflow should use official Android Platform Tools and collect device information without modifying the phone.

Recommended initial commands, with Android running:

adb devices
adb shell getprop ro.product.model
adb shell getprop ro.product.device
adb shell getprop ro.product.cpu.abi

When the device is intentionally placed into its bootloader interface, basic identification may include:

fastboot devices
fastboot getvar product
fastboot getvar unlocked

Record the complete output and any errors.

Do not unlock the bootloader, erase partitions, flash images, or attempt to boot an experimental image during initial identification.

3. Investigate the loader

A future loader would need to establish a valid handoff from the device's supported boot environment to the kernel.

Research questions include:

- Is a custom loader permitted by the device's boot chain?
- What image format and entry-point requirements apply?
- What CPU state and memory layout would the kernel require?
- How would memory maps and hardware descriptions be provided?
- How would early debugging work without a functioning display?
- What security checks would prevent the loader from running?

These questions must be answered with device-specific evidence before selecting an implementation.

4. Investigate XNU compatibility

XNU is the kernel used by Apple's operating systems. Obtaining a kernel binary is not enough to make an operating system work on different hardware.

A compatibility investigation must examine:

- ARM64 platform initialization.
- Exception levels and CPU configuration.
- Interrupt handling and system timers.
- Physical memory management.
- Device-tree or equivalent hardware descriptions.
- Serial console and debugging support.
- Storage and filesystem access.
- Required drivers and platform-specific components.
- The operating-system userspace and supporting services.

The Moto G60's hardware is not an Apple-supported platform. The amount of work required, and whether a useful boot is achievable, remain unknown.

5. Proposed research stages

Stage A — Device identification

Document the exact device variant, bootloader information, available interfaces, and Windows 11 tool versions.

Stage B — Boot-chain research

Determine the supported image formats, handoff requirements, and security restrictions using reliable documentation and non-destructive tests.

Stage C — Loader design

Write a design document before implementing code. Identify the expected entry point, memory requirements, hardware description, error handling, and debugging method.

Stage D — Minimal prototype

Only after the boot protocol is understood, consider a minimal experimental loader. Any prototype must be clearly labeled as unverified until tested on the actual device.

Stage E — XNU feasibility

Evaluate whether the required platform initialization and hardware support can be implemented. Do not claim XNU compatibility without reproducible evidence.

6. Image naming

The proposed future image filename is:

"iosintosh-g60-efi.img"

This is a naming proposal only. The ".img" extension does not establish that the image uses EFI, that it is compatible with the Moto G60, or that the device can boot it.

The previously considered command:

fastboot boot iosintosh-g60-efi.img

is not a validated instruction and must not be treated as a working procedure. Do not run it unless the image format, bootloader requirements, security state, and recovery plan have first been established.

7. Safety and security

- Keep the bootloader locked during initial research.
- Do not assume enabling OEM unlocking has unlocked the bootloader.
- Remember that unlocking may erase all user data.
- Never flash an unverified image to a device.
- Keep verified backups and a documented recovery procedure before any future modification.
- Do not distribute proprietary Apple kernel or firmware binaries.

Current status

- [x] Research plan documented.
- [ ] Device boot protocol verified.
- [ ] Loader requirements established.
- [ ] Minimal loader implemented.
- [ ] XNU compatibility demonstrated.
- [ ] Successful boot independently reproduced.

Current result: research only. No functional iOSintosh boot image is available.
