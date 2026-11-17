# BuildSync — direct downloads

Public download home for **BuildSync**, a construction project-management app
for site teams: projects, tasks, documents, daily reports and workforce, on
Windows, Android and the web.

This repository hosts **release binaries only**. The application source lives in
a private repository; nothing is developed here.

- **Website:** https://buildsync-site-201.pages.dev
- **Latest release:** https://github.com/bouazzaameurfares/buildsync-releases/releases/latest
- **Support / bug reports:** [Issues](https://github.com/bouazzaameurfares/buildsync-releases/issues)

## Download

| Platform | File | Requirements |
|---|---|---|
| Windows | [`BuildSync-Setup.exe`](../../releases/latest/download/BuildSync-Setup.exe) (197 MB) | Windows 10 or 11, 64-bit |
| Android | [`BuildSync.apk`](../../releases/latest/download/BuildSync.apk) (136 MB) | Android 7.0 or newer |

BuildSync is a **sideload-only** product: it is not published on Google Play or
the Apple App Store. There is no store listing and no account needed to install.

Versions, sizes and SHA-256 hashes are published in [`latest.json`](latest.json).

## Install — Windows

1. Download `BuildSync-Setup.exe`.
2. The installer is signed but not notarised, so SmartScreen may show
   *"Windows protected your PC"*. Choose **More info → Run anyway**.
3. The installer is per-user: it needs no administrator rights and installs to
   `%LOCALAPPDATA%\Programs\BuildSync`, with Start-menu and desktop shortcuts.

## Install — Android

1. Download `BuildSync.apk`.
2. When Android asks, allow installs from your browser or file manager
   (*Install unknown apps*).
3. Open the file and install. The app appears as **BuildSync**.

## Verify a download

Every artifact is published with a SHA-256 hash in `latest.json`.

```powershell
Get-FileHash .\BuildSync-Setup.exe -Algorithm SHA256
```

```bash
sha256sum BuildSync.apk
```

## Upgrading from BuildFlow AI 0.2.0

0.3.0 is a **new application**, not an update — the package identity changed:

- **Android:** the old `BuildFlow AI` app stays installed until you uninstall it.
  Anything queued offline in the old app (photos, edits) is lost, and the new app
  starts signed out.
- **Windows:** `BuildSync` installs alongside `BuildFlow AI` — two Start-menu
  entries, two uninstall entries and separate `%APPDATA%` folders. Uninstall the
  old app by hand when you are done with it.
- **SmartScreen:** the "unknown publisher" warning returns until the new binary
  builds reputation; the old binary's history does not carry over.
- No session, secret or cached data is shared between the two installs.

## What this repository is not

- Not a source repository.
- Not a bug tracker for the web app — use Issues here and it will be triaged.
- Not a distribution channel for app stores. See the brand and distribution rules
  in the private repository (`docs/12-BRAND.md`).
