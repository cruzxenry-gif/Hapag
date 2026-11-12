# Hapag 0.8.1 validation

The user reported that Today and Me selection highlights overlapped the curved floating navigation capsule and supplied a device screenshot. This update adds 8 dp inside the existing frosted capsule, giving native first/last selection indicators room inside its rounded edge. All four destinations and the central 60 dp Add remain. Today scroll clearance follows the measured navigation height; other destinations retain Scaffold padding. Narrow widths and enlarged text use native scrolling tabs when five 64 dp slots (scaled for font size) cannot fit inside 40 dp of gutters; expanded widths keep the rail.

## Scope and compatibility

Production changes are the compact navigation inset/test tag, earlier adaptation to native scrolling tabs when slots would crowd, scrolling-row height in HapagApp.kt, and version 9 / 0.8.1. The new NavigationCaptureTest exercises the actual activity. No data, nutrition, schema, backup or dependency changes. Same package ph.hapag, minimum API 26 / target 35 and development signer. Install over existing Hapag to keep the local diary. Schema 3 and backup format 2 (imports 1/2) remain. See [backup format](BACKUP-FORMAT.md).

## Evidence

66 host tests pass with zero failures/errors/skips; lint has zero issues. Five API 35 native navigation cases pass: dark/light phone, 320 dp narrow phone, 200% text and landscape expanded rail. Every case selects Today, Progress, Foods and Me, checks selected semantics, and opens/closes Add from Me. 28 native screenshot files show all compact selected states plus full Today/Me and four landscape rail states. Every file is opened and manifest-bound to APK 89231252f90762a1d1d1acc1d46d863106bca082002d22b074bad8d460cd9d4b. Crops are direct native screenshot crops, not design mockups. The user screenshot is retained as issue evidence. The independent review and design documentation check use these current files.

See capture manifest (retained in workspace), review (retained in workspace), design check (retained in workspace) and passing logs in the workspace. Older v0.8 tests/reviews remain evidence for their own builds, not newly rerun device flows. Native evidence is AOSP x86_64 software emulation, with animations disabled and extended emulator startup timeouts after the initial instrumented launch exceeded the software emulator’s startup window; no physical-device performance, full TalkBack, gesture-mode, camera/provider or ARM64 runtime certification is claimed.

## Packages

| Artifact | Bytes | SHA-256 |
| --- | ---: | --- |
| Hapag-0.8.1-debug.apk | 62,762,730 | `89231252f90762a1d1d1acc1d46d863106bca082002d22b074bad8d460cd9d4b` |
| Hapag-0.8.1-debug.zip | 37,187,778 | `cf86993a02f15edd7231162da4a8c2c2213c352864c8a76f4f1bec3533448411` |
| Hapag-0.8.1-arm64-debug.apk | 29,907,771 | `3565a158b6ea6437029a691d757fb758e75edd22dc3fd6509249ddb20e5b373b` |

Both APKs pass signature/version/API/permission and 16 KiB alignment checks using retained signer a4c8e496c0d550a52ec823f3869c61f7e9abc9a38259f06254ef94ebd4ffbc5f. ARM64 retained code/resources/model entries are byte-identical to the universal APK. ZIP CRC passes and it contains one byte-identical universal APK. Extract it before installing. These remain debug builds. Public-download proof is added after publication.

## Public downloads

All three public raw downloads were fetched after publication and matched the byte counts and SHA-256 hashes above. The downloaded ZIP passes CRC and contains one byte-identical universal APK. Binary artifact commit: `c141478f7bcf1475125ae68da4c148effea59517`. The artifact branch retains download verification; the local copy (retained in workspace) records the same checks.

[Public download verification](DOWNLOAD-VERIFICATION.json)
