# SkyFlow — Live Weather Wallpaper

![Release](https://img.shields.io/github/v/release/otabz/skyflow-app?label=latest%20release)
![Platform](https://img.shields.io/badge/platform-Android%208.0%2B-3ddc84?logo=android&logoColor=white)
![Signed](https://img.shields.io/badge/release-signed-brightgreen)
[![Security scans](https://img.shields.io/badge/security-release%20scanned-blue)](https://github.com/otabz/skyflow-app/releases/latest)

A personal live-wallpaper experiment that brings the beautiful MIUI weather experience to your Android home screen — ever-changing skies, majestic clouds, gentle transitions, and rich colors that follow your local weather and the time of day.

> ## ⚠️ IMPORTANT — ANDROID INSTALLATION NOTICE
>
> **Download the latest APK from the [Releases page](../../releases).**
>
> Android / Google Play Protect may warn that SkyFlow is unsafe or from an unrecognized developer when you install the APK.
>
> SkyFlow is currently distributed directly through GitHub and the developer is **not yet registered with Android's developer verification program**. Because of this, Android may not recognize the developer and may display a security warning during installation.
>
> **If you downloaded the APK directly from this repository's official Releases page, you can continue by selecting _More details_ and then _Install anyway_ when Android provides that option.**
>
> The exact wording may vary depending on your Android version.
>
> ✅ No advertising, analytics, or tracking  
> ✅ SkyFlow has no server or backend of its own  
> ✅ Data is sent directly to **Open-Meteo** only for weather, air-quality, and city/geocoding requests  
> ✅ No camera, microphone, contacts, storage, or notification access  
> ✅ The only optional runtime permission is **Location**  
> ✅ Location permission can be avoided entirely by selecting a city manually  
> ✅ Published release APKs are security-scanned; see the [latest release](https://github.com/otabz/skyflow-app/releases/latest)  
> ✅ Releases are signed with the same release certificate  
> ✅ Download only from this repository's official **Releases** page
>
> 🔒 **Privacy:** SkyFlow has no server or backend of its own and contains no advertising, analytics, or tracking. It communicates directly with **Open-Meteo** only to retrieve weather, air-quality, and city/geocoding information needed by the app. Location permission is optional and is used only to obtain weather for your current location; you can avoid granting it entirely by selecting a city manually. Your selected city and app preferences are stored locally on your device. See [`PRIVACY.md`](PRIVACY.md) for full details.

## Screenshots

<p align="center">
  <img src="images/clear.jpg" width="31%" alt="Clear sky">
  <img src="images/partly_cloudy.jpg" width="31%" alt="Partly cloudy">
  <img src="images/thunderstorm.jpg" width="31%" alt="Thunderstorm">
</p>

<p align="center">
  <strong>Clear</strong> · <strong>Partly cloudy</strong> · <strong>Thunderstorm</strong>
</p>

<p align="center">
  <img src="images/heavy_snow.jpg" width="31%" alt="Heavy snow">
  <img src="images/heavy_sand.jpg" width="31%" alt="Heavy sand">
  <img src="images/milky_way.jpg" width="31%" alt="Milky Way night sky">
</p>

<p align="center">
  <strong>Heavy snow</strong> · <strong>Heavy sand</strong> · <strong>Milky Way (night)</strong>
</p>

## What it does

- **Real-time weather** — the scene reflects the current conditions at your location: cloud cover, rain, snow, and clear skies.
- **Time-of-day sky** — physically-modelled atmospheric color that shifts through sunrise, day, sunset, and night.
- **Weather effects** — layered rain and snow, lightning during storms, sun glare, rainbows, a starfield at night, and the occasional galaxy.
- **Smooth transitions** — conditions cross-fade rather than snap, so the wallpaper changes gracefully as the weather does.
- **Location-aware** — uses your device location, or a city you pick, to fetch local weather.
- **Efficient** — a fixed-rate renderer with steady, bounded memory use.

## Supported devices

- Android with arm64-v8a or armeabi-v7a.
- Android 8.0 (Oreo) and above.
- Location permission is optional. It is only needed for automatic local weather; you can select a city manually instead.

## Security & privacy

SkyFlow is built with a published security process. The **actual release APK distributed through GitHub Releases** is scanned so the security results correspond to the build users download:

- **Release APK scanning** — the published Android release APK is analysed with MobSF.
- **Dependency scanning** — third-party libraries are monitored for known vulnerabilities with Dependabot.
- **Signed releases** — every APK is signed with a stable release key, so updates can be verified as coming from the same author.

See the [latest release and security scan](https://github.com/otabz/skyflow-app/releases/latest). Earlier reports are retained in the [`security/`](security/) archive.

**Privacy:** SkyFlow has no server or backend of its own and contains no advertising, analytics, or tracking. It communicates directly with **Open-Meteo** only to retrieve weather, air-quality, and city/geocoding information needed by the app. Location permission is optional and can be avoided entirely by selecting a city manually. Your selected city and app preferences are stored locally on your device. See [`PRIVACY.md`](PRIVACY.md) for full details.

## About this project

SkyFlow is a personal, non-commercial experiment — a fan's attempt to bring the beautiful MIUI weather experience onto an Android live wallpaper, so people like me can enjoy ever-changing weather with gentle transitions, majestic clouds, and rich sky colors throughout the day.

The weather visuals are closely derived from MIUI's weather designs, recreated for learning and personal enjoyment. This project is **not affiliated with, endorsed by, or connected to Xiaomi or MIUI**, and all rights to the original MIUI weather designs remain with Xiaomi. The application code and engine are the author's own work; the visual designs are not.


## License

The **source code** for this project — including the rendering engine, build tooling, and app logic — is the author's own work. The **visual designs and weather artwork** are derived from MIUI, but have been adapted and optimized for the live wallpaper experience, including performance, rendering efficiency, and memory usage.

## Feedback

Questions and bug reports are welcome in [Issues](../../issues).