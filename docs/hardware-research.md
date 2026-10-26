Hardware Research Checklist

Target Device

- Device: Motorola Moto G60
- Model: XT2135-2
- SoC: Qualcomm Snapdragon 732G
- CPU architecture: ARM64
- Development host: Windows 11

1. Device Identification

- [ ] Confirm the exact model number.
- [ ] Record the Android version and build number.
- [ ] Identify the installed firmware version.
- [ ] Determine the device's supported boot modes.
- [ ] Locate reliable documentation for this specific model.

2. Boot Chain

Research and document:

- [ ] Boot ROM and early boot stages.
- [ ] Qualcomm bootloader components.
- [ ] Android Verified Boot configuration.
- [ ] Boot image and vendor boot image formats used by the installed firmware.
- [ ] Device-specific boot configuration and partition layout.
- [ ] Whether official bootloader unlocking is available for this exact model.

Safety: Do not unlock the bootloader, change partitions, or flash experimental files during this research phase.

3. Hardware Dependencies

Investigate the hardware support required for a potential XNU port:

- [ ] CPU initialization and exception handling.
- [ ] Interrupt controller and timer.
- [ ] Physical memory layout and memory management.
- [ ] UART or another suitable debugging interface.
- [ ] Storage controller and filesystem access.
- [ ] USB support.
- [ ] Display and graphics hardware.
- [ ] Touchscreen and input devices.
- [ ] Power management and thermal control.

A working kernel would require appropriate support for the target platform; identifying the CPU architecture alone is not sufficient.

4. Existing Software and Documentation

- [ ] Find device-specific Android kernel source.
- [ ] Identify the relevant Linux kernel version and configuration.
- [ ] Review available device tree sources.
- [ ] Investigate documented boot image formats.
- [ ] Research existing ARM64 bootloader and kernel-loading projects.
- [ ] Review XNU source availability and supported platform assumptions.
- [ ] Document licensing restrictions on all referenced components.

5. Non-Destructive Diagnostics

When the Windows 11 laptop is available:

- [ ] Install Android Platform Tools from a trusted source.
- [ ] Confirm that ADB can detect the phone, if Android debugging is enabled.
- [ ] Record basic device properties.
- [ ] Inspect bootloader status using documented, read-only methods where available.
- [ ] Save diagnostic output without exposing personal identifiers.
- [ ] Back up important data before considering any future device modifications.

Do not assume that a command is read-only without checking its documented behavior.

6. Evidence and Findings

For each finding, record:

Item| Details
Research question| 
Source or reference| 
Finding| 
Confidence| Confirmed / Probable / Unknown
Follow-up needed| 

Completion Criteria

This checklist is complete when the boot chain, relevant hardware dependencies, available source code, and major technical blockers have been documented with credible references.

Completing the checklist does not mean that XNU can boot on the device.
