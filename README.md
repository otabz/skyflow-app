# SkyFlow — Live Weather Wallpaper

A live wallpaper for Android that renders the sky above you in real time — clouds,
sun, rain, snow, lightning, stars, and galaxies that follow your local weather and
time of day, with smooth transitions between conditions.

> **Download the latest APK from the [Releases page](../../releases).**
> Sideloading requires allowing "install from unknown sources" for your browser
> or file manager.

<!--
  SCREENSHOTS
  Drop your wallpaper screenshots into the images/ folder and update the paths
  below. Recommended: 3–5 shots showing different conditions (clear day, rain,
  night sky, a transition). PNG or JPG. Keep each under ~1 MB so the page loads
  fast. Replace the placeholder lines with your real filenames.
-->

## Screenshots

| Clear sky | Rain | Night |
| --------- | ---- | ----- |
| ![Clear sky](images/clear.png) | ![Rain](images/rain.png) | ![Night sky](images/night.png) |

<!-- Add more rows or a wide hero shot above the table if you have one:
![SkyFlow hero](images/hero.png)
-->

## Features

- **Real-time weather** — the scene reflects current conditions at your location:
  cloud cover, precipitation, and clear skies.
- **Time-of-day sky** — physically-modelled atmospheric colour that shifts through
  sunrise, day, sunset, and night.
- **Weather effects** — layered rain and snow, lightning during storms, sun glare,
  rainbows, a starfield at night, and an occasional galaxy.
- **Smooth transitions** — conditions cross-fade rather than snap, so the wallpaper
  changes gracefully as the weather does.
- **Location-aware** — uses your device location (or a city you pick) to fetch
  local weather.
- **Efficient** — a fixed-rate renderer with a scaled off-screen target; steady,
  bounded memory use.

## Supported devices

- Android with arm64-v8a or armeabi-v7a (essentially all current phones).
- Requires location permission for automatic local weather; a manual city
  selection is available if you prefer not to grant it.

## Security & privacy

SkyFlow is built with a published security process. The reports in
[`security/`](security/) are generated from automated scans of the source and
dependencies:

- **Dependency scanning** — third-party libraries checked for known
  vulnerabilities.
- **Static analysis (CodeQL)** — the source scanned for common security issues.
- **Signed releases** — every APK is signed with a stable release key, so updates
  are verifiably from the same author.

<!--
  Publish your reports here: export CodeQL / Dependabot / any scanner output as
  PDF or markdown and commit them into security/. Then link them, e.g.:
    - [CodeQL report (2026-09)](security/codeql-2026-09.md)
    - [Dependency audit (2026-09)](security/dependencies-2026-09.pdf)
-->

**On privacy:** SkyFlow requests location to fetch local weather. What it collects
and how it uses it is described in [`PRIVACY.md`](PRIVACY.md).

## About this repository

This is the public home for SkyFlow: screenshots, release downloads, and security
reports. The application source is maintained privately. Questions and bug reports
are welcome in [Issues](../../issues).

## License

<!-- Choose one. For a closed-source app distributed as an APK, a simple
     "all rights reserved" statement is common, or pick a license that fits.
     If you leave the source closed, you are NOT granting reuse rights to the
     APK or artwork; state that here. -->

© 2026 Muhammad Tayyab. All rights reserved. The SkyFlow application, its artwork,
and its assets may not be redistributed or reused without permission.
