iOSintosh Project Status

Status: Early research and documentation
Target device: Motorola Moto G60 (XT2135-2)
Target chipset: Qualcomm Snapdragon 732G
Development environment: Windows 11

Current State

iOSintosh is an experimental project investigating whether Apple's XNU kernel can be adapted to run on the Motorola Moto G60.

The project is not currently a working iOS port.

- [x] Target device identified
- [x] Initial project documentation created
- [x] Development roadmap documented
- [x] Repository contribution and security guidelines added
- [ ] Device hardware and boot-chain research completed
- [ ] Compatible boot environment demonstrated
- [ ] Required platform-specific kernel support implemented
- [ ] Kernel boot feasibility demonstrated on the target device
- [ ] Minimal userspace feasibility investigated

Important Limitations

Creating documentation or placeholder source files does not establish that XNU can boot on this hardware.

The project does not currently provide a verified, bootable iOSintosh image. Any proposed image filename or boot command must be treated as untested until a reproducible implementation exists.

ADB and Fastboot do not bypass bootloader security. Enabling OEM unlocking in Android settings does not itself unlock the bootloader.

Development Priorities

1. Gather non-destructive device information.
2. Research the Moto G60 boot chain and hardware requirements.
3. Investigate XNU's platform dependencies and licensing constraints.
4. Design and test components incrementally.
5. Document evidence and reproducible results before claiming progress.

Testing Principles

- Record actual test results rather than assumptions.
- Separate successful host-side checks from device-level tests.
- Never describe a kernel as booting unless there is reliable evidence.
- Avoid destructive device operations until recovery procedures are understood.

Windows Support

Windows 11 is the intended development environment for this project. Windows 10 is not a project target.

Linux-based CI jobs may still be used for repository checks that do not require a Windows host or the physical device.
