Contributing to iOSintosh

Thank you for your interest in iOSintosh!

iOSintosh is an experimental research project investigating the feasibility of booting the genuine Apple XNU kernel on the Motorola Moto G60 (XT2135-2).

The project is in an early research stage. A successful XNU boot has not been demonstrated.

Project goals

- Investigate the Moto G60 boot process and hardware.
- Research the technical requirements for XNU kernel loading.
- Develop Windows 11-compatible research and diagnostic tools.
- Document experiments, limitations, and reproducible results.
- Clearly distinguish verified results from hypotheses and future plans.

Development environment

Supported development operating system: Windows 11, 64-bit.

Windows 10 is not a supported development environment for this project.

Tools may include Android Platform Tools (ADB and Fastboot), Git for Windows, and appropriate development toolchains.

Evidence and reporting

When documenting technical findings, use these labels:

- Verified: Confirmed through a reproducible test or reliable technical documentation.
- Likely: Supported by evidence but not fully confirmed.
- Hypothesis: A proposed explanation that needs testing.
- Planned: A future goal that has not yet been implemented.

Please include device details, commands used, relevant output, and steps to reproduce a finding when possible.

Safety

- Do not assume that an experimental boot image is functional or safe.
- Do not flash unverified images to a device.
- Do not run erase, flash, or boot commands without understanding their effects.
- Bootloader unlocking may erase all user data and can affect device security or warranty.
- Enabling OEM unlocking in Android does not itself unlock the bootloader.
- Back up important data before any operation that could modify the device.
- Never describe a planned feature as working until it has been tested.

Firmware and intellectual property

Do not commit proprietary Apple firmware, copyrighted kernel binaries, private keys, or other restricted files to this repository.

Research tools and documentation should be designed to work with files supplied by the user where appropriate.

Code contributions

Before proposing code:

1. Explain the problem the change addresses.
2. Identify the target device and Windows 11 environment where relevant.
3. Document dependencies and testing steps.
4. Clearly identify anything that is experimental or unverified.
5. Avoid claiming compatibility without evidence.

Current status

iOSintosh is a work in progress. There is currently no verified bootable iOSintosh image, and successful execution of the XNU kernel on the Moto G60 has not been established.

All contributions should help make the research more accurate, reproducible, and transparent.
