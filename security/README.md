# Security scan summary

_Automated security analysis of SkyFlow. Reports are generated in CI on each
release. This page summarises the findings honestly — including which flags are
expected by design and which are artifacts of how the scan is run._

## Tools

- **mobsfscan** — static analysis of the app's Java source (MobSF rules, semgrep).
- **MobSF** — static analysis of the built APK (permissions, manifest, certificate).
- **Dependabot** — dependency vulnerability scanning (GitHub, on the private source repo).

## Headline

No hardcoded secrets, no known-vulnerable dependencies, and no exploitable
findings in the source. The MobSF APK score is deflated by debug-build flags that
are **not present in the released APK** — see below.

## About the APK score

The CI scan analyses a **debug build** of the APK (this keeps the release signing
key out of the scan job). Two of MobSF's highest-weighted findings are therefore
artifacts of the debug build and do **not** apply to the released app:

| MobSF finding | Reality |
| --- | --- |
| "Signed with a debug certificate" | The **released** APK is signed with a private release key. Only the scan build is debug-signed. |
| "Debug enabled (`android:debuggable=true`)" | The **released** build sets `isDebuggable = false` and is R8-minified. Debug builds set this flag; release builds do not. |

Because these two items carry most of the score penalty, the released APK's real
posture is substantially better than the debug-scan number suggests.

## Findings and disposition

**Expected by design**

- **Wallpaper service is exported and guarded by `BIND_WALLPAPER`.** Required: the
  Android system must be able to bind a live-wallpaper service. This is how every
  live wallpaper works.
- **`INTERNET`, `ACCESS_NETWORK_STATE`, and location permissions.** Needed to fetch
  local weather. Location is optional — a manual city selection is available.
- **`minSdk 26` (Android 8.0).** A device-reach choice, not a vulnerability.

**False positives (reviewed)**

- **"Hardcoded API key" (many matches).** These are SharedPreferences key *names*
  (e.g. `KEY_LATITUDE = "latitude"`), not secrets. No API key is embedded in the app.
- **"Hardcoded username".** Matches the app's HTTP `User-Agent` string, not a credential.
- **"Insecure random number generator".** `java.util.Random` is used for visual
  randomness (cloud drift, lightning timing), not for anything security-sensitive.
- **"Hidden UI element".** Matches `setVisibility(GONE)` on an error label and a
  search box — neither holds sensitive data.

**Optional future hardening (informational)**

- TLS certificate pinning / transparency, tapjacking protection, root detection,
  screenshot prevention. These are defence-in-depth suggestions, not defects.

## Reports

The raw reports for each release are published under `security/<version>/`:

- `mobsf-report.pdf` / `mobsf-report.json` — full MobSF APK analysis.
- `mobsfscan-report.json` — source static-analysis results.

## Note on asset protection

These scans assess the security of the application **code** — that it is free of
known vulnerabilities and embeds no secrets. Artwork protection (asset encryption
with a native-code key) is a separate concern handled inside the app; it raises
the cost of casual asset extraction but, like all client-side protection, cannot
make extraction impossible.
