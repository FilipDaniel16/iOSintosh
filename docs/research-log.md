iOSintosh Research Log

Purpose

This log records research, experiments, observations, and technical decisions related to investigating XNU on the Motorola Moto G60 (XT2135-2).

Only record tests that have actually been performed. Planned experiments must be labeled as planned.

Project Environment

- Target device: Motorola Moto G60 (XT2135-2)
- SoC: Qualcomm Snapdragon 732G
- Development host: Windows 11
- Project status: Experimental research
- Verified successful XNU boot: No
- Verified bootable project image: No

Research Entry Template

Copy this section for each new investigation.

Entry: YYYY-MM-DD — Short title

Status: Planned / In progress / Completed / Blocked

Question:
What are we trying to establish?

Background:
What do we already know?

Method:
What sources, commands, or tests were used?

Results:
Record observed results only. Include relevant error messages when appropriate.

Evidence:
Link documentation, source code, logs, or other references.

Conclusion:
What can reasonably be concluded from the evidence?

Next steps:
What should be investigated next?

Safety notes:
Could the work affect device data, security, or recoverability?

---

Initial Research Entries

Entry: 2026-10-26 — Repository preparation

Status: Completed

Question:
Has the initial project documentation structure been established?

Results:
Initial documentation and contribution guidance have been added to the repository through the GitHub interface.

Conclusion:
The repository has a documentation foundation. This does not demonstrate kernel compatibility or successful booting.

Next steps:
Research the Moto G60 boot chain, hardware dependencies, available source code, and licensing requirements.

Entry: 2026-10-26 — Device diagnostics

Status: Planned

Question:
Can the Windows 11 development host communicate with the phone using standard Android debugging tools?

Method:
To be determined during the planned laptop session.

Results:
Not yet tested.

Safety notes:
Begin with non-destructive diagnostics. Do not unlock the bootloader, erase partitions, flash firmware, or boot an experimental image.

Evidence Standards

- Distinguish facts from hypotheses.
- Include sources for technical claims.
- Record failed experiments as well as successful ones.
- Do not claim that XNU booted without reproducible evidence.
- Do not describe placeholder files as functional implementations.
- Never publish passwords, private keys, or unnecessary device identifiers.

Current Technical Unknowns

- Exact boot-chain requirements for the target device variant.
- Available and applicable device-specific kernel source.
- Platform initialization requirements for XNU.
- Required drivers and hardware support.
- Feasibility of providing a suitable userspace.
- Licensing and redistribution constraints.

These are open questions, not confirmed solutions.
