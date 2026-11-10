# Hapag 0.7.0 validation

Package `ph.hapag`, versionCode 7, versionName 0.7.0, minimum API 26/target 35. This update extends the approved charcoal/soft-white/sage style through meal logging, Foods and saved recipes. Schema 2 and the existing development signer are retained.

## Build and functional checks

`hapag-v07-modal-ground-build.log` records a successful app/instrumentation build, **56 host tests with zero failures, errors or skips**, and **zero lint issues**. The added API 29/35 host cases verify that clearing a Saved foods search keeps its selected filter and bookmarked food.

Comparison with the v0.6 source archive confirms five changed production UI files: FoodsScreen, MealEditor, QuickMealEntry, RecipeDialogs and the bounded modal-status ground in HapagApp. Theme and data sources remain unchanged. Exact centavo arithmetic, nutrition/portion assumptions, meal/recipe snapshots, offline OCR, Undo and backup/restore are preserved; no network permission, dependency or database migration is added.

## Native evidence

All passing final captures and workflows use universal APK `8a4baff24441a4baa6330deb3e5d6fe530ece3206fc65d59b71127fdca8b461b`.

| Environment | Passing capture/behavior scope |
| --- | --- |
| API 35 phone, dark | Eight library/logging states plus real keyboard search: 9 frames |
| API 35 phone, light | The same eight states plus the real recipe-dialog keyboard: 9 frames |
| API 35 phone, dark, font scale 2.0 | Eight states, search keyboard, scrolled recipe/recovery details and dialog keyboard: 12 frames |
| API 35 tablet, dark, 1600×2560 at 240 dpi | Eight states with the native rail/taskbar |
| API 29 phone, dark | Full LoggingCaptureTest behavior, 2 frames, plus MealFlowTest, RecipeFlowTest and NavigationFlowTest |

The capture helper verifies household-unit/gram round trips, unresolved-phrase blocking, explicit Skip, and no meal persistence without Save. The two dialog-keyboard cases assert yield and Cancel remain visible, then verify Back hides the keyboard while keeping the dialog open before a second Back dismisses it. Fixtures are explicitly named Demo and are excluded from the app APK.

The build thread opened all **40 final native frames**. The capture manifest (retained in workspace) records source, API, font scale, dimensions, image SHA-256 and source APK SHA-256. Source proofs are written only after each native case passes. Final logs are retained under `.impeccable/review/v0.7/logs/`. Earlier failed helpers, unsettled captures, old APK runs and controlled diagnostic window mutations are excluded from final evidence.

## Impeccable review and design records

The initial independent full review (retained in workspace) identified only F1: white status indicators over the dimmed light recipe dialog at about 2.43:1. The final F1 verdict (retained in workspace) scores that named correction resolved, disposition **ship**. This is a verdict on F1, not a second whole-surface audit.

The recipe dialog retains native decisions, scrolling, dimming and draft behavior. It uses non-floating window properties with safe-drawing/IME padding. On Android 15 only, while the light recipe dialog is open, a status-inset ground uses the existing dark background role behind Android's white indicators. The captured ground is RGB (12, 12, 12), giving white indicators about 19.56:1 contrast. The normal light ground/indicators return after dismissal. Existing dark, enlarged-text and tablet dialog states and the bottom navigation-button contrast remain in the supplied matrix.

The source-backed design check preserves 79 entries, resolves 32 references, checks 46 explicit Theme.kt colors, 22 source paths, 7 links and 10 previews, and confirms exact Markdown/JSON narrative parity. Ordinary extension rules preserve the established system; no new identity or decorative glass is introduced on forms.

## Packages

| Artifact | Bytes | SHA-256 |
| --- | ---: | --- |
| Hapag-0.7.0-debug.apk | 62,617,534 | `8a4baff24441a4baa6330deb3e5d6fe530ece3206fc65d59b71127fdca8b461b` |
| Hapag-0.7.0-debug.zip | 37,115,956 | `1970febd43e5a2d2a0ef26e10f5ab2662a065d4f8cdee3c1bba56db8ab4f174b` |
| Hapag-0.7.0-arm64-debug.apk | 29,834,043 | `acf46e4616db503dc8f7e727b319a3cf0151f5706ca73564ea85caec5de425b5` |

Both APKs verify with certificate SHA-256 `a4c8e496c0d550a52ec823f3869c61f7e9abc9a38259f06254ef94ebd4ffbc5f`, the existing Hapag development signer. Version/package/minimum/target SDK and absent Internet/network-state permissions were checked from each APK. Both pass 16 KiB alignment; the ARM64 package retains byte-identical code/resources/model entries while removing other-processor libraries. Its physical ARM64 runtime is not certified. The ZIP contains one identical universal APK and passes its CRC check.

Install over existing Hapag to retain the diary; extract the APK first when using ZIP. These remain development builds. Native evidence uses AOSP x86_64 emulators with SwiftShader; physical-device frame time, full TalkBack, gesture-navigation mode and camera/provider certification are outside this pass.
