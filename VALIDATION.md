# Hapag 0.8.2 validation

Food rows and optional weight entries now reuse Home's GlassCard: a translucent semantic surface, 24dp corners and a fine outline. Foods keep their names, portions, grams, kcal and sources, with separate native Bookmark and Add controls. Weight values use title-large above the quieter unchanged date. The cards use translucency, without a new per-row backdrop-blur effect.

## Scope and compatibility

Production changes are confined to FoodsScreen.kt, ProgressScreen.kt's weight entries and version 10 / 0.8.2. The corrected navigation, Home, recipes, chart and weekly table retain their existing implementation. No nutrition, dependency, schema or backup change. Same package ph.hapag, minimum API 26 / target 35 and existing development signer. Install over existing Hapag to keep the diary. Schema 3 and backup format 2 (imports 1/2) remain; see [backup format](BACKUP-FORMAT.md).

## Evidence

66 host tests pass with zero failures/errors/skips; lint reports zero issues. Five API 35 native cases pass on the actual activity: dark/light phone, 320dp narrow phone, 200% text and expanded landscape. They exercise weight-card display, saved-food state, a long custom food/source, missing-search recovery and the library-to-editor-to-picker route, confirming that adding another food retains both items. The dark phone also exercises the empty weight state and explicitly saves its first check-in through the native dialog. 22 native screenshots are opened and bound by the capture manifest to APK 02185fb3246871ef4c7de363efbed6cce2644abd863e1d1154a7ec2e80f4cb43. Demo custom foods and weight records are disposable test fixtures, never shipped seed records or user history. Weight-only fixture values are documented as synthetic even though the UI itself displays their numeric values normally.

Analytical compositing bounds over the existing atmosphere give supporting text at least 6.28:1 and primary icons at least 6.93:1 in either theme. This is a color calculation, not physical-device accessibility certification. The independent Impeccable review is scoped to these food/weight surfaces and their affected paths. See review (retained in workspace), capture manifest (retained in workspace), design checkpoint (retained in workspace) and workspace logs.

Native evidence uses AOSP x86_64 software emulation with animations disabled and extended emulator startup timeouts. No physical frame-time, full TalkBack, gesture-navigation, camera/provider or ARM64 runtime certification is claimed. Prior versions' evidence remains tied to their own artifacts; there is no fresh API 29 device-matrix claim for this pass.

## Packages

| Artifact | Bytes | SHA-256 |
| --- | ---: | --- |
| Hapag-0.8.2-debug.apk | 62,360,866 | `02185fb3246871ef4c7de363efbed6cce2644abd863e1d1154a7ec2e80f4cb43` |
| Hapag-0.8.2-debug.zip | 37,181,936 | `8cd178721c56c21d20098080f0f2dca54a07888689452d104cdf1211563dab6d` |
| Hapag-0.8.2-arm64-debug.apk | 29,903,675 | `a55d4e571e9fc2ffd2d6d3c2446d81049c7cb2c00f8dc18d2910dc4bd1aec147` |

Both APKs pass signature, version/API/permission and 16 KiB alignment checks using the retained development signer. The ARM64 package retains byte-identical code/resources/model entries. The ZIP passes CRC and contains one byte-identical universal APK; extract it before installing. These are debug builds. Public-download verification follows publication.

## Public downloads

All three public raw downloads were fetched after publication and matched the byte counts and SHA-256 hashes above. The downloaded ZIP passes CRC and contains one byte-identical universal APK. Binary artifact commit: `2ca504f7ed69f30e5196b267cf9825b571427d4f`. The artifact branch retains download verification; the local copy (retained in workspace) records the same checks.

[Public download verification](DOWNLOAD-VERIFICATION.json)
