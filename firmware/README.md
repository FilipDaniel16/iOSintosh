Firmware Research and Handling

Purpose

This directory documents how firmware-related research may be organized for iOSintosh.

The project investigates the feasibility of running the genuine Apple XNU kernel on a Motorola Moto G60 (XT2135-2).

No firmware package or kernel image in this project is verified to boot on the target device.

Firmware files

Do not commit proprietary Apple firmware, copyrighted kernel binaries, private keys, or other restricted files to this repository.

Firmware archives and extracted files should remain in a local research directory unless redistribution is clearly permitted.

The repository may contain documentation, scripts, and metadata that help users inspect files they are authorized to use.

IPSW archives

An IPSW is an Apple software distribution archive. Its contents, structure, and compatibility depend on the particular device and software release.

Possessing an iOS 18 IPSW does not establish that its kernel can boot on the Moto G60.

Before any file is considered useful, research must establish:

- The archive's source and integrity.
- Which device and software version it targets.
- Which components it contains.
- Whether a particular component can legally be used for the intended research.
- Whether the component's architecture and platform requirements match the proposed loader.

Local file organization

Researchers may keep authorized files outside the Git repository, for example:

C:\iOSintosh-research\
├── downloads\
├── extracted\
├── analysis\
└── logs\

This is an example directory layout, not a required installation path.

Do not publish private identifiers, credentials, signing keys, or other sensitive information in research logs.

Verification

Future tooling may check file structure, hashes, and metadata.

A matching hash can establish that two files are identical, but it does not prove that a file is compatible with a device or safe to boot.

Any verification result must state exactly what was checked and what remains unknown.

Current status

- [x] Firmware-handling policy documented.
- [ ] Required file formats identified.
- [ ] Metadata inspection workflow implemented.
- [ ] Any proposed compatibility checks validated.

No proprietary firmware or verified bootable image is supplied by this project.
