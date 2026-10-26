Decision 0001: Project Scope and Research Strategy

- Status: Accepted as the initial research plan
- Date: 2026-10-26

Context

iOSintosh investigates the feasibility of running Apple's XNU kernel on a Motorola Moto G60 (XT2135-2), powered by the Qualcomm Snapdragon 732G.

The device was designed for Android, and a successful XNU boot has not been demonstrated by this project.

The project therefore begins with research and non-destructive diagnostics rather than attempting to boot an experimental image.

Decision 1: Development Host

Decision: Windows 11 is the intended development environment.

The project will not target Windows 10.

Some automated repository checks may run on Linux-based CI infrastructure when they do not require the Windows development host or physical device.

Decision 2: Initial Development Phase

Decision: Begin with documentation, hardware research, and non-destructive diagnostics.

Initial work will focus on:

1. Confirming device identity and installed software.
2. Understanding the device boot chain.
3. Finding relevant device-specific source code.
4. Investigating XNU's platform requirements.
5. Identifying licensing and technical constraints.

Decision 3: Experimental Images

Decision: No file will be described as a bootable iOSintosh image until it has a real implementation and supporting evidence.

A filename, placeholder, or proposed Fastboot command is not proof that an image is functional.

No experimental image should be flashed or booted on the physical device without a reviewed implementation, a clear understanding of the risks, and a recovery plan.

Decision 4: Device Security

Decision: Avoid destructive device operations during initial research.

ADB and Fastboot are diagnostic and device-management tools; they do not bypass the device's bootloader security.

Enabling OEM unlocking in Android settings does not itself unlock the bootloader.

Any future unlocking or flashing procedure must be reviewed separately, including potential data loss and recovery requirements.

Decision 5: Source Code and Licensing

Decision: Prefer original code, public technical documentation, and legally distributable source materials.

Do not commit proprietary Apple firmware, kernel binaries, signing keys, or other restricted materials without appropriate authorization.

Consequences

This strategy may delay device-level experiments, but it improves reproducibility, protects user data, and makes technical blockers easier to identify.

The feasibility of running XNU on the target device remains an open research question.

Reconsideration Criteria

This decision may be revisited when credible evidence establishes:

- The relevant boot-chain requirements.
- A technically plausible loading strategy.
- The required platform-specific kernel support.
- A safe and documented testing and recovery procedure.
