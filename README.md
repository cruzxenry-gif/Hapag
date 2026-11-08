# Hapag 0.4.0 — Android development build

[Download APK](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.4.0/Hapag-0.4.0-debug.apk) · [Download ZIP](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.4.0/Hapag-0.4.0-debug.zip)

Install over the existing Hapag app to retain its diary. Same package and signing certificate; version code 4; database schema 2 unchanged. Extract the APK if using the ZIP.

## This update

- Real bundled on-device nutrition-label reading from a camera or chosen photo, with no Internet permission or backend key.
- Whole-label preview with orientation correction and zoom/pan/reset; visible recognized text and editable values.
- Explicit per-serving/per100g basis, gram weight and human confirmation. Missing/ambiguous readings remain blank; edits reset confirmation.
- Save a reusable label food and log servings, preserving an existing meal draft and cost. Temporary label photos removed on save/discard.
- Existing v0.3 navy/light design, offline diary, recipes and history retained; database schema2 unchanged.

Validation: 37 host tests across API29/35, four native API29 workflows including real OCR on a synthetic English label, clean lint and scoped native visual review. Same signing certificate supports in-place updates. Camera/picker hardware and all real-world label layouts are not exhaustively audited. English single-column gram/kcal labels have a manual fallback; automatic food-photo AI and barcode lookup remain future work.

The APK is larger because the text model is bundled for offline use. No account is required.

Checksums: [SHA256SUMS.txt](SHA256SUMS.txt).
