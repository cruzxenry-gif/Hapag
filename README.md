# Hapag 0.2.0 — Android development build

[Download APK](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.2.0/Hapag-0.2.0-debug.apk) · [Download ZIP](https://github.com/cruzxenry-gif/Hapag/raw/refs/heads/downloads/hapag-0.2.0/Hapag-0.2.0-debug.zip)

Install over the existing Hapag app to retain its diary. Application ID and signing certificate match v0.1; version code is 2. If using the ZIP, extract the APK first.

## This update

- Type foods, review exact offline catalog matches and visible portion assumptions, and explicitly correct or skip unknown phrases.
- Save a whole recipe with ingredients, batch cost and serving yield; edit recipes and log servings.
- Editing or deleting a saved recipe preserves nutrition and costs in previously logged meals.
- Room schema 1→2 preserves existing meals, custom foods, favorites, goals, water and weight.

Validation: 22 host tests passed, including Android 10/15 Compose flows and a populated v0.1 migration fixture. Both connected API 29 meal/recipe workflows passed; lint reported zero issues.

Starter nutrition values remain labeled estimates. Typed matching uses the on-device catalog; automatic photo AI, export/backup and sync are future work. No account is required.

Artifact hashes: [SHA256SUMS.txt](SHA256SUMS.txt).
