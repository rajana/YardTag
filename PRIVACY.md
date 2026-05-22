# YardTag Privacy Policy

**Effective:** 2026-05-17
**Last updated:** 2026-05-22

YardTag is a mobile app for running a garage, yard, moving, or community sale. It is designed to be **local-first**: your sale data lives on your phone, not on our servers. This policy explains exactly what data the app handles, what leaves your device, and why.

If anything here is unclear, email **support.yardtag@gmail.com**.

---

## 1. Who we are

YardTag is published by Rajana Devassykutty. References to "we," "us," or "the app" in this policy mean YardTag and Rajana Devassykutty.

---

## 2. The short version

- All your items, photos, sales, and checklists are stored **on your phone** in a local database and the app's private file storage.
- We do **not** have user accounts. We do not collect your email or phone number. The app lets you optionally enter your name and address in Settings so they can be printed on Pro price tags — these values are stored **only on your device** and are never transmitted to YardTag's servers or any third party.
- The only thing that leaves your phone for our service is what you send to get an AI price suggestion: a downsized photo and the short description you typed, along with an anonymous device ID for rate limiting.
- The app uses Apple/Google in-app purchase for the optional one-time Pro unlock. The purchase itself is handled by Apple/Google; we receive a purchase receipt, not your payment details.
- We use PostHog for anonymous product analytics and Sentry for crash reports. Neither receives photos, item descriptions, names, or other personal info.

---

## 3. What stays on your phone (and never leaves)

The following data is stored **locally only** and is never uploaded to our servers:

- Your sales (name, dates, archive status)
- Your items (name, description, category, condition, quantity, listed price, sold price, notes)
- Photos you take or pick (stored as JPEG files in the app's private storage)
- Your checklist
- App settings (currency, AI-on/off, onboarding state)
- Your **seller name and address** (optional, entered in Settings) — used only to render your Pro price tags before printing. These values are stored on your device and are never transmitted to YardTag's servers or any third party.
- Your Pro entitlement status

If you uninstall the app, this data is deleted with the app. Because it is not synced to a cloud account, **we cannot recover it for you** if your phone is lost or wiped.

---

## 4. What leaves your phone, and why

### 4.1 AI price suggestions (only when you tap "Suggest Price with AI")

When you ask the app for a price suggestion, the app sends the following to our pricing service:

- A **downsized JPEG** of the photo you took or picked (resized client-side to a max edge of 512 pixels, quality 70, EXIF stripped — so location/camera metadata embedded by your phone is removed before upload)
- The **short text description** you typed for the item
- An optional **ZIP code** and **category hint** if you provided one
- An **anonymous device ID** — a random identifier generated on first launch and stored on your phone. It is not linked to your name, email, Apple ID, Google account, or any other identifier we hold.

Our pricing service:

1. Hashes the photo and description and looks up a cached price (30-day TTL). If found, it returns the cached price without calling the AI model.
2. If not cached, forwards the request to Anthropic's API to generate a price (Claude Haiku 4.5 by default). Anthropic processes the request under their own terms; per Anthropic's published policy at the time of writing, API inputs and outputs are not used to train their models.
3. Stores the resulting price in the cache and returns it to your phone.
4. Increments a monthly counter on the anonymous device ID (`usage:<device_id>:<YYYY-MM>`) so we can enforce the monthly free-tier limit (currently 100 AI price suggestions per device per calendar month; this limit may change over time).

We do **not** associate price requests with your identity. We do not log photos or descriptions long-term beyond the cache described above.

If you turn AI suggestions off in Settings, no requests are sent.

### 4.2 Product analytics (PostHog)

If product analytics is enabled in your build, the app sends a small set of **event names with bounded properties** to PostHog (a third-party analytics provider). Examples: `add_item`, `mark_sold`, `tags_printed`, `paywall_shown`. The full list is the same as the engineering reference at [ANALYTICS.md](ANALYTICS.md).

What is sent:

- The event name
- A few bounded properties such as quantities, price magnitudes, the kind of error (e.g. `network`, `rate_limited`), or which Pro feature triggered a paywall
- The **anonymous device ID** described above

What is **not** sent:

- Photos
- Item names or descriptions
- Sale names
- Checklist contents
- Any name, email, address, or contact info

If the analytics key is not configured in a given build, no events are sent at all.

### 4.3 Purchases (Apple / Google)

The optional one-time YardTag Pro unlock ($4.99) is processed by Apple's App Store or Google Play in-app purchase, with RevenueCat acting as our receipt-validation provider.

- Apple/Google handle your payment. We never see your card number, billing address, or full Apple/Google account.
- RevenueCat receives the purchase receipt and your anonymous device ID so we can restore your Pro entitlement on reinstall or on a different device signed into the same Apple/Google account.
- You can review Apple's privacy practices at apple.com/legal/privacy, Google's at policies.google.com/privacy, and RevenueCat's at revenuecat.com/privacy.

### 4.4 Crash reports (Sentry)

When the app crashes or hits an unhandled error, it sends a diagnostic report to Sentry (sentry.io), a third-party error-monitoring service, so we can find and fix the bug.

What is sent:

- The **stack trace** and error message
- **Device and OS info** — phone model, OS version, app version, locale, free memory
- **Breadcrumbs** — a short, recent log of in-app actions leading up to the error (e.g. "opened AddItem screen," "price call returned"). Free-form fields like your item names and descriptions are not included.
- The **anonymous device ID** described above

What is **not** sent:

- Photos
- Item names, descriptions, or notes
- Sale names or checklist contents
- Screenshots
- Any name, email, address, or contact info

We use Sentry's default IP-address scrubbing where supported. Sentry retains crash data per their plan and their privacy policy at sentry.io/privacy/.

### 4.5 Printing and exporting

When you print price tags or export a sale summary (CSV/PDF), the file is generated on your phone and handed to the operating system's native print or share sheet. We do not see what you print or where you share it.

---

## 5. Third-party services we use

| Service | Role | What they receive |
|---|---|---|
| Cloudflare Workers + KV | Our pricing proxy and cache | Downsized photo, description, optional ZIP, anonymous device ID |
| Anthropic (Claude API) | AI price generation | Downsized photo and description (forwarded by our proxy on cache miss) |
| PostHog | Anonymous product analytics | Event names + bounded properties + anonymous device ID |
| Sentry | Crash and error reports | Stack trace, device/OS info, breadcrumbs, anonymous device ID |
| Apple App Store / Google Play | In-app purchases | Your payment, per their terms |
| RevenueCat | IAP receipt validation and restore | Purchase receipt, anonymous device ID |

Each of these providers has its own privacy policy and data-handling practices.

---

## 6. Permissions the app asks for

- **Camera** — to photograph items for AI pricing. Used only when you open the camera in the app.
- **Photo library** — to pick existing photos for AI pricing. Used only when you tap "Use library."

The app does not ask for contacts, location, microphone, calendar, or background access.

---

## 7. Children

YardTag is intended for adults running a sale. It is not directed at children under 13, and we do not knowingly collect data from children.

---

## 8. Your choices and rights

- **Turn off AI suggestions.** Settings → AI suggestions off. No requests will be sent to our pricing service.
- **Delete everything.** Uninstalling the app removes the local database, photos, and all settings from your device.
- **Reset your device ID.** Uninstalling and reinstalling the app generates a new anonymous device ID. PostHog and Sentry records for the old ID are no longer linked to your new install.
- **Restore Pro.** Tap "Restore Purchases" on the paywall screen to re-apply your Pro unlock on a new device signed into the same Apple/Google account.
- **Request deletion of cached AI data.** Because cache entries are keyed by an anonymous hash and not by your identity, we cannot identify your specific entries on request. They expire automatically after 30 days. If you want us to invalidate the entire pricing cache, email us.
- **Request deletion of analytics or crash data.** Email us with your anonymous device ID (Settings → About → Device ID, in a future build) and we will delete the corresponding PostHog person record and any Sentry events tied to that ID.

If you are in a jurisdiction with applicable data-protection laws (e.g. GDPR, UK GDPR, CCPA), you may have additional rights to access, correct, or delete the limited data we hold. Contact us and we will respond in good faith.

---

## 9. Data retention

- **On-device data:** kept until you delete an item, end a sale, or uninstall the app.
- **AI pricing cache (Cloudflare KV):** 30 days from last write.
- **Rate-limit counters (Cloudflare Durable Object storage):** reset each calendar month.
- **PostHog analytics:** retained per PostHog's default retention for our plan.
- **Sentry crash reports:** retained per Sentry's default retention for our plan (typically 30–90 days).
- **RevenueCat receipts:** retained for the life of the Pro entitlement so the unlock can be restored.

---

## 10. Security

- We never ship the Anthropic API key in the app. It lives only as a Cloudflare Worker secret.
- Network calls to our pricing service use HTTPS.
- Photos and descriptions in the cache are keyed by a SHA-256 hash, not by your identity.

No system is perfectly secure. If you believe you have found a security issue, please email us before disclosing it publicly.

---

## 11. International users

Our pricing service runs on Cloudflare's global edge network and routes AI requests to Anthropic, which processes them in the United States. By using AI price suggestions, you acknowledge that the downsized photo and description you send may be processed outside your country of residence.

---

## 12. Changes to this policy

If we make material changes, we will update the "Last updated" date at the top and, where appropriate, surface a notice in the app on next launch. Continued use of the app after an update means you accept the revised policy.

---

## 13. Contact

Questions, deletion requests, or anything else:

**support.yardtag@gmail.com**
