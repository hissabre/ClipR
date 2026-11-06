# CLIPR

Book a verified barber who comes to your home.

CLIPR is a two-sided marketplace: customers find, book, track and pay a mobile barber; barbers run their whole business from their phone; an admin side handles verification, disputes, fees and promotions.

This version is a **working demo**. Everything runs in the browser, with no server.

## What's in this folder

| File | What it is |
|---|---|
| `index.html` | The entire app (design, logic and demo data in one file) |
| `icon.svg` | The CLIPR app icon (browser tab and phone home screen) |
| `README.md` | This guide |

## Put it online with GitHub Pages

1. Sign in to [github.com](https://github.com) and click **New repository**.
2. Name it, for example `clipr`. Set it to **Public** and click **Create repository**.
3. On the next page click **uploading an existing file**, drag in `index.html`, `icon.svg` and `README.md`, then click **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set **Source** to *Deploy from a branch*, choose the **main** branch and the **/ (root)** folder, then click **Save**.
5. After a minute or two, your app is live at `https://YOUR-USERNAME.github.io/clipr/`.

To update it later, upload the new `index.html` over the old one in the repository. The site refreshes on its own.

**Tip:** on a phone, open the link and choose *Add to Home Screen*. CLIPR then opens full screen with its own icon.

## Trying the demo

- **Login code:** any phone number or email works. The verification code is **2580**.
- **Switch sides:** the dark bar at the top switches between Customer, Barber and Admin, and between English and French.
- **Live tracking:** in Bookings, open the upcoming appointment and tap **Mark on the way** in the demo controls box. The trip takes about 45 seconds and sends the "heading to you", "almost here" and "arrived" alerts.
- **Start over:** Account → *Reset demo data*.

Demo data is saved only in the browser you are using. Other people who open the link get their own fresh copy.

## How CLIPR makes money

| Stream | How it works | Default |
|---|---|---|
| Booking commission | Taken from the barber's earnings on each completed booking. Depends on the barber's plan. | 15% Starter · 10% Pro · 6% Elite |
| Customer service fee | Added to the customer's total at checkout. | 5% |
| Barber memberships | Monthly plans that lower commission and add perks. | Starter free · Pro ≈ 1 haircut/month · Elite ≈ 2 haircuts/month |
| Sponsored boosts | Barbers pay to take the first slot in search, clearly marked *Sponsored*. Shown only when they have open slots. | ≈ 0.15 haircut per day |
| Instant payout fee | Barbers can cash out now instead of waiting 2 days. Free on Elite. | 1.5% |

Membership and boost prices are set in "haircuts" so they follow local spending power: Pro costs €35/month in Paris and 5,000 F CFA in Bamako. All of these values can be changed in **Admin → Settings**.

## What is simulated

- **Accounts and login:** no real account is created and no code is sent.
- **Payments:** card, Apple Pay, bank transfer and mobile money (Orange Money, Wave, Moov, MTN) are shown, but no money moves.
- **Map and tracking:** the map is drawn by the app. There is no real GPS.
- **Other barbers:** barbers you don't control accept requests automatically after a few seconds.

## Going to production

A real launch needs:

1. **A backend:** real accounts, a shared database and live messaging. Supabase is a good fit.
2. **Payments:** Stripe Connect for cards and barber payouts, plus a mobile-money aggregator for West Africa, such as CinetPay, PayDunya or Flutterwave.
3. **Maps:** Mapbox or Google Maps for real streets, addresses and live GPS tracking.
4. **Push notifications:** a native app wrapper such as Capacitor, or web push.
5. **Identity checks:** a provider such as Onfido or Smile ID to verify barbers.
