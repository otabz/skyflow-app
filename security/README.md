# SkyFlow — Security scans

SkyFlow security verification is performed against the **published release APK** distributed through GitHub Releases. This means the scanned app is the same release build users download, rather than a separate debug scan build.

[← Back to main README](../README.md) · [Latest release & security scan](https://github.com/otabz/skyflow-app/releases/latest) · [All releases](https://github.com/otabz/skyflow-app/releases) · [Privacy policy](../PRIVACY.md)

## Current release scanning

For each published release, the release APK is analysed as part of the release security process. Security results and release assets should be reviewed from the corresponding entry on the [GitHub Releases page](https://github.com/otabz/skyflow-app/releases).

The release scan covers the actual production package:

- **App:** SkyFlow Live Weather
- **Package:** `com.otabz.skyflowliveweather`
- **Build:** signed release APK

This avoids the misleading debug-only findings that can appear when a separate debug APK is scanned, such as a debug certificate, `android:debuggable=true`, or a `.debug` application ID.

## Security tools

- **MobSF** — static analysis of the published Android release APK, including permissions, manifest configuration, certificate information, code findings, network configuration, and other APK security checks.
- **Dependabot** — dependency vulnerability monitoring through GitHub.

## Historical reports

The versioned folders under this `security/` directory are retained as a historical archive of earlier scan reports. Some older versions include **mobsfscan source reports** and reports produced from the previous scan workflow.

For the current security status, use the scan associated with the relevant [GitHub Release](https://github.com/otabz/skyflow-app/releases) rather than assuming an older report in this directory represents the latest build.

## Interpreting scan findings

Automated security scanners can report findings that are expected or non-security-sensitive in the context of an Android live wallpaper. For example:

- SharedPreferences key strings are application preference identifiers, not API credentials or secrets.
- `java.util.Random` may be used for visual variation such as clouds or lightning rather than for cryptographic purposes.
- The exported wallpaper service is protected by Android's `BIND_WALLPAPER` permission because Android must be able to bind to a live wallpaper service.
- Android 8.0 / API 26 is intentionally supported as the minimum Android version.

Review findings in the context of the exact release APK that was scanned.

## Permissions and privacy

SkyFlow has no server or backend of its own and contains no advertising, analytics, or tracking.

The app communicates directly with **Open-Meteo** to obtain weather, air-quality, and city/geocoding information used by the wallpaper.

Location permission is optional. It is used for automatic local weather and can be avoided by selecting a city manually.

See the [privacy policy](../PRIVACY.md) for full details.

## About security scans

Automated scanning helps identify common implementation, dependency, and configuration issues, but a clean scan is not a guarantee that software is free from every possible vulnerability.

Always download SkyFlow from this repository's official [GitHub Releases page](https://github.com/otabz/skyflow-app/releases).
