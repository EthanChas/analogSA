# Changelog

## v0.0.5

**Canon.** 426 lenses across every Canon mount — EF (150), RF (102), FD (98), FL (31), R
(18), EF-M (15) and EF-S (12) — compiled from Wikipedia's lens mount articles. Each entry
carries focal length, maximum aperture, year of introduction, and the feature flags that
matter when buying: L-series, USM, image stabilisation, filter thread.

Canon has **no camera bodies yet**, and the app now says so rather than showing Pentax's.
Camera bodies are tagged by brand, so each brand's count is its own.

The Canon logo appears on its card, in the same way Pentax's does.

## v0.0.4

**The updater no longer crashes, and says what went wrong when it fails.** Updating from
within the app could black out and die instead of installing. Every step of the update
path is now caught, and a failure ends in a dialog naming the cause with an option to
download the file in a browser instead.

Three specific fixes behind that:

- **Redirects.** GitHub serves release downloads via a redirect to a separate storage
  host. `HttpURLConnection` does not follow that hop automatically, so the download could
  end up saving a redirect stub rather than an APK. Redirects are now followed explicitly,
  up to five hops.
- **The download is now verified** before being handed to the installer — it must be over
  100 KB and start with the zip magic number that every APK begins with. Previously an
  error page saved as `.apk` would have been passed straight to the package installer.
- **Progress is visible.** An 18 MB download over mobile data takes a while, and there was
  nothing on screen during it. There is now a progress dialog, so the app no longer looks
  like it has hung or done nothing.

The install permission is also re-checked immediately before installing, since it can be
revoked between granting it and the download finishing.

## v0.0.3

**Share the app.** A new row on the home screen shows a QR code for the project page.
Point a phone camera at it and it opens the release page, which is the whole distribution
mechanism for an app that is not on any store. There is also a button to send the link
through any share target, and a note explaining the warning the recipient will see when
they install it.

The code is generated when the screen opens rather than being a bundled image, so it
follows the light or dark theme and can never fall out of sync with the link.

## v0.0.2

**In-app updates.** The app now checks GitHub for a newer release once each time it
starts. When one exists it shows the version and its release notes, and can download and
install it itself. Android asks permission to install apps the first time; that is the
only thing the permission is used for. Any network failure is ignored silently rather than
showing an error to someone who is offline.

**Version in Settings.** Settings now shows the installed version and build number, with a
*Check for updates* button and a link to the releases page. The automatic check only runs
at launch, so the button is there for when a release goes out while the app is already
open.

**Pricing disclaimer.** Every screen that shows a price now states that the figures are
estimates from incomplete data, may be outdated or wrong, and should not be treated as an
absolute reference. It appears only where a price is actually on screen.

**README.** The repository now explains what the app is, why Android and Play Protect warn
about a sideloaded APK, where the data comes from, and how to build it yourself.

### Note on version numbering

The app previously reported its version as `1.0.0`, which is *higher* than the `v0.0.1`
release tag, so the updater correctly concluded there was nothing newer and stayed quiet.
Versioning now follows the published tags. **The tag and `versionName` in
`app/build.gradle.kts` must match on every release** — if the tag is higher than what the
installed build reports, the app will offer the same update forever.

## v0.0.1

First release.

- **Equipment.** 220 Pentax K and M42 mount lenses with ratings, pricing and 118
  photographs. 110 camera bodies from the 1952 Asahiflex onward, with 96 photographs.
  Side-by-side comparison of any two lenses or bodies.
- **Film.** Labs, film stock by format, chemicals, and a placeholder for darkroom hire.
- **Repair and services**, **Social** (clubs and forums), **Other** (courses, gear
  websites), and **Settings**.
- Monochrome design throughout, with a light and dark mode setting.
