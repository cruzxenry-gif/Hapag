# Hapag 0.5.0 — Android development build

[Download APK](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.5.0/Hapag-0.5.0-debug.apk) · [Download ZIP](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.5.0/Hapag-0.5.0-debug.zip)

Install over the existing Hapag app to retain its diary. Same package and signing certificate; version code 5; database schema 2 unchanged. Extract the APK if using the ZIP.

## This update

- Portable ZIP backup and explicitly confirmed restore from Me → Backup and restore. Includes saved photos, independent meal/recipe snapshots, favorites, settings, water and weight.
- Validated record-count preview, cancellation/recreation, and transactional replacement. Invalid backups leave the existing diary intact. Exported files contain personal data and are not encrypted by Hapag.
- Undo a deleted meal while the native snackbar is visible.
- Selected-week queries bound live diary/history data while preserving full history in storage and backups.
- Optional [ARM64 APK](Hapag-0.5.0-arm64-debug.apk) for compatible phones, with the same code/resources/offline OCR model and existing signer. Use the universal APK if compatibility is uncertain.

Validation: 50 host tests across API29/35, clean lint, real native backup/undo/restore and existing meal/recipe/navigation/OCR workflows, plus scoped native visual review. See repository docs/VALIDATION-v0.5.md for evidence and limits. ARM64 packaging has signature/alignment/payload checks; physical ARM64 runtime and physical-device speed targets are not certified. The universal build is executed on the API29 x86_64 software emulator.

Install over the existing Hapag development build to retain the diary; do not uninstall first. Database schema2 is unchanged. Backup is user-initiated, offline-capable storage with a system chooser; cloud document providers may separately need connectivity. No account or Internet permission is introduced.

Checksums: [SHA256SUMS.txt](SHA256SUMS.txt).
