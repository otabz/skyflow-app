# Security reports

Published output from the automated scans run against the SkyFlow source.

## What goes here

Commit generated reports into this folder and link them from the main README.
Suggested cadence: refresh on each release, or monthly.

- **CodeQL** — from the private repo's Security tab, export or summarise results.
  Save as `codeql-YYYY-MM.md`.
- **Dependabot / dependency audit** — the dependency alert summary. Save as
  `dependencies-YYYY-MM.md` (or `.pdf`).
- **Any additional scanners** you run (e.g. MobSF for the APK) — save the summary
  here too.

## How to generate them

The scans run in the **private** `skyflow` repository (it has the source). Enable
in that repo's **Settings → Code security**:

- Dependency graph + Dependabot alerts
- CodeQL analysis (default setup is one click; it runs on every push)
- Secret scanning

Then export or summarise the results and commit the summary here, in the public
repo, so the report is visible without exposing the source.

## Note

These reports describe the security of the application **code** — that it is free
of known vulnerabilities and built from audited dependencies. They are a signal
that the app is safe to install. They are separate from asset protection, which is
handled inside the app.
