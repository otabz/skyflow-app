# SkyFlow — Security scan summary

Automated security analysis for SkyFlow. Reports are generated from the source and APK and published here so the results can be reviewed directly.

[← Back to main README](../README.md) · [Privacy policy](../PRIVACY.md)

## Latest published reports — v1.1.3

- [MobSF APK report (PDF)](v1.1.3/mobsf-report.pdf)
- [MobSF APK report (JSON)](v1.1.3/mobsf-report.json)
- [mobsfscan source report (JSON)](v1.1.3/mobsfscan-report.json)

## Tools

- **mobsfscan** — static analysis of the app's Java source using MobSF/Semgrep rules.
- **MobSF** — static analysis of the built Android APK, including permissions, manifest configuration, certificate information, code findings, and network configuration.
- **Dependabot** — dependency vulnerability monitoring through GitHub.

## Important note about the APK scan

The published MobSF report for v1.1.3 analyses the **debug scan build** (`1.1.3-debug`), not the signed production APK.

Because of this, MobSF reports findings that are expected for the scan build:

| MobSF finding | What it means |
| --- | --- |
| **Application signed with a debug certificate** | The APK submitted to MobSF is the debug scan build. Public SkyFlow releases are signed separately with the stable release certificate. |
| **Debug enabled (`android:debuggable=true`)** | Expected for the debug scan build. It does not describe the release build. |
| **Android 8.0 / minSdk 26** | SkyFlow intentionally supports Android 8.0 and above. |
| **Exported wallpaper service protected by `BIND_WALLPAPER`** | Required for Android to bind to a live wallpaper service. |

The MobSF report identifies the scanned APK as:

- **App:** SkyFlow Live Weather
- **Package:** `com.otabz.skyflowliveweather.debug`
- **Version:** `1.1.3-debug`
- **Permissions:** Internet, network state, coarse location, and fine location
- **Detected trackers:** 0

## Source-scan findings

Some static-analysis findings are expected false positives or non-security-sensitive uses:

- Strings used as SharedPreferences keys may be reported as possible hardcoded keys even though they are not credentials or API secrets.
- `java.util.Random` is used for visual effects such as cloud and lightning variation, not cryptographic operations.
- UI visibility calls such as `setVisibility(GONE)` can be flagged even when they only control ordinary interface elements.

Raw findings are available in the published JSON reports above.

## Permissions and privacy

SkyFlow has no server or backend of its own and contains no advertising, analytics, or tracking.

The app communicates directly with **Open-Meteo** to obtain weather, air-quality, and city/geocoding information used by the wallpaper.

Location permission is optional. It is used for automatic local weather and can be avoided by selecting a city manually.

See the [privacy policy](../PRIVACY.md) for full details.

## About these reports

Security scanning helps identify common implementation and configuration issues, but automated scan results should not be interpreted as a guarantee that software is free from every possible vulnerability.

The raw scan outputs are kept alongside this summary so findings can be independently reviewed for each published version.
