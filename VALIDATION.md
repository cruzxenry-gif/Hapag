# Hapag 0.8.0 validation

Package `ph.hapag`, versionCode 8, minimum API 26/target 35. This build implements the user's dark-glass Today/Add meal reference and confirmed editable macro goals. The existing development signer is retained.

## Changes and data compatibility

Today uses the near-black/green canvas, static green/warm blooms, a calorie ring with remaining intake, colored macro progress, compact meal rows and gold budget progress. Water follows the budget. Compact navigation retains a central sage Add action; tablets retain the rail. Dark remains the default; appearance can be changed from Me. The date control opens Android's calendar.

Add opens a real meal-draft sheet with Filipino occasion labels, offline food/recipe search, reviewed portions and visible grams/sources, whole-meal cost, frequent/saved suggestions and explicit saving. Multi-food drafts use one shared cost. Quantity changes update both calories and macros, preserving fractional input. Alternate text, recipe, label and reference-photo paths remain available. Force-stop/reboot draft persistence is not added by this redesign.

Schema 2→3 adds nullable protein/carbs/fat targets. Existing targets and records remain intact; unset macros have no invented progress. Targets are user-entered, not personalized nutrition advice. Backup exports use format 2, with version-1 and version-2 import support. Missing legacy macro targets import as unset. See [backup format](BACKUP-FORMAT.md). Earlier app builds accept only backup format 1.

## Build and functional evidence

The final host reports record **66 tests, zero failures/errors/skips**, and **zero lint issues**. They cover schema 1/2 upgrades, macro entry/validation/persistence/clearing, current and legacy backup import, invalid-target rejection, source/snapshot/cost invariants and the affected logging/settings flows. The app build and instrumentation build complete successfully.

All final native captures name universal APK `6d9e0c8b199d8a522a052aeb2e2c4f8b746b3b5ca42bf60e033dabfaa28330a0`. There are **36 manifest-bound frames**, opened by the build thread, across API 35 dark/light phone, 200% text, tablet and narrow phone, plus API 29 dark phone. Each main capture case checks real portion math, typed cost, keyboard visibility, Back hiding the keyboard without losing the sheet, discard/Keep editing, single-commit saving and the goal editor. Test-only Demo records are absent from the production starter catalog.

API 29 MealFlowTest, RecipeFlowTest and NavigationFlowTest each pass on this app build, retaining edit/delete/recipe-snapshot/draft-restoration/settings assertions. The sheet confirmation callback retains stable identity as draft state changes, covered by host regressions. Capture setup now scrolls to actual controls instead of issuing an oversized raw swipe that moved the parent sheet, and waits for the focused native window to draw. Earlier wrong-state frames and failed helpers are excluded from the final manifest. Native evidence uses AOSP x86_64 software emulators with SwiftShader. Physical-device performance, full TalkBack, gesture-navigation and camera/provider certification are outside this pass.

The independent full review identified one portion-input focus issue; the correction adds a theme-colored caret and visible focused outline without changing quantity behavior. The final verdict scores that listed correction at its stated scope.

The capture manifest (retained in workspace), source proofs, passing logs, source scope (retained in workspace), final independent review (retained in workspace) and source-backed design records are retained in the workspace. The attached user image and approved plan define the visual target; native insets, scalable text and touch targets govern device adaptation.

## Packages

| Artifact | Bytes | SHA-256 |
| --- | ---: | --- |
| Hapag-0.8.0-debug.apk | 62,412,078 | `6d9e0c8b199d8a522a052aeb2e2c4f8b746b3b5ca42bf60e033dabfaa28330a0` |
| Hapag-0.8.0-debug.zip | 37,181,510 | `2a0a6501d5f3902e08fee9332ba8fac67a1e780934f688626a13406f1bbf2fa9` |
| Hapag-0.8.0-arm64-debug.apk | 29,903,675 | `03ecb19f370ffa5ea4543c38cfac2fdc05b712c72178c508995dd12d26aeca72` |

Both APKs verify with signer SHA-256 `a4c8e496c0d550a52ec823f3869c61f7e9abc9a38259f06254ef94ebd4ffbc5f` and pass 16 KiB alignment. Package/version/API values and absent Internet/network-state permissions were checked. The optional ARM64 package retains identical included code/resources/model entries and removes other-processor libraries; physical ARM64 runtime is not certified. The ZIP contains one byte-identical universal APK and passes CRC.

Install over existing Hapag to keep the diary. Extract the APK before using ZIP. These remain development builds. Public-download verification is recorded after publication.

## Public downloads

All three public raw downloads were fetched after publication and matched the byte counts and SHA-256 hashes above. The downloaded ZIP passes CRC and contains one byte-identical universal APK. Binary artifact commit: `4a3601baffe26d82687206b663f44c79fdc26062`. The artifact branch retains download verification; the local copy (retained in workspace) records the same checks.

[Public download verification](DOWNLOAD-VERIFICATION.json)
