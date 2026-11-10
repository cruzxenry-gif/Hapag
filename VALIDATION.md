# Hapag 0.6.0 validation

Hapag's charcoal/soft-white/sage Home and navigation update passes54 host tests, zero lint issues, five native core workflows and the native Home/appearance matrix. The final universal APK is ph.hapag, versionCode6, versionName0.6.0, minimum API26/target35. Database schema2 and the established development signer are retained.

## Build and host checks

`hapag-v06-native-boundary-final-checks.log` records the successful universal/instrumentation build, complete54-test host run and lint. Test XML reports zero failures, errors or skips; lint XML contains zero issues. `hapag-v06-final-capture-helper.log` records a successful instrumentation build and lint after removing temporary reflection diagnostics; production code was unchanged by that cleanup.

The existing50 host regressions are retained. Four Home/appearance cases cover dark default under a light-system configuration, saved manual selection/recreation, saving a meal after recreation, and summary/meal/budget/water placement. Native Today selectors use a stable destination tag, distinct from the screen heading. Earlier failed/stale builds are excluded from passing evidence.

## Native functional checks

All five workflows passed on the final installed universal APK on an API29 AOSP x86_64 emulator with SwiftShader. Installed app and test APK hashes were compared with the final local files before the run. Each class started with fresh synthetic app data in this disposable AVD.

| Workflow | Result | Log under `/workspace/toolchains/` |
| --- | --- | --- |
| Meal logging/editing | Pass | hapag-v06-api29-MealFlowTest.log |
| Saved recipes and history | Pass | hapag-v06-api29-RecipeFlowTest.log |
| Backup/restore and Undo | Pass | hapag-v06-api29-BackupFlowTest.log |
| Navigation, drafts and goals | Pass | hapag-v06-api29-NavigationFlowTest.log |
| Offline label OCR/review | Pass | hapag-v06-api29-LabelOcrFlowTest.log |

`hapag-v06-flows-final-resume.log` records completion. A cloud process interruption stopped an earlier run; interrupted checks were resumed and only completed passing logs are used here.

## Native visual and appearance checks

All29 required PNGs are native full-system frames, opened and validated before handoff. The workspace capture manifest records paths, hashes, dimensions, font scale and the final APK hash. Every required frame is newer than that APK. Earlier captures and loading/launcher experiments are excluded.

| Configuration | Required frames |
| --- | --- |
| API35 phone, dark | Empty, populated Home, budget/water, Add, after dismissal |
| API35 phone, light | Same five states |
| API35 phone, font_scale2.0 | Same five states and the other end of scrollable navigation |
| API35 tablet | Same five states; budget/water already fit within the viewport |
| API29 solid fallback | Same five dark states |
| API35 ordinary cold launch | Home, Add, return; captured outside instrumentation |

Phone frames are1080×2340; tablet frames are1600×2560 at density240. Native Home tests assert a saved synthetic meal, supported/fallback glass eligibility, four displayed Add methods and real Back in the active native sheet window. The enlarged-text run visits all four destinations. Saved light appearance also passes a separate process-restart check. Fixture records are explicitly named Demo meals and are not shipped or seeded into users' diaries.

Evidence includes `hapag-v06-platform-contrast-phone-dark.log`, `hapag-v06-native-final-resume.log`, `hapag-v06-theme-restart.log`, `hapag-v06-api29-final.log` and `hapag-v06-ordinary-final.log`. The final API35 run resumes only interrupted remaining variants; completed dark/fallback/ordinary frames were retained and verified against the same final APK.

## Review corrections and material

The initial independent Impeccable review identified three material findings: F1 enlarged navigation labels clipping/breaking midword, F2 activity/modal system-inset contrast, and F3 prematurely captured light/tablet Add frames. A fresh replacement Impeccable verdict scored F1, F2 and F3 resolved and returned **ship**, at the original fix-list scope. The original reviewer became unavailable after the cloud interruption; the replacement used an independent fresh context and opened all29 valid frames. F2 is resolved for the supplied navigation modes, with gesture-mode runtime behavior outside that verdict. The report is `.impeccable/review/v0.6/finish-verdict.md`.

F1 uses native scrollable icon/text tabs above fontScale1.4, with unshrunk single-line names, minimum112dp tab width/row height and a separately pinned52dp Add action. All destinations were exercised; an edge fragment of the next tab is a scrolling affordance. Other phone sizes retain the labeled native bar; tablets use a rail.

F2 paints app-matching activity window ground and manual status appearance. On API35+, a native tappable button-navigation strip follows OS night appearance; gestures and earlier APIs retain app appearance. A disposable global-layout observer reads public root-window insets without replacing Compose's inset listener. Diagnosis found native132px button insets while the activity Compose child reported zero; using the child had selected the wrong appearance. Activity and sheet share the resolved mode and retain native navigation contrast enforcement. Current dark/light/tablet/API29 and ordinary-launch frames show readable controls before, during and after Add. Gesture-mode runtime and hardware certification are outside the supplied evidence.

F3 replacements show settled native light/tablet sheets with all four logging methods. The helper asserts displayed controls, waits for native rendering and captures the result after dismissal. Earlier incomplete sheet frames are excluded.

Haze1.5.2 supplies bounded backdrop effects on API32+ hardware-accelerated views:18dp blur, input scale0.75, zero noise,88% surface tint, and an opaque solid-surface fallback. API31 deliberately retains the fallback. Foreground controls/text stay outside the blur source. Home's bottom scroll clearance uses measured navigation height plus20dp; other screens retain native content/IME spacing. No browser screenshot or HTML/CSS detector is used as native evidence.

Static contrast pairs include dark primary text/background16.86:1, dark helper/surface9.01:1, dark primary action8.97:1, light helper/background6.10:1 and light primary action7.34:1. These calculations complement native frames and do not constitute full accessibility certification. Written totals, units and labels accompany indicators; individual macro targets are not invented.

`DESIGN.md` and `.impeccable/design.json` document46 explicit color roles,10 typography roles,3 radii,8 spacing steps and12 components. Source color equality, YAML/JSON structure,32 references, scoped previews, links and source paths were checked. Palette/type/shape primitives did not change in the system-inset correction.

## Data and package continuity

Appearance uses local SharedPreferences outside the portable diary archive, defaults to dark and saves the manual switch. Restoring diary records does not change that separate preference. Shared neutral tokens apply to existing controls; only Home/navigation/Add composition is redesigned in this milestone.

Schema2 and the additive1→2 migration remain. Offline OCR, recipes, immutable meal snapshots, exact costs, Undo and portable diary/photo backup/restore remain covered. Manifest inspection confirms no Internet or network-state permission. Both APKs retain certificate SHA256:

`a4c8e496c0d550a52ec823f3869c61f7e9abc9a38259f06254ef94ebd4ffbc5f`

| File | Bytes | SHA256 |
| --- | ---: | --- |
| Hapag-0.6.0-debug.apk | 63,032,827 | d858236d3db7de50feceac8b335d8a470d2683fedacdcf4db963fc8d59b8cc08 |
| Hapag-0.6.0-debug.zip | 37,117,167 | aabe0156ab03e69b7b93013b4b6c93aa19a890a77dcb86fd749f193fa2b618e8 |
| Hapag-0.6.0-arm64-debug.apk | 29,838,139 | f778018aa20c405766e559e67f6a9d54e3364b1d714ac32fa1a06cd280efbcc8 |

The optional ARM64 package passes signature verification,16KiB zip alignment and byte equality for retained code/resources/offline-model entries. It removes other-processor libraries and obsolete signature records and is52.7% smaller than universal. This is packaging validation, not ARM64 execution evidence. The ZIP contains the same universal APK.

Download files and checksums are distributed on `downloads/hapag-0.6.0`, preserving older download branches. Install over the existing app to keep the diary; extract the APK first if using ZIP.

## Evidence limits

Native evidence comes from software-emulated AOSP/SwiftShader without KVM. API35 startup required disabling the failing disposable AVD Bluetooth service and increasing emulator startup/watchdog thresholds; no Bluetooth feature/permission or timeout workaround is added to the APK. Emulation timings are not hardware performance measurements.

Physical-device frame times, battery use, full TalkBack certification, gesture hardware behavior, ARM64 execution and physical camera/provider compatibility are not certified here. There is no60fps claim. Layouts outside the Home/navigation milestone are not exhaustively recertified. No account, backend or production signing key is introduced.
