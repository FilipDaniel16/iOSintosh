Windows 11 Development Setup Guide

Purpose

This guide prepares a Windows 11 computer for non-destructive research on the Motorola Moto G60 (XT2135-2).

It does not install iOS, unlock the bootloader, or create a working XNU image.

1. Host Requirements

- Windows 11
- Internet connection
- USB data cable compatible with the Moto G60
- Sufficient disk space for development tools and diagnostic logs
- Administrator access only when required by a trusted installer

2. Initial Preparation

Before connecting the phone:

- [ ] Install pending Windows security updates.
- [ ] Use a trusted USB data cable.
- [ ] Back up important files on the laptop.
- [ ] Create a project folder for research notes and logs.
- [ ] Do not download or run experimental boot images.

3. Android Platform Tools

Obtain Android SDK Platform Tools from the official Android developer website.

Official download page: https://developer.android.com/tools/releases/platform-tools

After downloading:

1. Extract the archive to a known folder, such as "C:\Android\platform-tools".
2. Open Windows Terminal or PowerShell.
3. Change to the extracted directory.
4. Run ".\adb.exe version" to check that ADB starts.

This command checks the host tool; it does not modify the phone.

4. Initial USB Connection

On the phone:

1. Open Android Settings.
2. Open Developer options.
3. If USB debugging is already enabled, connect the phone.
4. Review the computer authorization prompt on the phone, if one appears.

Only authorize your own trusted computer.

In PowerShell, run:

.\adb.exe devices

If the phone appears as "device", ADB communication is available.

If it appears as "unauthorized", unlock the phone and review its authorization prompt.

If no device appears, check the cable, USB port, connection mode, and Windows device drivers.

Do not share device serial numbers in public issue reports.

5. Record Basic Device Information

If ADB is working, the following commands collect basic Android properties:

.\adb.exe shell getprop ro.product.model
.\adb.exe shell getprop ro.build.version.release
.\adb.exe shell getprop ro.build.fingerprint

The build fingerprint can contain device and software identification details. Keep the full output private unless you have reviewed it before sharing.

These commands query Android properties; they do not unlock the bootloader or flash firmware.

6. Bootloader Safety

Enabling OEM unlocking in Android settings is not the same as unlocking the bootloader.

Before any future bootloader operation:

- [ ] Confirm official unlock eligibility for the exact device variant.
- [ ] Understand whether unlocking will factory-reset the phone.
- [ ] Back up important data.
- [ ] Research a reliable recovery procedure.
- [ ] Verify the source and integrity of any required files.
- [ ] Review the exact command and its effects before running it.

Do not use "fastboot flash", "fastboot erase", or experimental "fastboot boot" commands as part of initial setup.

7. Save Research Results

Create a private local folder for diagnostic output and notes.

Record:

- Date and time of each test
- Windows version
- Tool versions
- Commands executed
- Actual results
- Errors or unresolved questions

Redact personal identifiers before sharing logs publicly.

8. Initial Milestone

The first milestone is complete when:

- [ ] ADB runs on Windows 11.
- [ ] The phone is detected, if USB debugging is available.
- [ ] Basic device information has been recorded privately.
- [ ] No device partitions have been modified.
- [ ] No experimental image has been flashed or booted.

Passing these checks establishes a basic research environment only. It does not demonstrate that XNU can boot on the Moto G60.
