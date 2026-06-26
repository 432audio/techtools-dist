# techtools-dist

Public release channel for **432audio Techtools**.

This repo holds only the published download artifacts — it is **not** the source
(which stays private). The app self-updater reads `version.json` from `main`,
compares the advertised `versionCode` to the running build, and if newer offers
to download + install the APK from that release.

- **`version.json`** — the live manifest the app polls:
  - `versionCode` / `versionName` — the latest published build
  - `apkUrl` — direct download for that build's APK (a release asset here)
  - `notes` — shown in the in-app update dialog
- **Releases** — each holds the signed APK for a version (and may host
  `node_fw.bin` for the DMX node OTA).

To publish a new version: cut a release with the APK, then bump `version.json`
on `main` to match. The bump on `main` is what makes phones see the update.
