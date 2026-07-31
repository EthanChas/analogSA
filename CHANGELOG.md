# Changelog

## v0.0.23

**Minolta is on the home screen**, with its logo. No lenses or bodies yet — the category is
there ready for them.

Brands now come from a `brands.json` list rather than being inferred from whatever appears
in the lens file, which is what makes an empty brand possible at all. It also fixes the
ordering, which used to shuffle as lens counts changed.

**The Canon logo is 50% bigger, and the haze behind it is gone.** The cause turned out not
to be the layout, which is where the previous two attempts at this went. The file was
320x240 but the Canon wordmark inside it is only 304x64 — the rest was near-transparent
padding, and since the logo is scaled by its canvas rather than its artwork, that padding
was shrinking the wordmark to about a quarter of the space available. Trimming the canvas
scales the artwork back up. Those faint pixels were also rendering as a visible tinted
rectangle behind the logo, which is now cleared.

The Minolta wordmark is recoloured to the blue of its own symbol. It is black in the
original, which would have disappeared against the dark theme; both other brand logos are a
single mid-tone colour for exactly that reason.

## v0.0.22

**Canon camera bodies are in — 89 of them**, spanning 1933 to 2004, so Canon is no longer
lenses-only. They are grouped into eleven series that follow Canon's own history:

- **Rangefinder** (18) — Kwanon prototype, Hansa Canon, the VT, L and VI bodies, the P, the 7 and 7s
- **Canonflex, R mount** (4) — Canon's first SLRs
- **FL mount** (6) — including the pellicle-mirror Pellix
- **F series** (8) — F-1, FTb, New F-1
- **A series** (6) — AE-1, A-1, AE-1 Program
- **T series** (5) — T50 through the T90, and the Cosina-built T60
- **EOS** (13) — EOS 650 through the EOS-1V, including the APS bodies
- **Canonet** (11) — including the G-III QL17
- **Compact autofocus** (6) — the AF35M and the Sure Shot / Prima / Autoboy family
- **Half-frame** (9) — Demi and Dial
- **110 format** (3)

Each carries its years, mount, format, focus type, lens compatibility, and notes on what
made it distinct. No photographs yet.

Where the source list deliberately groups a family — the postwar Leica-thread run, the
70-plus Sure Shot variants, the Rebel/Kiss badge variants — the group is kept as one entry
rather than inventing per-model years that are not recorded.

## v0.0.21

**A one-time notice before the gear pages.** Opening Equipment information for the first
time now explains that the prices are estimates, may be outdated or wrong, and that the
condition of a lens directly affects what it is worth — fungus, haze, separation or a stiff
focus ring can put the same lens at a fraction of the figure shown. It appears once and
then not again.

**A support screen**, on the home menu under a heart, with the Ko-fi page
(ko-fi.com/ethanwispy) and an address for corrections and inquiries
(ethanchasb@gmail.com). Both also appear at the bottom of Settings.

## v0.0.20

**The film list goes from 38 stocks to 112.** This was the real reason films looked
missing. Searching Takealot harder could not help, because most of what it sells had no
entry in the app for a price to attach to — six of the nine Takealot links reported missing
were stocks the app had simply never listed.

The list is now built from Cape Film Supply's own catalogue, which tags every product with
its format, brand, film type and ISO, plus stocks the other shops carry that they do not.
Newly listed: the whole Ilford range (Delta 100/400/3200, FP4, HP5, Pan F 50, XP2, SFX,
Ortho), Kentmere Pan 100/400, Harman Phoenix and Phoenix II, CineStill 50D/800T/400D/BWXX,
the Lomography range, Ektachrome E100, Kodacolor, AgfaPhoto APX 100/400 and Colour 400,
Fomapan in every format, Kodak's respooled Vision cine stocks, Polaroid 600, SX-70 and
i-Type, Instax Square and Wide, and the budget Takealot stocks (Lucky SHD 400, Bea's
Choice, Crystal Film).

**111 of the 112 now show a live price.** The one that does not, Kodak Pro Image 100, is
genuinely not stocked by any of the seven shops. Every match was verified by running the
shipping code against live shop data.

**Film entries were showing the wrong logo.** They carried the logo of a *retailer* rather
than the film's maker — Ilford FP4 was showing a stock photograph of a wine glass from a
shop's website. Film now carries its maker's mark: Kodak, Ilford, Fujifilm, Foma and
Harman, covering 81 of the 112 stocks. The rest show no logo rather than a wrong one.

**Matching is stricter again, and had to be.** A match now needs *every* distinguishing
word, not just one in common. With only one required, every Kodak Vision stock quoted the
cheapest Vision roll and every Instax pack quoted the Mini price. Also fixed along the way:

- Speeds welded into a word are read, so APX 100 stops quoting APX400's price.
- 24 and 36 exposure rolls are 35mm, so a 120 entry no longer quotes a 36-exposure roll.
- Phoenix and Phoenix II are told apart.
- Numbers that are not film speeds now identify a product, which is what separates
  Polaroid 600 from SX-70 and Vision3 5219 from 5207.

**Takealot gets 12 more searches**, including the plain-language ones that surface stock
sold under unfamiliar brand names.

**Amazon was looked at and is not usable.** amazon.co.za answers every request, including
its own home page, with an empty bot-check response and no product data. There is no public
product feed; their Product Advertising API needs an affiliate account with qualifying
sales. Nothing can be read from it without credentials.

## v0.0.19

**The app is now called AnalogSA**, with the camera-and-flag logo as its launcher icon and
at the top of the home screen. The package id is deliberately unchanged, so this installs
over your existing copy as an update rather than arriving as a second app.

**Takealot is searched far more thoroughly.** Two things were limiting it. A search returns
36 results however many exist — "35mm film" alone has 51 — and the cursor to the rest was
never followed. And the eight searches were mostly generic ("kodak film"), which buries
individual stocks. There are now 41 searches, by stock name as well as by brand, and each
one is paged to the end. Takealot went from 273 products to 1,160, and from 7 of your film
stocks to 11.

**A progress bar during refresh**, naming each shop as it is read. With seven shops and 41
Takealot searches a refresh is no longer instant, and it should look like work rather than
a hang.

**Matching got stricter again, because a bigger catalogue means more collisions.** Searching
harder turned up three listings wearing film names: a Yamaha T-MAX key shell, a Bronica
"Split Image" focus screen, and a "Vision" security camera — each one would have shown as a
film price. A match now also has to agree on the maker, with the trade names that stand for
it (Eastman is Kodak, Kentmere is Ilford, Instax is Fujifilm).

Three more corrections found while testing:

- Spacing no longer breaks a match: "Pro Image" now finds "ProImage".
- "120mm", which is how several shops write medium format, is recognised as 120. A 35mm
  roll was quoting a 120 price through that gap.
- 24 and 36 exposure rolls are told apart, so Fomapan 100 135-36 stops quoting the 135-24
  price.

Across all seven shops, 34 of 38 film stocks now show a live price, and every match was
checked by hand. Of the four without one, three are genuinely not stocked anywhere on the
list (Pro Image 100, and Portra 400 in 4x5) and one is a catch-all entry with no single
product behind it.

## v0.0.18

**Cape Film Supply is now checked for stock.** It is the first shop on the list that sells
nothing but film, and it fills the gaps the general retailers leave: Portra, Ektar, HP5 and
Tri-X are all carried there and were showing no price anywhere before. Film stock coverage
goes from 24 of 38 stocks with a live price to 35 of 38.

**Three matching corrections**, all of them things that were quietly showing the wrong price:

- Hyphens are no longer treated as word breaks. "T-Max" was splitting into "t" and "max",
  and matching a GoPro **MAX** battery. It is now one word, so it only matches T-Max.
- Film format is respected. A 35mm roll no longer quotes the price of the same stock in 120,
  which is a different product at a different price.
- Accessories are excluded. Instax Mini film was matching a *photo album* for Instax prints.
  Albums, cases, straps, batteries, holders and the like are no longer treated as film.

## v0.0.17

**Takealot is now checked for film stock**, alongside Truth Photo, Outdoorphoto, Cameraland,
ORMS and Expired Film. Its catalogue is far too large to pull wholesale, so it is searched
instead: a fixed set of film searches, pooled and de-duplicated by product id, giving about
100 film products with live price and stock.

**Product matching is much stricter, which matters more than the new shop.** Matching on any
two shared words was pairing Kodak Portra 400 with Kodak UltraMax 400, Fomapan 400 with
AgfaPhoto 400, and Kodak Ektar 100 with an Ektar *camera* — all at prices belonging to a
different product entirely.

A match now needs a genuinely distinctive product word in common, ignoring the words half
the catalogue shares — kodak, film, colour, 35mm, professional and the film speeds. Where
both sides state a speed, the speeds must agree, and a film never matches a camera that
shares its name.

On Takealot this took the film stocks from 21 matches, mostly wrong, to 7 that are all
correct: Gold 200 to Gold 200, ColorPlus to ColorPlus, Instax Mini to Instax Mini,
UltraMax 400 to UltraMax 400, Double-X to Eastman Double-X. Fewer results, but each one is
the product you were actually looking at.

## v0.0.16

**The Truth Photo logo is in**, covering all 17 of their listings across labs, film stocks
and chemicals. It is pure white artwork on transparency, drawn for a dark background, so
in light mode the app puts a dark backdrop behind it rather than letting it disappear into
a white card — the contrast handling added in v0.0.15 doing exactly what it was written
for.

Every logo reference in the directory now resolves: 111 listings pointing at 87 files,
with nothing unresolved and nothing orphaned.

## v0.0.15

**Watch stock.** Open a film stock or chemical and tap **Watch stock**. Every hour the app
re-reads the shop feeds and tells you when something changes:

- it comes **back into stock**, with the cheapest price and how many shops have it
- it **sells out** everywhere being checked
- it drops to the **last few**

Notifications fire only on a change, never on "still in stock" — an hourly reminder that
nothing happened is noise, and noise gets muted, which would defeat watching entirely.
The state when you start watching is recorded first, so the next check compares against
that rather than announcing a return from nothing.

A failed fetch is treated as a failure and retried, never as "everything sold out".

One limit worth knowing: **low-stock warnings need a shop to publish how many are left.**
The WooCommerce Store API does, so Expired Film reports it; Shopify's public feed gives
availability only, so Truth Photo, Outdoorphoto, Cameraland and ORMS can report in or out
of stock but never "three left". The app says so next to the button rather than implying
the warning covers everything.

The hourly check is scheduled only while something is watched, stops when the last item is
unwatched, and survives reboots.

**Logos for the directory.** 94 businesses now carry their own logo — labs, repairers,
film retailers, forums, schools and gear shops. Each was taken from that business's own
website, preferring what the site itself declares to be its logo: a schema.org
Organization logo first, then the image it uses when shared, then its touch icon, then its
favicon. 69 came from the sites directly and 17 from a favicon service.

**The logo always appears on a listing's own page.**

**New setting: Show logos in lists.** With it on, each row in a directory carries its logo
above the name, so a lab or repairer is recognisable while scrolling rather than having to
be read. Off by default, and rows without a logo keep their normal text layout. The choice
takes effect as soon as you return from Settings.

Logos are cached in memory once decoded, because a scrolling list asks for the same
handful repeatedly and decoding each time would make it stutter.

Coverage by section: forums 7 of 7, gear websites 15 of 18, clubs 13 of 39, repairers 16
of 26, labs 10 of 13. Anything without a website has nothing to fetch, and a few sites
publish no usable image at all — Truth Photo declares an image that returns a 404 and has
no favicon either.

## v0.0.14

**Brand logos are balanced by area rather than by a bounding box.** The Pentax wordmark is
five times wider than it is tall and the Canon one is nearly square, so any single
constraint favours one of them — fit the height and Pentax spans the whole card, fit the
width and Canon shrinks to a third of it. The logo box is now taller and inset
horizontally, which caps how far a long wordmark can run while letting a squarer mark grow.
On a typical screen the two now occupy 11,349 and 10,325 square dp; Canon was previously
less than half of Pentax.

## v0.0.13

**Live prices and stock for film and chemicals.** Open a film stock or a chemical and tap
Refresh prices and stock: the app reads the product feeds of five South African shops and
shows what each has, at what price, and whether it is in stock. Tapping a listing opens it
in the shop.

Shops read: Truth Photographic Company, Outdoorphoto, Cameraland, ORMS Direct and Expired
Film — about 3,000 listings, with 35 of the 38 film stocks finding a live match.

Truth Photo needed tracking down: truth.photo is a static site with an embedded Shopify
shop, so its products live on a separate domain, and the app reads that shop's feed.

Only shops publishing a machine readable feed are used — Shopify's `products.json` and the
WooCommerce Store API — which is why this works where scraping product pages would not.
Nothing is fetched until you press refresh, and results are cached with the time of the
check shown, so a stale price is never presented as live.

**Places get a Google Maps link rather than a star rating.** Reading Google ratings in an
app needs their Places API and a billed key, and scraping them from search results is
against Google's terms and breaks whenever the markup shifts. Repairers, labs, clubs and
shops now have an Open in Google Maps button, which shows the rating, reviews and
directions from Google itself with nothing to configure. Where the source PDF carried a
map pin, that exact pin is used.

**Lenses deliberately have no live stock.** Shop listings do not distinguish lens
generations, so a 16-35mm f/2.8 II matched the I and the III as well and showed a price
belonging to none of them.

## v0.0.12

**The supplied Canon ratings are in.** 151 lenses scored, every line parsed and every name
matched — nothing was dropped or guessed at. Scores in that file are out of five and have
been doubled onto the ten-point scale used everywhere else.

**Canon rated lenses go from 96 to 241.** The vintage mounts are now essentially complete:
FD 126 of 133, FL 31 of 33, R 9 of 21. Across both brands, 394 of 682 lenses carry a
rating, up from 249.

Where a lens already had an allphotolenses score, the supplied file wins — it is
hand-checked and draws on more sources for vintage glass, which is exactly where the
scraped database is weakest. That affected 6 lenses.

Each lens records which method produced its score, so the two remain distinguishable: the
scraped community scores and the ratings derived from prose verdicts across review sites
are both named in the source line on the detail screen.

Remaining gaps are concentrated in RF (98) and the rest of EF (84), which the supplied
vintage run put out of scope.

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
