iOSintosh Loader

Purpose

This directory is reserved for source code related to a future experimental loader for the Motorola Moto G60 (XT2135-2).

The loader's purpose would be to investigate whether a supported boot path can be established for research into running the genuine Apple XNU kernel.

Current status

No loader has been implemented.

This directory currently contains documentation only. There is no functional executable, EFI application, boot image, or verified kernel-loading procedure.

Before implementation

The following questions must be investigated:

- Which boot protocol does the device support?
- What image format and entry point are required?
- What security restrictions does the bootloader enforce?
- What CPU state and memory layout must be established?
- How will the loader obtain the hardware description?
- What early debugging interface is available?
- How can failures be diagnosed and recovered from safely?

Implementation principles

- Develop and test with Windows 11, 64-bit, as the supported host environment.
- Keep experimental code separate from verified tooling.
- Document dependencies and build instructions.
- Validate input sizes and image metadata before processing.
- Do not assume that an image is bootable because it compiles.
- Never label an untested image as functional.
- Do not include proprietary Apple kernel or firmware binaries in the repository.

Proposed future files

These are possibilities, not implemented components:

src/loader/
├── README.md
├── design.md
└── src/

The actual language, build system, and source layout should be selected after the boot protocol and loader requirements are better understood.

Current milestone

Document the loader's requirements before writing code that assumes a particular boot mechanism.
