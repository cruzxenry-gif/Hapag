# Hapag 0.8.3 validation

This testing update packages the reviewed Today polish: directional glass cards/navigation using existing Haze, stronger Remaining hierarchy, continuous macro bars, nullable-only 25/50/25 macro fallbacks, meal-type chips/icons, two-line titles and positive-only meal cost. Today respects Scaffold bottom insets so meals clear the floating navigation. No new dependencies or schema/backup changes.

## Review and packaging boundary

The UI code passed 69 host tests with zero failures/errors/skips, zero lint issues, native API 35 Today/last-meal navigation-clearance acceptance and phone/expanded native render inspection. The scoped independent Impeccable review returned ship for reviewed APK `17bedc039aff64ff7c8614da89a2c9e8f5f64d64a58c07918cb462c640e427e9`. Its source-backed documentation checkpoint passed. Numeric/demo meal fixtures occur only in tests, not production seed data.

For this installable release, versionCode 10 / versionName 0.8.2 was changed only to 11 / 0.8.3. Every main source/resource/asset file is SHA-256-identical to that reviewed code, and the build configuration differs only in those two values. The version-only bridge records these checks. The new package `9623bd06b045becdb59000f60916d6c4ceeb043ced56eba2df8d81f9b118b033` was rebuilt and linted. Earlier native screenshots remain evidence for the identical reviewed UI code before this version bump; they are not represented as new screenshots of the version 11 binary. See version bridge (retained in workspace) and Today review (retained in workspace).

Same package ph.hapag and retained development signer, min API 26 / target 35, schema 3 and backup format 2 (imports 1/2). Existing records and explicit macro targets are preserved. Install over existing Hapag to retain the diary. See [backup format](BACKUP-FORMAT.md).

## Packages

| Artifact | Bytes | SHA-256 |
| --- | ---: | --- |
| Hapag-0.8.3-debug.apk | 62360866 | `9623bd06b045becdb59000f60916d6c4ceeb043ced56eba2df8d81f9b118b033` |
| Hapag-0.8.3-debug.zip | 37191611 | `628595842a54320ad5954bc3772b71677c2834bd3580c9eb46cfe04910266bf4` |
| Hapag-0.8.3-arm64-debug.apk | 29903675 | `6a2489526120b450b13df74fb02e48acb11593d0c13f9674d5355371dc268cfd` |

Both APKs pass signer/version/API/permission and 16 KiB alignment checks. The ARM64 package retains byte-identical code/resources/model entries; ZIP CRC passes and contains a byte-identical universal APK. Extract ZIP before installation. These remain debug builds. No physical ARM64 runtime, frame-time, full TalkBack or app-wide device-matrix certification is claimed. Public-download verification follows publication.

## Public downloads

All three public raw downloads were fetched after publication and matched the byte counts and SHA-256 hashes above. The downloaded ZIP passes CRC and contains one byte-identical universal APK. Binary artifact commit: `f415f61a103e15c1ba4360f095046ebaf8c9f549`. The artifact branch retains download verification; the local copy (retained in workspace) records the same checks.

[Public download verification](DOWNLOAD-VERIFICATION.json)
