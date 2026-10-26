iOSintosh Images and Diagrams

Purpose

This directory is intended for project-related images, architecture diagrams, and visual documentation.

Guidelines

- Use images that help explain the project or document a real test.
- Prefer original diagrams and screenshots created for iOSintosh.
- Add a short explanation of what each image demonstrates.
- Identify mockups and conceptual illustrations as such.
- Never present a concept image as proof of a successful boot.
- Do not include proprietary Apple assets unless their use and redistribution are permitted.
- Check screenshots for personal information, device serial numbers, and other sensitive details before publishing.

Suggested organization

images/
├── README.md
├── architecture/
├── hardware/
└── test-results/

These subdirectories can be created when they are needed.

Evidence standards

Images documenting test results should include enough context to understand what was tested.

A screenshot showing a loader starting does not, by itself, prove that the XNU kernel has successfully booted.

Current status

No successful XNU boot has been demonstrated on the Moto G60. Any future images must accurately represent the project's actual progress.
