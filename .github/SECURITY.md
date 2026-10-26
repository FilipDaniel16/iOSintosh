Security Policy

Project Status

iOSintosh is an experimental research project investigating the feasibility of running Apple's XNU kernel on the Motorola Moto G60 (XT2135-2).

A successful XNU boot has not been demonstrated. No experimental image should be assumed to be functional or safe.

Supported Versions

The project is under active development. Until versioned releases exist, security fixes and reports should reference the affected Git commit whenever possible.

Reporting a Vulnerability

If you discover a potential security vulnerability in project code or tooling:

1. Do not publish sensitive exploit details before the issue has been assessed.
2. Use GitHub's private vulnerability reporting feature if it is enabled for this repository.
3. If private reporting is unavailable, open a public issue containing only a high-level description and request a private reporting channel before sharing sensitive details.

Do not include passwords, access tokens, private keys, or personal device identifiers in reports.

Device Safety

- Do not flash or boot unverified images on a physical device.
- Bootloader unlocking may erase user data and can affect device security.
- Never treat enabling OEM unlocking in Android settings as proof that the bootloader has been unlocked.
- Keep backups of important data before any future device-modifying experiments.
- Clearly document potentially destructive commands and their risks.

Firmware and Licensing

Do not commit proprietary Apple firmware, kernel binaries, signing keys, or other restricted material without appropriate authorization. Prefer documentation, original source code, and legally distributable research materials.

Responsible Disclosure

Please allow reasonable time to investigate and address a confirmed vulnerability before publicly disclosing technical details.
