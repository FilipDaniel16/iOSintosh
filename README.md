# iOSintosh
Experimental XNU bootloader research for Motorola Moto G60
iOSintosh

Experimental XNU boot research for the Motorola Moto G60.

«[!WARNING]
Work in progress — experimental research only. iOSintosh has not successfully booted XNU on the Motorola Moto G60. No verified boot image is currently available. Do not treat this project as a working iOS port.»

About

iOSintosh is an experimental research project exploring whether Apple's XNU kernel can be brought up on non-Apple ARM64 hardware, with the Motorola Moto G60 as the initial target.

The project begins with hardware research, boot-chain investigation, and Windows-compatible development tools. Booting XNU is a long-term research goal, not a currently working feature.

Target Hardware

Component| Details
Device| Motorola Moto G60
Model| XT2135-2
Processor| Qualcomm Snapdragon 732G
Architecture| ARM64
Development host| Windows 11, 64-bit
Project status| Early development

Initial development is focused exclusively on Windows 11. Windows 10 is not a supported development environment.

Project Goals

- Investigate the Moto G60's boot process and hardware capabilities.
- Research the requirements for loading an experimental ARM64 XNU kernel.
- Develop Windows 11-compatible diagnostic and research tools.
- Document bootloader requirements and hardware compatibility limitations.
- Build and test prototypes incrementally.
- Publish reproducible research and verified artifacts when available.

Current Status

Feature| Status
GitHub repository| Created
Target device identified| Yes
Windows 11 development plan| Planned
Device diagnostics| Not yet implemented
Custom loader| Not yet implemented
XNU compatibility research| Early research
Verified XNU boot| Not achieved
"iosintosh-g60-efi.img"| Not available
Developer Preview 0.1.0| Planned

Development Roadmap

Phase 1 — Research and Preparation

- [ ] Document the exact Moto G60 hardware and firmware.
- [ ] Record the current bootloader state.
- [ ] Prepare a Windows 11 development environment.
- [ ] Establish a safe device-diagnostics workflow.
- [ ] Document recovery options before any bootloader experiments.

Phase 2 — Windows Tooling

- [ ] Plan the iOSintosh command-line interface.
- [ ] Investigate firmware archive inspection.
- [ ] Add device-detection and diagnostic functionality.
- [ ] Document required tools and setup instructions.

Phase 3 — Boot Architecture Research

- [ ] Investigate the device's boot chain.
- [ ] Research supported boot image formats and execution constraints.
- [ ] Study ARM64 kernel entry requirements.
- [ ] Determine whether a custom loader is technically feasible.

Phase 4 — XNU Compatibility

- [ ] Research XNU initialization requirements.
- [ ] Identify dependencies on Apple-specific hardware and firmware.
- [ ] Investigate the gap between XNU's supported platforms and the Moto G60.
- [ ] Document technical blockers and experimental findings.

Phase 5 — Prototype and Testing

- [ ] Develop prototypes only after their format and purpose are understood.
- [ ] Validate artifacts before attempting to execute them on hardware.
- [ ] Record test conditions, logs, and results.
- [ ] Document recovery procedures and known limitations.

Phase 6 — Developer Preview

- [ ] Publish a verified and documented development artifact, if feasible.
- [ ] Provide checksums and release notes.
- [ ] Document supported configurations and known issues.
- [ ] Prepare iOSintosh Developer Preview 0.1.0 when there is a genuine artifact suitable for release.

Planned Windows CLI

The following commands are ideas for future development, not implemented features:

iosintosh.exe inspect
iosintosh.exe verify "C:\Firmware\iOS18.ipsw"
iosintosh.exe devices

Possible purposes:

- "inspect" — inspect supported research artifacts.
- "verify" — validate an IPSW archive and report its contents.
- "devices" — display available device diagnostics.

Actual behavior and supported formats will be documented after implementation.

Bootloader and Device Safety

The Moto G60 currently has a locked bootloader.

Enabling OEM unlocking in Android Developer Options does not itself unlock the bootloader or bypass Android's security mechanisms. Unlock eligibility and the required procedure must be verified for the exact device.

Important precautions:

- Back up important data before any bootloader-unlocking attempt.
- Understand that unlocking may factory-reset the device.
- Never flash or boot an unverified image.
- Do not assume that a generic EFI image can boot on this phone.
- Keep a recovery plan before performing experiments.

The proposed filename "iosintosh-g60-efi.img" and a possible command such as:

fastboot boot iosintosh-g60-efi.img

are unverified ideas only. This command must not be treated as a working installation or boot procedure. Image format, bootloader support, and kernel compatibility must first be established.

Important Technical Limitations

XNU is a kernel, not a complete iOS installation. A successful kernel boot would not automatically provide a functioning iOS environment.

Major challenges may include:

- Hardware-specific initialization.
- Memory and interrupt-controller configuration.
- Device drivers for the Moto G60.
- Platform firmware and boot-chain compatibility.
- Kernel configuration and early userspace requirements.
- Apple's proprietary components and platform dependencies.

The Moto G60 was not designed as an Apple-supported XNU platform. Technical feasibility remains uncertain, and successful booting is not guaranteed.

Repository Structure

The project may grow toward the following structure:

iOSintosh/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── .gitignore
├── docs/
│   ├── architecture.md
│   ├── boot-process.md
│   ├── moto-g60.md
│   └── development-roadmap.md
├── src/
│   └── loader/
├── tools/
│   └── windows/
│       └── README.md
├── firmware/
│   └── README.md
├── images/
│   └── README.md
└── .github/
    └── ISSUE_TEMPLATE/

This is a proposed structure. Directories and files will be added as the project develops.

Firmware and Copyright

This repository is intended for research, documentation, and original development tools.

- Do not commit or redistribute Apple's proprietary kernel or firmware binaries without appropriate authorization.
- Do not publish private keys, signing credentials, or other sensitive material.
- Use legally obtained firmware for analysis and respect applicable license terms.
- Document tool versions, hashes, and test results where appropriate.

Contributing

Research notes, hardware documentation, reproducible diagnostics, and technical corrections are welcome.

When contributing, distinguish clearly between:

- Verified: reproduced or directly confirmed results.
- Under investigation: active research with incomplete evidence.
- Planned: ideas that have not yet been implemented.

Do not claim that XNU has booted successfully without reproducible evidence.

Disclaimer

iOSintosh is an independent experimental project and is not affiliated with, endorsed by, or supported by Apple, Motorola, or Qualcomm.

Bootloader and firmware experiments can result in data loss or an unbootable device. Proceed only when you understand the risks and have a recovery plan.

The goal is to investigate what is technically possible, document what works, and be transparent about what does not.
