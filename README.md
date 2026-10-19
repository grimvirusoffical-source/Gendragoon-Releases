# GenDragoon Releases

Pre-release builds of the GenDragoon Cloud SSD clients. Every build here is a **test build**: unsigned, not distributed through any app store, and not yet verified on real devices. Use them for evaluation only.

Source code lives in the [gendragoon-cloud-ssd](https://github.com/grimvirusoffical-source/gendragoon-cloud-ssd) repository.

## Downloads

| Release | Platform | Asset | Status |
|---|---|---|---|
| [android-v0.17.0-build20-debug](https://github.com/grimvirusoffical-source/Gendragoon-Releases/releases/tag/android-v0.17.0-build20-debug) | Android 8.0+ (API 26) | `GenDragoon-Android-0.17.0-build20-debug.apk` | Debug-signed APK. Builds successfully; not yet installed on a device or emulator. Not suitable for Google Play. |
| [windows-x64-v0.1.0-unpacked](https://github.com/grimvirusoffical-source/Gendragoon-Releases/releases/tag/windows-x64-v0.1.0-unpacked) | Windows 10/11 x64 | `GenDragoon-Cloud-SSD-Windows-x64-unpacked-0.1.0.zip` | Unpacked Electron app, unsigned. No installer yet. Not yet run on Windows. |
| [desktop-companion-windows-linux-source-ce5665f](https://github.com/grimvirusoffical-source/Gendragoon-Releases/releases/tag/desktop-companion-windows-linux-source-ce5665f) | Windows and Linux | `GenDragoon-Desktop-Companion-Windows-Linux-source.zip` | Command-line companion (Python 3.11+ source). 36 unit tests pass on Linux; the Windows path has not been run. |
| [audit-patches-2026-10-19](https://github.com/grimvirusoffical-source/Gendragoon-Releases/releases/tag/audit-patches-2026-10-19) | Developers | two `.patch` files | Test-only patches that make two timestamp-based tests deterministic. |

macOS and iOS builds are not published here; they require Xcode.

## Verifying downloads

The Android, Windows and companion releases include a `SHA256SUMS` file:

```sh
sha256sum -c SHA256SUMS
```

## Installing

* **Android:** enable installation from unknown sources and open the APK. The app uses a debug signing key.
* **Windows:** unzip and run `GenDragoon Cloud SSD.exe`. Windows SmartScreen will warn because the build is unsigned. The app was built without a cloud API address, so it starts in local-preview mode and does not connect to the cloud backend.
* **Companion (Windows and Linux):** unzip, then run `sh install-linux.sh` or `install-windows.ps1`. See the README inside the archive.
* **Patches:** apply with `git am` on top of commit `ce5665f` of `gendragoon-cloud-ssd`.

## Known limitations

* None of these builds are signed for distribution.
* The Android and Windows apps have not been run on real devices.
* The Windows build is an unpacked folder; the installer is produced by the source repository's CI job and is not included.
