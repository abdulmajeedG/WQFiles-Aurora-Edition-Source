# WQFiles — Aurora Edition (Modern Dark)

Design-only fork of [kolbicz/WQFiles](https://github.com/kolbicz/WQFiles),
published here so the original developer can review and adopt the redesign
if wanted. No obligation; this repository can be archived at any time.

## Contents

| File | Description |
|---|---|
| `AuroraSource.zip` | Complete Aurora Edition source (Objective-C/UIKit, 17 localizations, tests, icons, `build.sh`). SHA-256: `da20522d243547a9525118c37fd2280339876ebdee1ed559f8a945fd28e5266f` |
| `WQFiles-Aurora-Edition-0.1.0-test12.ipa` | Ad-hoc signed test build produced from that exact source. SHA-256: `588751c3ef467c9c833dd298ec798d5f7292d108ad651fdb08e6d15b821605e7` |

## What it changes (presentation only)

- Dark-only Modern Dark design system with Blue and Red accent variants.
- New home dashboard: circular storage gauge with real measured values,
  category chips, floating tool cards, recent files, collapsible extras.
- Themed tab bar and navigation chrome; four switchable app icons
  (Cleaning / Files / Storage / Apps) via `setAlternateIconName:`.
- All original behaviour preserved: worse_query and container access,
  file operations, backup verification, SQLite integrity checks,
  deletion confirmations and the App Group entitlement
  (`group.cz.kolbi.wqfiles`).

## Build

1. Unzip `AuroraSource.zip`.
2. On macOS with a stable Xcode that provides the iPhoneOS 26 SDK, run
   `bash ./build.sh` (runs the upstream regression preflight and gates,
   then produces `WQFiles.ipa`).
3. Re-sign the IPA with a provisioning profile that preserves the App Group
   before installing on a device.

## Verification notes

- 44 Python tests, all Foundation fixtures, runtime localization checks
  (17 languages), strict arm64 compile/link and the build artifact gates
  passed in the hosted macOS build that produced the IPA above.
- The IPA is ad-hoc signed: it contains no certificates or profiles and
  must be re-signed by whoever installs it.
- Compatibility was exercised on one iPhone only; universal device support
  is not claimed.

## License

GPL-3.0-or-later. Original application © kolbicz.
worse_query © Taj C (forcequit). Aurora design/UI by @abdulmajeedG.
