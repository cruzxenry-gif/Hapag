# Hapag 0.6.0 — Android development build

[Download APK](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.6.0/Hapag-0.6.0-debug.apk) · [Download ZIP](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.6.0/Hapag-0.6.0-debug.zip)

Install over the existing Hapag app to retain its diary. Same package and signing certificate; version code 6; database schema 2 unchanged. Extract the APK if using the ZIP.

## This update

- Dark-first charcoal/soft-white UI with a restrained sage action color and a saved manual light/dark switch, with matching status icons. On Android15+, button-navigation chrome follows OS appearance for readable controls; gestures and earlier Android versions retain app appearance.
- Compact energy and macro summary before recent meals. Budget and water follow meals; all existing logging methods remain available.
- Bounded native backdrop blur on supported hardware, with readable tint and solid fallback on older/unsupported devices. Native labels, Back, scrolling/insets and tablet navigation retained.
- Existing offline OCR, portable diary/photo backup/restore, recipes, exact costs, snapshots and Undo preserved; database schema2 unchanged.
- Optional [ARM64 APK](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.6.0/Hapag-0.6.0-arm64-debug.apk) uses the same code/resources/offline model and existing development signer. Use the universal APK if compatibility is uncertain.

See [validation and limits](VALIDATION.md). This remains a development build. Physical-device frame-time and ARM64 hardware certification are not claimed. No account or Internet permission is introduced. The appearance preference is local app configuration, outside the portable diary archive.

54 host tests, five native core workflows and lint passed. Impeccable scored the three original review fixes resolved within the supplied native evidence.

Checksums: [SHA256SUMS.txt](SHA256SUMS.txt).
