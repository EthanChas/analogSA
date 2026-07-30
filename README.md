# analogSA

An offline reference app for shooting film in South Africa.

It answers the questions that come up constantly and have no good local answer: which lens
is worth buying, what a body actually does, where to get a roll developed, who will repair
a seized shutter, and what a given piece of glass tends to go for.

Everything ships inside the app. There is no account, no tracking, and no network needed
to use it — the only time it goes online is to check whether a newer version has been
released.

---

## ⚠️ Installing: Android will warn you, and that is expected

This app is not on the Play Store. It is a **sideloaded APK**, so Android and Play Protect
will both object. You will see some combination of:

- *"For your security, your phone is not allowed to install unknown apps from this source"*
- *"Unsafe app blocked"* or *"Play Protect doesn't recognise this app's developer"*
- A warning that the app was not scanned

**This is normal for any app installed outside the Play Store.** It does not mean anything
has been found wrong with the app — it means Google has not reviewed it, because it was
never submitted. The APK is unsigned by any recognised developer certificate, which is
exactly what that warning is describing.

To install:

1. Download the latest `app-debug.apk` from [Releases](https://github.com/EthanChas/analogSA/releases).
2. Open it. When Android says the source is not allowed, tap **Settings** and enable
   *Allow from this source* for whichever app you opened it with (Files, Chrome, etc).
3. If Play Protect blocks it, choose **Install anyway** / **More details → Install anyway**.

You are trusting this build the same way you would trust any APK from the internet. If
that is not a trade you want to make, build it yourself — see [Building](#building) below.

### Updating

The app checks GitHub once each time it starts. When a newer release exists it tells you,
and can download and install it for itself. Android will ask permission for the app to
install apps the first time; that is the `REQUEST_INSTALL_PACKAGES` permission and it is
used for nothing else.

You can also check manually under **Settings → Version → Check for updates**, which is
also where the currently installed version is shown.

---

## What is in it

**Equipment information**
- **220 lenses** for the Pentax K and M42 mounts — the SMC Pentax K, M and A series, the
  screwmount Takumars, and third-party K-mount glass from Vivitar, Sigma, Tamron, Kiron,
  Tokina and others. Ratings, review counts, pricing, and 118 photographs.
- **110 camera bodies**, from the 1952 Asahiflex to the 2023 K-3 III Monochrome, with
  mount, format, years and lens compatibility. 18 carry full specifications; 96
  photographs across 66 bodies.
- Side-by-side comparison for any two lenses or any two bodies.

**Film**
- **Labs** that develop and scan, with prices and turnaround where published.
- **Rolls** — film stock for sale, filterable by format (35mm, 120, 4×5, Instax).
- **Chemicals** — black and white chemistry you can buy locally, and the C-41 situation.
- **Darkrooms for rent** — no data yet.

**Repair and services** — shops and independent repairers, with phone numbers, addresses
and map pins.

**Social** — camera clubs with meeting times and venues, plus forums and communities.

**Other** — courses and schools, and gear websites worth watching, split between South
African and international.

---

## ⚠️ About the prices

**Prices in this app are estimates built from incomplete data. Do not treat them as an
absolute reference.** They may be old, outdated, or simply wrong.

Second-hand camera prices in particular move with condition — fungus, haze, oil on the
aperture blades and cosmetic wear swing the real number enormously — and the figures here
come from community submissions and shop listings captured at a point in time. Always
confirm with the seller.

---

## Where the data comes from

| Section | Source |
|---|---|
| Lens ratings, review counts, USD prices | PentaxForums lens review database |
| Lens local pricing, introduction dates, photographs | Field guide booklets (three volumes) |
| Camera bodies and specifications | camera-wiki.org |
| Camera photographs | Wikimedia Commons, each credited in the app with its photographer and licence |
| Labs, repairers, clubs, forums, schools, film and chemical stock | Gauteng photography directory and the ZA analogue resource list |
| Gear websites | Compiled and checked for a live response before inclusion |

Coverage is uneven and the app says so where it matters. Bodies without verified
specifications state that outright rather than showing invented numbers, and sections with
no data say they are empty rather than being padded.

---

## Building

Requires JDK 17 or newer and the Android SDK (compileSdk 35).

```bash
gradle -p . assembleDebug
```

The APK lands at `app/build/outputs/apk/debug/app-debug.apk`.

The app targets SDK 34 deliberately. Android 15 forces edge-to-edge layout on targetSdk
35, and these screens use the AppCompat action bar, which does not inset itself.

---

## Licence

No licence is currently specified, which means default copyright applies. The bundled data
belongs to its original sources, listed above; camera photographs from Wikimedia Commons
carry their own licences and are credited individually inside the app.
