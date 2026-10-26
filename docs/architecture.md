iOSintosh System Architecture

1. Overview

iOSintosh is an experimental research project investigating the feasibility of running the genuine Apple XNU kernel on the Motorola Moto G60 (XT2135-2).

The project is designed around a Windows 11 development environment.

Current status: Architecture planning and documentation. No working XNU bootloader or verified bootable image exists.

This document describes proposed components, their responsibilities, and the research needed before implementation.

2. High-Level Architecture

The proposed architecture consists of five main components:

+--------------------------------------------------+
|              Windows 11 Development              |
|                                                  |
|  +----------------+  +-------------------------+ |
|  | Device Tools   |  | Firmware Analysis Tools | |
|  | ADB / Fastboot |  | Metadata / File Checks  | |
|  +-------+--------+  +------------+------------+ |
|          |                        |              |
+----------|------------------------|--------------+
           | USB                    | Local files
           v                        v
+--------------------------------------------------+
|          Motorola Moto G60 — XT2135-2            |
|                                                  |
|  +--------------------------------------------+  |
|  | Existing Device Boot Chain                |  |
|  +---------------------+----------------------+  |
|                        |                         |
|                        v                         |
|  +--------------------------------------------+  |
|  | Future Experimental Loader, If Feasible    |  |
|  +---------------------+----------------------+  |
|                        |                         |
|                        v                         |
|  +--------------------------------------------+  |
|  | XNU Kernel Compatibility Investigation    |  |
|  +--------------------------------------------+  |
|                                                  |
+--------------------------------------------------+

Diagram status: Conceptual. It does not represent a working implementation or a verified boot path.

3. Component A — Windows 11 Tools

The Windows development environment is intended to provide tools for:

- Inspecting connected Android devices.
- Collecting ADB and Fastboot diagnostic output.
- Recording device and bootloader properties.
- Inspecting user-supplied firmware archives.
- Checking file hashes and metadata.
- Organizing research logs and test results.

The first tools should be read-only wherever practical.

The proposed command names below are examples for future software, not existing commands:

iosintosh.exe inspect
iosintosh.exe verify <file>
iosintosh.exe devices

A future verification command must explain precisely what it checks. File integrity alone cannot prove kernel compatibility.

4. Component B — Device Boot Chain

The Moto G60 uses a device-specific boot chain. Its behavior and security restrictions must be researched before attempting to load a different kernel.

Research should establish:

- Which boot interfaces are supported.
- Which image formats are accepted.
- How the bootloader validates images.
- What security restrictions apply.
- What CPU state and memory layout are provided at kernel entry.
- How the kernel receives hardware information.
- What recovery methods are available if an experiment fails.

These details must be verified for the exact device variant. Compatibility must not be assumed from another Motorola or Qualcomm device.

5. Component C — Experimental Loader

A custom loader is a possible future research component, not a confirmed solution.

If a viable loading path exists, a loader may need to:

- Accept a documented image format.
- Validate image boundaries and required metadata.
- Establish the required memory layout.
- Prepare the execution environment.
- Provide required hardware descriptions.
- Transfer control to the kernel entry point.
- Report failures through an available debugging interface.

The exact requirements depend on the device boot protocol and the kernel's expectations.

No loader implementation should be described as functional until it has been built, tested, and its behavior documented.

6. Component D — XNU Compatibility Research

XNU is Apple's kernel. Running it on the Moto G60 would require substantially more than obtaining an Apple kernel binary.

The investigation must consider:

- ARM64 CPU initialization.
- Exception levels and processor state.
- Memory management.
- Interrupt controllers and timers.
- Hardware descriptions and device discovery.
- Early serial or other debugging support.
- Storage, USB, display, and power management.
- Platform-specific drivers and components.
- Required userspace and supporting system services.

The Moto G60 is not an Apple-supported hardware platform. The feasibility and amount of required work remain unknown.

7. Component E — Diagnostics and Evidence

Every experiment should produce a record of what was attempted and what actually happened.

Useful records include:

- Windows 11 version.
- Tool versions.
- Exact device model.
- Commands used.
- Relevant output and errors.
- File hashes where appropriate.
- Test conditions.
- Expected versus observed behavior.
- Recovery steps, if needed.

Do not publish serial numbers, credentials, signing keys, or other sensitive information.

Use these labels in technical documentation:

- Verified: Reproduced or confirmed with reliable evidence.
- Likely: Supported by evidence but not conclusively confirmed.
- Hypothesis: Proposed explanation that still needs testing.
- Planned: Not implemented or tested yet.

8. Proposed Data Flow

The intended research workflow is:

1. Use Windows 11 tools to inspect the device.
2. Record the device's actual properties and bootloader state.
3. Research the boot protocol and relevant security restrictions.
4. Analyze authorized files without modifying the phone.
5. Document the loader requirements.
6. Evaluate XNU's platform requirements.
7. Consider a prototype only if the research identifies a plausible, testable path.
8. Publish results with evidence and clearly stated limitations.

This workflow prioritizes understanding and reproducibility before potentially risky device operations.

9. Security Boundaries

The project must respect the device's boot security.

- ADB and Fastboot do not bypass bootloader security.
- Enabling OEM unlocking does not itself unlock the bootloader.
- Unlocking may erase user data.
- An experimental image must never be assumed safe or bootable.
- No image should be flashed without a validated procedure and recovery plan.
- Proprietary Apple firmware and kernel binaries must not be committed to the repository unless redistribution is permitted.

10. Proposed Image Format

The name "iosintosh-g60-efi.img" is a proposed filename only.

The ".img" extension does not establish that a file is an EFI executable, that it follows the Moto G60's boot protocol, or that the device can load it.

The actual image format and loading method must be determined through research before implementation.

11. Implementation Status

Component| Status
Windows 11 documentation| Started
Device identification workflow| Documented; not yet verified on the user's device
Boot-chain investigation| Planned
Loader design| Preliminary concept
Loader implementation| Not implemented
XNU compatibility| Unknown
Verified bootable image| None
Successful XNU boot| Not demonstrated

12. Next Milestone

The next milestone is to establish a reproducible Windows 11 development environment and collect basic device information without modifying the phone.

Only after those results are documented should the project move toward more detailed boot-chain research.
