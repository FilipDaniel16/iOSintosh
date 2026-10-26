iOSintosh Testing Strategy

1. Purpose

This document defines how iOSintosh components and research findings should be tested.

The project investigates the feasibility of running the genuine Apple XNU kernel on the Motorola Moto G60 (XT2135-2).

Current status: Research and documentation. No successful XNU boot has been demonstrated, and no verified bootable image exists.

2. Development Environment

The supported development environment is Windows 11, 64-bit.

Tests should record:

- Windows version.
- Tool and dependency versions.
- Target device model.
- Exact commands executed.
- Expected and observed results.
- Error messages.
- Steps required to reproduce the test.

3. Testing Stages

Stage A — Documentation

- [ ] Verify that setup instructions are understandable.
- [ ] Check that filenames and repository paths are correct.
- [ ] Confirm that unimplemented features are labelled as planned.
- [ ] Check that safety warnings are present where needed.

Stage B — Windows Tools

When a Windows 11 development environment is available:

- [ ] Confirm ADB version information can be retrieved.
- [ ] Confirm Fastboot version information can be retrieved.
- [ ] Verify that diagnostic commands produce understandable output.
- [ ] Test error handling when no device is connected.
- [ ] Ensure diagnostic output avoids exposing sensitive information.

Stage C — Device Identification

After connecting the Moto G60:

- [ ] Record the model reported by Android.
- [ ] Record relevant device properties.
- [ ] Record available bootloader information.
- [ ] Preserve complete command output and errors.
- [ ] Check that results are reproducible.

Initial identification must not require unlocking the bootloader, erasing data, or flashing an image.

Stage D — File Inspection

If file-inspection tools are implemented:

- [ ] Test behavior with a valid sample file.
- [ ] Test behavior with an empty file.
- [ ] Test behavior with a truncated or malformed file.
- [ ] Check file size and metadata validation.
- [ ] Confirm that integrity checks report exactly what they establish.
- [ ] Confirm that unsupported files fail safely.

Passing a file-integrity check does not establish that a kernel or image is compatible with the target device.

Stage E — Loader Research

Before any device-boot experiment:

- [ ] Document the boot protocol.
- [ ] Establish the expected image format.
- [ ] Document security requirements.
- [ ] Define the intended memory layout and kernel handoff.
- [ ] Establish a debugging method.
- [ ] Document recovery procedures.
- [ ] Review the risks before proceeding.

No experimental image should be considered bootable merely because it builds successfully.

Stage F — XNU Compatibility

Any claimed compatibility milestone must be supported by reproducible evidence.

A loader starting is not proof that XNU has started. A kernel reaching an early initialization stage is not proof that the operating system is fully functional.

Document the exact milestone achieved and any unresolved failures.

4. Evidence Labels

Use these labels consistently:

- Verified: Confirmed through a reproducible test or reliable documentation.
- Likely: Supported by evidence but not conclusively confirmed.
- Hypothesis: A proposed explanation that requires testing.
- Planned: Not yet implemented or tested.
- Failed: A test was performed and did not achieve its intended result.

Do not change a result to Verified without supporting evidence.

5. Safety Rules

- Keep the bootloader locked during initial research.
- Do not assume enabling OEM unlocking unlocks the device.
- Remember that bootloader unlocking may erase user data.
- Do not flash unverified images.
- Do not run commands that modify partitions without a documented procedure and recovery plan.
- Keep proprietary Apple firmware and kernel binaries out of the repository unless redistribution is permitted.

6. Test Report Template

Use this template for future test results:

Test name:
Date:
Windows version:
Device model:
Tool versions:

Objective:

Commands or steps:

Expected result:

Observed result:

Status: Verified / Likely / Hypothesis / Planned / Failed

Errors or limitations:

Reproduction instructions:

Do not include passwords, signing keys, device serial numbers, or other sensitive information in public reports.

7. Current Test Status

- [x] Initial testing strategy documented.
- [ ] Windows 11 tools verified.
- [ ] Device inspection completed.
- [ ] Boot protocol researched.
- [ ] File-inspection tooling tested.
- [ ] Loader implemented.
- [ ] XNU kernel boot demonstrated.

Current result: The project has a testing plan, but implementation and device testing remain future work.
