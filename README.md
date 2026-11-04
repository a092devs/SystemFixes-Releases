# System Fixes

Signed builds of **System Fixes**, a LibXposed module for the ported OxygenOS 16 build on the
Poco F7 (`onyx`).

The module corrects the parts of the port that do not follow the hardware or the settings: it
never invents signal, never forces a network type and never overrides a per-app choice. Every
indicator is driven by the state the ROM itself publishes.

## What it fixes

- **Lock screen notifications** — notifications posted before the keyguard appeared are kept on
  the lock screen. The per-app switch, do-not-disturb, secret visibility, children mode and
  security lock mode still apply.
- **Contact save account** — remembers the account your last new contact was saved to, so the next
  new contact opens already set to that account instead of asking again. "This device", SIM and the
  other accounts stay available in the picker.
- **Vo5G / VoNR** — the Vo5G glyph follows the live voice radio on each SIM, and the VoNR switch is
  visible and usable for SIM 2 as well as SIM 1. Nothing is shown when voice is not actually on NR.
- **5G+ / 5G++** — shown only from the real aggregated NR carrier count, and only while the modem
  is actually aggregating. The standard 5G glyph stays until then.
- **My Files capacity** — the 512 GB variant reports 512 GB instead of 1.00 TB.
- **Screen Attention** — grants Android System Intelligence camera access and enables adaptive
  attention.
- **Display density** — any DPI from 280 to 640, applied through WindowManager and kept across
  restarts. Reset at any time.
- **App icon** — hide or show the drawer entry; the LSPosed settings entry keeps working either
  way.
- **In-app updates** — the app checks this repository, shows the changelog and hands the signed
  APK to the system installer.

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

## Scope

The module is declared for:

```
com.android.systemui
com.android.phone
com.oneplus.filemanager
com.android.contacts
```

The scope is fixed at install time, so changing it needs an uninstall and reinstall, not an
in-place update.

## Notes

- This repository carries signed APKs and their release notes only; the source repository is
  private.
- Turning the module off in the manager restores the ROM's own behavior for everything it hooks.
  Settings you changed in the app itself, such as display density, stay in effect until you reset
  them in the app.
