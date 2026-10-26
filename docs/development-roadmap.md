iOSintosh Development Roadmap

Project overview

iOSintosh is an experimental research project investigating the feasibility of running the genuine Apple XNU kernel on a Motorola Moto G60 (XT2135-2).

Project status: Early research.

A successful XNU boot has not been demonstrated. There is no verified bootable iOSintosh image.

Development environment

- Supported operating system: Windows 11, 64-bit.
- Target device: Motorola Moto G60, model XT2135-2.
- Target architecture: ARM64.
- Primary research areas: Device boot chain, loader design, XNU compatibility, and diagnostic tooling.

Windows 10 is not a supported development environment for this project.

Phase 1 — Repository foundation

- [x] Create the project repository.
- [x] Write the initial README.
- [x] Add contribution guidelines.
- [x] Document the target device.
- [x] Document the proposed boot research process.
- [ ] Add a license after deciding which license is appropriate.
- [ ] Add a ".gitignore".
- [ ] Review documentation for accuracy and consistency.

Phase 2 — Windows 11 development tools

- [ ] Document the Windows 11 setup procedure.
- [ ] Install and verify Android Platform Tools.
- [ ] Record ADB and Fastboot versions.
- [ ] Create a repeatable device-inspection procedure.
- [ ] Record the Moto G60's actual reported properties.
- [ ] Document diagnostic output and troubleshooting steps.

Completion criterion: Another developer can reproduce the non-destructive inspection procedure on Windows 11.

Phase 3 — Device and boot-chain research

- [ ] Verify the exact device variant.
- [ ] Document bootloader information.
- [ ] Research supported boot image formats.
- [ ] Determine relevant bootloader security restrictions.
- [ ] Research the kernel handoff requirements.
- [ ] Identify an early debugging method.
- [ ] Document recovery options before considering device modifications.

Completion criterion: The boot process and its limitations are supported by reliable, device-specific evidence.

Phase 4 — XNU feasibility study

- [ ] Research the relevant XNU source code and licensing.
- [ ] Identify the required ARM64 initialization sequence.
- [ ] Investigate memory layout and hardware descriptions.
- [ ] Assess interrupt, timer, and console requirements.
- [ ] Identify the platform-specific drivers and components that would be needed.
- [ ] Assess whether the necessary supporting software can be implemented or legally obtained.
- [ ] Publish a feasibility report with evidence and unresolved questions.

Completion criterion: A documented assessment explains what is technically possible, what remains unknown, and what would be required for further work.

Phase 5 — Experimental loader

This phase must not begin until the boot protocol and security requirements are understood.

- [ ] Write a loader design specification.
- [ ] Define image format and memory requirements.
- [ ] Define error reporting and debugging behavior.
- [ ] Implement a minimal prototype if feasible.
- [ ] Test in an appropriate environment before attempting any device boot.
- [ ] Document known limitations and recovery procedures.

Completion criterion: A prototype's actual capabilities are documented and independently reproducible.

Phase 6 — XNU boot investigation

- [ ] Establish a valid kernel-loading path.
- [ ] Investigate platform initialization.
- [ ] Collect early boot diagnostics.
- [ ] Document every failure and test result.
- [ ] Demonstrate a kernel milestone before claiming success.
- [ ] Publish reproducible evidence for any successful result.

A loader starting successfully does not, by itself, mean that XNU has booted.

Phase 7 — Developer Preview 0.1.0

A first preview may consist of research documentation and diagnostic tools rather than a bootable operating system.

Potential deliverables:

- Windows 11 setup documentation.
- Device inspection tools.
- Boot-chain research.
- XNU feasibility report.
- A loader prototype only if one is implemented and tested.

A release must clearly identify what works, what has not been tested, and what is not supported.

Development principles

1. Never describe a planned feature as implemented.
2. Never label an untested image as bootable.
3. Preserve device data and security during initial research.
4. Keep proprietary Apple binaries out of the repository.
5. Prefer reproducible evidence over assumptions.
6. Document limitations honestly.
7. Use Windows 11, 64-bit, as the supported development environment.

Current milestone

Milestone: Establish a documented, reproducible Windows 11 research environment.

Current achievement: Initial repository and research documentation.

Next objective: Verify the device's reported properties and document the Windows 11 toolchain.
