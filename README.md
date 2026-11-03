# System Fixes

Signed builds of **System Fixes**, a LibXposed module for the ported OxygenOS 16 build on the
Poco F7 (`onyx`).

Lock screen notifications · real Vo5G / VoNR · carrier-aggregation 5G+ · My Files 512 GB ·
Screen Attention · any-DPI screen size · app icon toggle · in-app updates.

## Install

1. Download `SystemFixes.apk` from the
   [latest release](https://github.com/a092devs/SystemFixes-Releases/releases/latest).
2. Install it and enable the module in your LSPosed-compatible manager.
3. Reboot.

Open System Fixes from the app drawer, or from the manager, to turn fixes on or off.

## Updates

The app checks this repository's latest release, shows the changelog and hands the signed APK to
the system installer. Builds up to v2.6 used a different signing key and cannot be updated in
place — uninstall them first.

## Notes

This repository carries signed APKs and their release notes only; the source repository is private.
The module's scope (`com.android.systemui`, `com.android.phone`, `com.oneplus.filemanager`) is fixed
at install time, so changing it needs a reinstall.
