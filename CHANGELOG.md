# Changelog

## v0.0.45

**Price history on watched items.** The hourly stock check was already fetching every
shop's price and then keeping only whether anything was in stock. It now keeps the number.
A listing you have been watching shows a sparkline, the cheapest it has been in 90 days and
the date that was, and how far above that it is sitting today. A manual refresh counts as a
reading too, so history builds up just from browsing.

Only the cheapest in-stock price is kept, not a series per shop, because the useful figure
is what you would actually have paid. Nothing in stock records no reading at all rather than
a zero, so the gap in the line is real.

**Notifications on a price drop**, not only on a restock. A fall of R10, or five percent,
whichever comes first, so rounding and exchange-rate drift stay quiet. If it is also the
cheapest in 90 days, the notification says so.

**Compare labs.** A button on the labs list opens all 17 side by side: develop price from,
turnaround in working days, and which chemistries each runs, sortable by price, speed or
name and filterable by process. Seven of the seventeen publish a price. The other ten sort
to the bottom and say "not published" rather than being quietly treated as free, which is
what sorting an unknown as zero would have done.

**Battery guide**, under Other. Six cells, four of them long dead, with what to put in
instead and what it does to your meter. A PX625 replaced with a 1.5V alkaline makes the
meter read the scene brighter than it is and under-exposes by half a stop to a stop, which
is the single most common reason a meter that looks fine is not. Zinc-air, MR-9 adapter,
WeinCELL and alkaline are each given with their real trade-offs.

Camera pages whose battery is one of these now carry the warning directly, with a link
through to that cell. Where the catalogue records only "1.35V mercury cell" without naming
it, the warning says exactly that instead of guessing a part number, since a Spotmatic told
to buy a PX625 when it wants a PX400 has been misinformed rather than helped.

**Kameraz added**, in Johannesburg. Contact details filled in for RGB Pixel Lab, Ricky,
Eugene Lin, Tracy Kahn, Outdoorphoto and Ludwig's, and the two duplicate Radiolens rows
merged into one.

## v0.0.44

**125 digital-only Canon lenses removed**: 98 RF, 15 EF-M and 12 EF-S, running to 2026. No
film camera ever made takes any of them. This is the lens half of the cull done to the bodies
in v0.0.40, which was never followed through. Canon goes from 462 lenses to 337.

EF stays. It is not vintage, but thirteen of the Canon film bodies in the app take it, from
the EOS 650 of 1987 to the EOS 300 of 2004, and it is the only autofocus mount you can shoot
film with. `Mounts` still knows RF, EF-S and EF-M as digital-only, so re-adding one by
accident cannot make it look compatible.

**Records whose catalogue entry has gone are now shown, not dropped.** They appear in Your
equipment flagged **Not in the catalogue**, and tapping one offers to delete it or keep it.
Silently vanishing is how the watch list and the equipment list both went wrong before, and
a record can outlive its entry whenever something is renamed or removed.

**Fixed a data-loss path in the v0.0.43 migration.** A record whose stored position was past
the end of the current catalogue was cleared before a new home for it had been found, so it
was deleted instead of carried over. Nothing is cleared now until the destination is known.
Shortening the lens list in this release is exactly the case that would have triggered it.

## v0.0.43

**Fixed: your equipment turning into other cameras.** Records were filed under the item's
position in the catalogue, not the item. The position is a property of the list, so removing
the 39 digital Pentax bodies and adding 61 Nikons renumbered everything after them, and every
saved record silently came to rest on a different camera. An AE-1 became a Canonet.

Records are now filed under the brand and the name, which do not move when the catalogue is
rebuilt. This class of bug cannot happen again.

**The records that already moved cannot be put back automatically.** There is no way to tell
which version of the catalogue a given record was saved against, and guessing would just be a
different wrong answer stated confidently. So every existing record is carried over intact,
with its notes, serial, service history and shutter tests, and marked **Check this is right**
in orange in Your equipment. Open one and you get two buttons: confirm it, or move the whole
record to the right item, picked from the catalogue. Nothing you typed is lost either way.

**22 Canon lenses renamed** so no two share a name. The source had dropped the version suffix,
so the 1995 and the 2001 "EF 70-200mm f/2.8 L" were separate entries with identical names,
which showed as two identical rows and would have collided under the new keys. They now carry
their introduction year. They are different lenses and both are kept.

## v0.0.42

**The dead "Refresh prices and stock" button is gone from lens and camera pages.** It was
already hidden on lenses, but camera bodies share the same layout and never hid it, so every
camera page carried an empty offers card with a button that did nothing when pressed.

Neither screen was ever going to work. Shop listings do not distinguish lens generations, so
a 16-35mm f/2.8 II matches the I and the III as well and reports a price that belongs to none
of them, and there is no usable feed for second hand bodies at all. Film and chemicals keep
their offers card, where the lookups are real.

## v0.0.41

**20 Olympus camera bodies**, so Olympus is no longer an empty badge. The whole OM line from
the OM-1 of 1972 to the Cosina-built OM-2000 of 1997, the three Pen F half-frame SLRs, and
the FTL, the odd M42 screwmount body Olympus sold for barely a year before the OM-1 arrived
and made it pointless.

**Nine Olympus history pieces**: the FTL, OM-1, OM-2, OM-3Ti, OM-4T/OM-4Ti, OM-10, OM-2000,
Pen F and Pen FT. Forty-six bodies now carry one.

**65 Mamiya-Sekor lenses**, so Mamiya is no longer an empty badge either. Twenty-seven in M42
screw, nineteen on the 35mm E bayonet, eight for the 645 system, four for the RB67, and a
handful in Exakta and other mounts. Fifty of them carry a rating.

The M42 ones are the useful part for most people: they fit every M42 body in the app, which
is nineteen Pentax screwmount cameras plus the Olympus FTL. `Mounts` now also knows the OM,
Pen F, Mamiya E, Mamiya 645, Mamiya RB and Exakta mounts, and knows that none of them
interchange, whatever the shared brand name suggests.

**Ricoh and Leica are on the home screen**, with their logos. No lenses or bodies yet.

## v0.0.40

**Mamiya is on the home screen**, with its logo. No lenses or bodies yet.

## v0.0.39

**61 Nikon camera bodies**, 1948 to 2004, so Nikon is no longer lenses-only. Seven series:
the professional F line, the Nikkormats, the manual-focus enthusiast bodies, the autofocus
F and N series, the pre-F rangefinders, the Nikonos underwater cameras, and the APS and
premium compacts. Autofocus bodies keep both names, since an F-801 and an N8008 are the
same camera on different continents. The 111 Nikkor lenses already in the app now have 43
bodies to fit.

**Twelve Nikon history pieces**: the SP, F, F2, F3, F5, F6, FM2, FM3A, Nikkormat FTN,
Nikonos V, L35AF and 28Ti.

**39 digital bodies removed.** All of them were Pentax: thirty APS-C DSLRs, two full-frame,
the K-01, the four Q bodies and the 645D and 645Z. Canon had none to remove; that list was
built from a film-only source in the first place.

The cull was done on the format, not the lens mount. Pentax's SF, Z and MZ film bodies all
use the KAF autofocus mount, so filtering on the mount would have deleted twenty-three film
cameras along with the digital ones. `Mounts` also no longer describes KAF as digital-only,
which was wrong, and now recognises the Nikon S and Nikonos mounts.

## v0.0.38

**History / Philosophy**, a drop-down on the cameras that earned one. Twenty-five bodies
carry a piece of about two hundred words covering four things: what kind of camera it
actually is, why it mattered at the time, what the company was trying to do and believed
it was for, and where it stands today — who shoots it now, what it costs in reputation,
and what to check before buying one.

- **Pentax** — Asahiflex I, Asahi Pentax, Spotmatic, K1000, MX, LX, 6x7
- **Canon** — Canon P, Pellix, F-1, New F-1, AE-1, A-1, T90, EOS 650, EOS-1V, Canonet G-III QL17
- **Minolta** — SR-T 101, XD, X-700, Maxxum 7000, Hi-Matic, Hi-Matic 7SII, CLE, TC-1

Deliberately not every body. A note on a camera that changed how the industry worked is
worth reading; the same treatment on every budget variant would be padding, and would
teach people to skip the section. The other 231 bodies simply do not show the card.

It is collapsed by default, because someone looking up a flash sync speed should not have
to scroll past an essay to reach the table.

## v0.0.37

**Your name now travels with your code.** Sharing asks for it once, before it will
generate anything, and it can be edited from the same screen afterwards.

**Adding a friend no longer asks who they are** — the code says so. Paste it and they are
filed under their own name straight away.

**A second code from the same person updates their list rather than duplicating them**, and
says what actually moved: how many items were added and removed on each of the owned and
wanted lists. If nothing has changed since last time, it says that too, so re-adding a code
is never a silent no-op you cannot tell apart from a successful update.

The name is percent-encoded inside the code, so names containing a comma, a bar, an accent
or a colon survive the trip intact. Codes made by the previous version still work — they
simply carry no name, and adding one still asks who it belongs to. Codes made by this
version can also be read by the previous one, which ignores the name and takes the lists.

## v0.0.36

**Friends' equipment.** Your equipment now has two buttons: **Share mine**, and a blue
**Friends' equipment**.

Share mine turns your list into a code, shown as text and as a square. Send it however you
like — it carries the list itself, so there is no account, no server, and nothing to sign
up for. Add a friend takes a pasted code, asks who it belongs to, and files their gear
under their name with the same I have / I want tabs. Tap anything of theirs to open it in
your catalogue; hold a friend to remove them.

**There is no scanner to install and no camera permission.** If someone sends the square
instead of the text, any phone's own camera app will read it and hand back the code to
paste. That keeps the whole thing to one text field.

**Only what you have marked is shared.** Your notes, serial numbers, service history and
shutter tests are never in the code.

**Items are identified by name, not by position in the data files.** Positions shift every
time gear is added, so two people on different versions would otherwise read each other's
lists as entirely different lenses. Anything in a friend's list that your copy has never
heard of is counted and reported rather than quietly dropped.

A typical share is under 200 characters; 150 items still fits comfortably inside a QR code.

## v0.0.35

**Lenses now tell you whether they fit a camera you own.** Once at least one body is marked
"I have this", every lens page says either which of your cameras it goes on, or plainly
that none of them take that mount — which is the more useful of the two, since it is the
mistake this is here to prevent.

Only native fits count. Almost anything can be adapted to almost anything given enough
money and a lost infinity focus, and a note saying "compatible" has to mean you can put it
on and shoot. So:

- K, M, A and KA lenses fit every K-mount body, autofocus ones included, but not the 645
  or 67 medium format bodies.
- FD and FL share a mount and are treated as interchangeable.
- M42 screw is kept separate from the K bayonet.
- EF-S, EF-M and RF are digital-only and match no film body at all.
- Minolta A and Minolta SR are different mounts and are not confused with each other.

## v0.0.34

**Your equipment** — the app now keeps track of what you own and what you are after. It
sits above the brands in Equipment information, with two tabs, I have and I want.

Every lens and camera page has **I have this** and **I want this** at the top. Tapping the
one already set clears it, so there is no third button meaning "neither".

**A record for anything you own.** Notes and a serial number for lenses and bodies alike,
and for bodies also a service history and a maintenance checklist: light seals, mirror
foam, shutter speeds, meter, battery contacts, focus screen.

**Shutter speed accuracy.** Fire each marked speed with a tester, enter the time it
actually measured, and the error is shown in stops rather than milliseconds — a third of a
stop means the same thing at 1/1000 as it does at one second, and a millisecond does not.
Within a third of a stop is green, within two thirds orange, beyond that red, since a third
is roughly where an exposure error starts to show on film. The worst speed is summarised at
the top of the table and beside the camera in your list, so a body that needs attention is
visible without opening it.

**Service reminders.** Record when a body was last given a clean, lubricate and adjust and
the app tells you when the next one is due — default every seven years, adjustable to
three, five or ten. Lubricants stiffen and seals perish whether a camera is used or not,
which is exactly the sort of thing nobody remembers years later. Each camera is announced
once per due date rather than nagging daily, and the reminder is checked once a day since
the event is years away.

All of it stays on the phone. None of it is uploaded — a serial number and a service
history are not things to hand to a server — and it is lost if the app is uninstalled.

**Multi-packs are labelled.** A blue **KIT / PACK** tag now sits above any listing that
sells more than one: five-packs, 100ft bulk rolls, 2+1 free, double packs and starter kits.
A five-pack of Portra at R2 150 is not dearer film, but the price alone does not say so.
Listings marked "(Single)" or "(1 Pack)" are deliberately left alone.

**Wanted items are starred** in the lens and camera lists, beside the rating, so a wish
list is visible while browsing rather than only in its own screen.

**Logos in lists and colour-by-rating are now on by default.** Both were off, which meant
most people never saw either. Anyone who has already turned one off keeps it off — a stored
choice still wins over the default.

## v0.0.33

**The cheapest price now shows next to each film in the list**, so the whole list can be
read at a glance instead of opening every stock in turn. It is the lowest price a shop is
confirmed to actually have in stock — an unverifiable price is not a price you can go and
pay, so out-of-stock and un-refreshable listings are left out of it.

Working that out means walking several thousand offers per film, so it is done once in the
background when the list opens rather than while rows are being drawn. The search bar shows
its progress bar until the prices land, and the list is usable the whole time.

**Amazon film is in, marked as un-checkable.** Amazon publishes no product feed and blocks
reading its pages — the app cannot see its stock and never will — so 20 listings are
recorded by hand and shown in orange with **CANNOT VIEW LIVE STOCK — CHECK MANUALLY**. They
sort below anything the app can verify, and they never count toward the cheapest-in-stock
price in the list, because nobody can confirm they are in stock.

17 of those attach to films already in the app, including three that took a new rule to
match. Amazon sells Kodak cine stock respooled under reseller names — "Bea's Choice 5219",
"YUR Films Double-X 5222" — so the maker never agrees even though it is literally the same
emulsion. Where both sides quote the same Kodak emulsion code, that now settles it and the
maker check steps aside. The remaining three are unbranded ECN-2 film with no equivalent
listing in the app.

## v0.0.32

**A much better Olympus logo, and Yashica finally has one.**

The Olympus mark was lifted off a 400 x 140 screenshot and then scaled up, which left it
soft. The replacement comes from a 1600 x 960 file that already carried proper
transparency, so it only needed trimming and scaling down — no keying, no upscaling, and
it is a third of the file size of the one it replaces.

Yashica was showing the generic camera glyph. Its wordmark is plain black, so the app tints
it to match the theme, the same as Nikon.

All six brand logos now render from artwork at or above the size they are displayed at.

## v0.0.31

**Yashica and Olympus are on the home screen**, taking the app to six brands.

**92 Yashica lenses** come with it, so Yashica arrives with a catalogue rather than empty.
The app now holds 1,005 lenses. They are grouped by mount, which is what decides whether a
lens will physically fit:

- **C/Y** (46) — the Contax/Yashica bayonet, from 1975
- **M42** (34) — the Auto Yashinon, Yashinon-DS, DX and Yashikor screwmount lenses
- **Yashica AF** (5) — the short-lived early-1980s autofocus mount
- Plus a handful listed on other mounts: Contax G, Pentax K, T2 and Praktica B

**73 carry a rating; 19 do not.** Unlike the Nikkors, a real crowd-rated source exists here,
so these are AllPhotoLenses user star averages doubled onto the same /10 scale as the rest.
The nineteen with no votes logged are marked unrated rather than guessed at — the
catalogue's own note points out these tend to be rarer variants or duplicate listings, not
necessarily poor lenses. Each record carries a note on what its mount will and will not fit,
and Contax-branded Carl Zeiss lenses are deliberately excluded even though they share the
C/Y mount.

**Olympus is listed with its logo but no gear yet**, the same way Minolta and Nikon started.

## v0.0.30

**111 Nikon lenses**, so Nikon is no longer an empty category. The app now holds 913 lenses
across four brands.

These are the manual-focus F-mount Nikkors — Pre-AI, AI and AI-S, plus the five Series E
lenses — with autofocus AF/AF-D/AF-S deliberately left out as a separate, much larger
generation. They are grouped by **mount generation**, because that is the distinction that
actually matters when buying one: a Pre-AI lens will not meter on many bodies without being
converted.

- **AI-S** (33), **AI / AI-S** (24), **Pre-AI (F)** (18), **Pre-AI / AI** (18),
  **Pre-AI / AI / AI-S** (10), **Series E** (5), **AI** (2), **AI-P** (1)

**41 carry a rating out of 10; 70 do not**, and the difference is recorded on each record
rather than hidden. The catalogue's own note is explicit that no crowd-sourced database
exists for manual Nikkors, unlike PentaxForums or Dyxum, so those 41 scores are a hand-built
synthesis of written reviews. Each says so in its source line: they are directional, not a
crowd-sourced average. The other 70 keep a description and no invented number.

Every rated lens links to the review it came from — Photography Life, Casual Photophile,
Richard Haw and others.

The finer lens categories are kept as the source gave them, so Fisheye, Perspective Control,
Mirror/Reflex, Super-telephoto and the UV and Medical specialities are all searchable by
name rather than flattened into "prime" and "zoom".

## v0.0.29

**57 Minolta camera bodies**, 1947 to 2003, so Minolta now has both lenses and cameras. The
app holds 256 bodies across three brands. Nine series:

- **SR-mount SLR** (15) — SR-2 through the X-700, including the SR-T 101 and the XD
- **Hi-Matic** (15) — the 1962 original through to the GF
- **Maxxum / Dynax / Alpha AF** (13) — the 7000 through to the Dynax 60
- **Minolta 35 rangefinder** (3) — the Leica-thread bodies Minolta started with
- **110 and 126 pocket** (3), **Other** (3), **Leica collaboration** (2) — the CL and CLE
- **16 subminiature** (2), **Premium compact** (1) — the titanium TC-1

Each carries its years, mount, format, focus type, lens compatibility and what made it
distinct — the SR-7 being the first 35mm SLR anywhere with a built-in meter, the XD being
the first with both automatic exposure modes, the Maxxum 7000 being the camera that proved
autofocus SLRs worked, and the Hi-Matic that John Glenn took into orbit.

Where the source declines to itemise a family — the sixteen subminiatures, the Autopak line,
the Freedom and Riva compacts — that family is one entry rather than a set of invented model
years. The Vectis APS system and the half-frame Repo are listed for completeness, flagged as
noted in passing rather than covered in detail.

No photographs yet.

## v0.0.28

**25 listings added from the r/FilmPhotoZA resource page**, checked one by one against what
was already in so nothing is duplicated.

- **Darkrooms is no longer empty** — the Wits School of Art darkroom and the Market Photo
  Workshop. Both are teaching facilities closed to the public, which is recorded on each.
- **Four Cape Town labs**: Lady & Co, Tothills Photo-chemists, Noyes Pharmacy and Gallery F.
- **Eight communities**: Film My Soul in Johannesburg and Cape Town, the film photography
  WhatsApp group, Vintage Film Trader SA, Vintage Camera Trader SA, Analogue Cape Town,
  Nightcrawlers, and the Richmond Studio Cafe.
- **Eleven sellers and suppliers**: Crystal Film SA (the Lucky stock already priced in the
  film list), Skiet Film Cameras, Vintage Film Cameras, Red October, Film Camera Shop,
  Frame CPT, Tracy Kahn, Bromix Nielzek, ANVL Leather, and two people who supply darkroom
  chemistry and gear directly.

**A countdown on watched items**, reading "Refresh in MM:SS" and ticking every second, so
the hourly check is visible rather than something you have to take on trust. Android decides
when a periodic job actually runs, so once it goes past due the line says so instead of
counting into negative numbers.

**Search now waits for you to stop typing**, showing a bar while it waits. Filtering eight
hundred lenses on every keystroke was wasted work and made the list feel like it lagged
behind the keyboard; it now runs once, a fifth of a second after the last letter.

**The refresh in Settings has the same progress bar** as the one on a listing, naming each
shop as it goes. It was the one long operation left with no feedback at all.

## v0.0.27

**The watch button and live stock are back on every film stock.** They were missing from 29
of the 112, including all the Fomapan.

The whole live-stock card — prices, the refresh button, the progress bar and the WATCH
button — was only shown when a listing happened to carry a price field. Those 29 stocks are
the ones added by hand from shops other than Cape Film Supply, and none of them had a price
recorded, so the entire section was hidden and there was no way to watch them. Whether
something is buyable is a property of the section it sits in, not of how complete its record
happens to be, and that is now what decides it. Six chemicals were hidden the same way and
are also fixed.

**Prices filled in for those 28 stocks**, read from the shops that actually stock them, so a
page is not blank before its first refresh. Film stocks with a price go from 83 of 112 to
111 of 112; the last is Kodak Pro Image 100, which no shop on the list carries.

## v0.0.26

**Fixes watched items disappearing.** This was caused by v0.0.20, where the film list was
rebuilt and every stock renamed — "FOMAPAN 100 (135-24)" became "Foma Fomapan 100". A watch
is stored under the listing's name, so every existing watch was left pointing at a name that
no longer existed: the button showed unwatched and the hourly check went looking for
products that were not there.

Watches are now pointed back at their listings automatically, by matching on the words a
stored name shares with a current one, with the film format required to agree so a 35mm
watch cannot land on the 120 roll of the same stock. Of the stocks watchable before the
rebuild, 23 of 24 reattach; the one that does not is the old "Kodak B&W films (various)"
catch-all, which had no single product behind it. **Nothing needs to be re-tapped.** This
also runs in the background worker, which can start without any screen being opened.

**Film stocks sold in more than one format now have distinct names.** The rebuild left 29
names duplicated across 63 entries — three separate listings were all called "Foma Fomapan
100". Since a watch is keyed by name, watching one silently watched all of them, and they
shared a single stock state between three different products. Names that clash now carry
their format: "Foma Fomapan 100 (35mm)", "(120)", "(4x5 sheet)". Stocks sold in only one
format are unchanged.

## v0.0.25

**120 Minolta lenses**, so Minolta is no longer an empty category. The app now holds 802
lenses across three brands.

They come in two families, and the app keeps them apart because the evidence behind them is
genuinely different:

- **Maxxum / Dynax AF (A mount)** — 92 lenses, 1985 to 2006, each with a Dyxum
  crowd-sourced score out of 10, its year, its review count and a link to its entry.
- **MC / MD Rokkor (SR mount)** — 28 manual-focus lenses. There is no crowd-sourced score
  for these anywhere, so rather than invent one they carry a reputation tier and the
  written basis behind it, quoted from the review it came from.

That means Minolta lenses will look different from Pentax and Canon under the colour-by-rating
setting: the AF lenses are tinted, the Rokkors are not, because they have no number to tint
by. That is deliberate — an invented score would be worse than an honest blank.

Two things worth knowing about the data:

- The AF 3x-1x Macro is specified by magnification rather than focal length, so it sorts
  without a focal length. Its aperture is recorded.
- One lens in the list, the AF DT 11-18mm, is Minolta's APS-C line and cannot cover a 35mm
  frame. It is kept, but marked as not usable on a film body.

Also fixed: a stray character that had been showing in place of the separator in Canon lens
feature and source lines.

## v0.0.24

**Nikon is on the home screen**, with its logo. No lenses or bodies yet, same as Minolta.

**Brand logos with no colour of their own now follow the theme.** The Nikon wordmark is
plain black, which would have disappeared against the dark theme. Rather than repainting
the artwork — as the Minolta wordmark needed, because it sits beside a blue symbol that had
to stay blue — a monochrome mark is now tinted with the same colour the text uses, so it
comes out near-black on light and near-white on dark.

The test is the mark's own saturation, not a list of brand names, so it keeps working for
whatever gets added next: Pentax at 255, Canon at 235 and Minolta at 196 are left exactly
as drawn, and Nikon at 0 is tinted.

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
