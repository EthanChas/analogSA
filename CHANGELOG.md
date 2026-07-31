# Changelog

## v0.0.11

**Photographs for the vintage Canon lenses.** 46 images from Wikimedia Commons covering
113 FD, FL and R lenses, each carrying its photographer and licence, shown beneath the
image and changing as you page through. Lens photographs now use the same credited format
as the camera ones; the field-guide scans, being your own, show no credit line.

A file is only accepted when its title names the maker, the mount and the focal length,
because a search for "Canon FD 50mm" otherwise returns camera bodies and unrelated lenses.
That is why coverage is 58 of 106 focal groups rather than everything.

**Why the remaining lenses have no rating**, having checked each against the source:

- 199 are listed on allphotolenses but nobody has reviewed them
- 131 have no listing at that focal length for that mount
- 36 have a listing at that focal length but for a different maximum aperture — a
  genuinely different lens, so deliberately not matched

Canon RF is absent entirely because allphotolenses has no RF catalogue; the page exists
and contains no lenses. R and FL are catalogued but almost nothing there is reviewed.

## v0.0.10

**Colour by rating**, off by default, under Settings. When on, the rating figure is tinted
so quality reads at a glance: 1–2 red, 3–4 orange, exactly 5 grey, 6–7 light green, 8–9
strong green, 10 purple. Values between bands take the band above, since only a flat 5 is
meant to read as neutral. The setting shows a colour key while it is on, and the palette is
lifted in dark mode so every band stays legible. Anything unrated is left alone.

**Canon ratings roughly tripled — 96 lenses now rated, up from 32.** The rating scraper had
been pointed at the wrong catalogue: `c_1` on allphotolenses is Contax/Yashica, not Canon
EF, so the largest Canon series had never been read at all. EF and EF-S are now included,
which took the collected data from 94 focal/aperture keys to 204, and the lenses matched to
a listing from 118 to 295.

Canon coverage is still well behind Pentax — 96 of 462 against 153 of 220 — because the
source genuinely has few Canon reviews, not because of the scrape.

All ratings remain on the ten-point scale. The allphotolenses scores are out of five and
are doubled on import; nothing in the dataset now sits above 10.

## v0.0.9

**Selected filters are now green.** A checked chip was the same tone as the card behind it
and effectively invisible. Selection is now the one place colour appears in an otherwise
monochrome app, in both light and dark.

**Brand logos are sized properly.** The Pentax wordmark is five times wider than it is
tall while the Canon one is nearly square, so a fixed height made Canon look tiny beside
it. Logos now fit inside a box rather than to a height, letting each grow until it hits
whichever edge constrains it.

**The booklet verdict scale is gone.** The field guides carried their own seven-point
scale, which was not comparable with the community ratings shown for both brands. It has
been dropped from 120 lenses and from the detail and comparison screens.

**Transitions.** Screens slide and fade rather than cutting, and list items rise into place
in sequence. Everything is 220ms or under, so nothing feels slower for it.

**Modularity.** Every data file and asset folder is now named in one place, `Catalogue.kt`,
which documents what adding a brand, camera bodies, a directory section or photographs
actually takes. The README carries the same table. Most additions are data-only: the list,
search, filter, comparison and detail screens are generic.

## v0.0.8

**Category selection is now inside the Filters sheet**, which is where it should have been
in v0.0.7. It was only on the chip row above the list, so opening Filters offered year,
rating and price but no way to pick EF, EF-M and EF-S together.

The sheet now has a Category section with a chip for every mount or series, any number of
which can be selected at once. Selecting none means all. The chip row above the list stays
in step with it, so the two never disagree, and Reset clears everything including the
categories.

## v0.0.7

**Advanced filters**, on both the lens and camera lists, for Pentax and Canon alike.

**Categories are now multiple choice.** The chip row selects any combination of mounts or
series — EF and RF together, or K, M and A at once — rather than one at a time. Selecting
none shows everything, which removes the need for an "All" chip that has to be kept in
sync with the rest.

**A Filters button** opens range controls for:

- **Released** — a year range, read from the introduction date.
- **Rating** — minimum and maximum, on the ten-point scale.
- **Price** — minimum and maximum in USD.

The button shows how many ranges are active. Sliders left at their extremes do not count
as filtering, so an untouched control never silently removes anything.

Ranges only appear where the data supports them: cameras get the year range and nothing
else, because bodies carry no rating or price. Anything with no value for an active filter
is excluded rather than quietly kept — a lens with no rating cannot satisfy "rated 8 or
better" — and the sheet says so next to the controls that behave this way.

## v0.0.6

**Canon lens names were wrong, and are fixed.** Lenses were appearing as "Canon 93 mm"
with a focal length of 600 mm, because the older mount tables rowspan their focal-length
cell across every variant of a lens. Continuation rows therefore arrive one cell short,
and every column read after that point was shifted — a "Dia. x Len." cell was being read
as the lens name, and a diameter as a filter thread.

Column alignment now accounts for the rowspan, and a name is only used if the focal length
inside it matches the focal length derived independently. Recovering those continuation
rows also added 36 lenses that had been dropped, taking Canon from 426 to **462**.

**Quality ratings for Canon**, from allphotolenses.com, which is the nearest equivalent to
the PentaxForums database the Pentax ratings came from. Its scores are out of five and have
been rescaled to the ten-point scale used elsewhere, with the same tier thresholds, so
"Excellent" means the same thing for both brands.

Coverage is thin and the app does not pretend otherwise: **32 of 462 Canon lenses carry a
rating**, against 213 of 220 for Pentax. There is no openly accessible Canon equivalent of
the PentaxForums review database, and most Canon entries there have no user reviews at all.
Everything unrated is shown as "No rating data" rather than being given a plausible number.

Two caveats worth knowing. Ratings are matched by mount, focal length and maximum aperture,
so generations sharing those figures share a rating — the four 50mm f/1.4 FD variants all
show the same score. And several ratings rest on one to three reviews, so the review count
is shown next to every score.

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
