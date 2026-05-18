# YardTag Support

Need help with YardTag? You're in the right place.

**Email:**support.yardtag@gmail.com — we aim to reply within 2 business days.

When you write in, please include:
- Your phone model and OS version (e.g. iPhone 14, iOS 18.2 / Pixel 8, Android 15)
- The app version (Settings → About in the app)
- A short description of what you were doing and what happened

---

## Quick start

1. **Open the app** and swipe through the onboarding slides. Set your sale start and end dates on Home — this unlocks the rest of the actions.
2. Tap **+ Snap to Price** to add your first item. Take a photo, type a short description (e.g. "blue ceramic lamp, 80s, works"), then tap **Suggest Price with AI**. The AI returns three tiers — pick one or enter your own price. You can also skip AI entirely by typing a price in the manual field below.
3. Repeat until your sale is loaded.
4. (**Pro**) Go to **Print price tags**, select your items, and print to AirPrint or save the PDF. Tag printing is a Pro feature — tap the button on Home to upgrade.
5. On sale day, tap an item and **Mark Sold** as buyers pay.
6. End of day, open **Sale Summary** to see totals and (Pro) export a CSV or PDF report.

---

## Frequently asked questions

### Pricing & AI

**Q: How does the AI price work?**
You take a photo and type a short description. The app sends a downsized photo plus your description to our pricing service, which uses Claude (an AI model from Anthropic) to suggest three price tiers: quick-sale, fair, and top-end. It also returns a one-sentence reason.

**Q: Why is the suggested price off?**
The AI is a starting point, not the final word. It is conservative because garage-sale buyers expect deep discounts. Adjust freely — type a custom price on the same screen.

**Q: I got a "You've used your free price calls for this month" message.**
The free tier allows 100 AI price calls per device per month. The counter resets on the 1st of each month. Pro does **not** raise this limit (Pro unlocks tag printing, Bulk Snap, more than 1 sale per year, export, and a payment QR on tags — see Pro section below). When you hit the cap, you can keep adding items by typing prices manually in the AddItem screen.

**Q: The price call failed — what does each error mean?**
- **Network** — Your phone could not reach our service. Check wifi/cellular and try again.
- **Rate limited** — You've hit the monthly free-tier cap. Wait until the 1st, or price the rest manually.
- **AI failed / Parse error** — The model returned an unexpected response. Retry once. If it keeps happening, email us with the item description.
- **Config** — The app build is missing the pricing service URL. This usually means a broken build — please email us.

**Q: Can I turn AI off entirely?**
Yes. Settings → AI suggestions off. Add items by typing the price yourself.

### Items & sales

**Q: How do I edit an item?**
On the Items tab, tap the row. The Add Item screen reopens with the existing values; edit and save.

**Q: I marked an item sold by mistake.**
Open the item from Items. You can revert (return) the sale; the inventory count goes back up.

**Q: What does "Remaining" mean for an item with quantity > 1?**
Quantity is total units; sold quantity is how many you've already sold. Remaining = quantity − sold. The item disappears from the active list when remaining hits zero.

**Q: How do I start a new sale?**
Open the Sales screen (from Home). Tap the **+** to create a new sale. Each item belongs to exactly one sale.

**Q: Can I run more than one sale per year?**
Only with Pro. Free allows 1 sale per calendar year; Pro lets you create as many sales as you need each year (e.g. a spring sale and a fall sale, or helping a friend with theirs).

### Tags & printing

**Q: Why is the "Print price tags" button locked?**
Tag printing is a Pro-only feature. Tap the button and you'll be taken to the upgrade screen. After upgrading, the full Tags flow is available.

**Q: What paper does the Tags PDF print on?**
The tag layout targets **Avery 5160** US Letter labels (30 per sheet, 1" × 2-5/8"). Load a sheet in any inkjet/laser printer that supports US Letter and AirPrint.

**Q: Where does the QR code go on the printed sheet?**
If you've set up a payment service (Venmo, Cash App, PayPal, or a custom URL) in Settings, one dedicated "Scan to pay" tag is printed at the start of the sheet — the rest are item price tags, so the QR doesn't repeat on every label.

**Q: Can I print just some items?**
Yes. On the Tags screen, deselect any items you don't want included before tapping Print.

### Pro unlock

**Q: What does Pro include?**
- **Print Avery 5160 price tags** (the entire Tags flow is Pro-only)
- **Bulk Snap** — rapid photo-after-photo pricing for loading many items quickly
- **CSV and PDF export** of your sale summary
- **More than 1 sale per year** (free is capped at 1 sale per calendar year)
- **Payment QR on tags** (a scannable Venmo / Cash App / PayPal / URL QR code printed once per sheet)

**Q: What does Pro cost?**
$4.99, one-time, lifetime. No subscription, no renewal. The unlock is tied to your Apple ID / Google account and restores on a new device or after reinstall.

**Q: Does Pro raise the AI price-call limit?**
No. The 100 calls/month limit is the same for both tiers.

**Q: I bought Pro but a new phone / fresh install doesn't show it.**
Open the paywall screen (try to tap a Pro-only feature) and tap **Restore Purchases**. Make sure you're signed into the same Apple ID / Google account that bought it.

**Q: I want a refund.**
Refunds are handled by Apple or Google, not by us. Use Apple's "Report a Problem" page (reportaproblem.apple.com) or Google Play's purchase history. If they decline and you believe the situation warrants an exception, email us with the order ID and we'll see what we can do.

### Data & privacy

**Q: Where does my data live?**
On your phone, in the app's local database and private file storage. We do not have user accounts or cloud sync.

**Q: If I lose my phone or uninstall the app, can you recover my sale?**
No. Because nothing syncs to the cloud, the data is gone with the device. We recommend exporting (Pro) at the end of each sale day if the data matters to you.

**Q: What gets sent to your servers?**
Only what's needed for AI pricing: a downsized photo, your typed description, and an anonymous device ID for rate limiting. Full details in the [Privacy Policy](PRIVACY.md).

**Q: How do I request my data be deleted?**
Uninstall the app to wipe everything on-device. To clear the small amount of server-side analytics tied to your anonymous device ID, email us.

### Performance & bugs

**Q: The camera is slow or won't open.**
Force-quit the app and reopen. If the camera permission was denied previously, re-enable it in your phone's Settings → YardTag → Camera.

**Q: The app crashed.**
Sorry. The app sends an anonymous crash report to Sentry automatically (stack trace + device info + recent in-app actions — no photos, item content, or personal info). For us to act on it quickly, please also email us with: phone model, OS version, app version, and what you were doing in the seconds before the crash. Screenshots help.

**Q: Can I turn off crash reporting?**
The app does not currently offer a toggle. Crash data is anonymous (tied only to your random device ID) and never includes photos or item content — see the [Privacy Policy](PRIVACY.md) §4.4. If you'd prefer no crash reports be sent, email us and we'll exclude your device ID.

**Q: Photo orientation is wrong on a tag.**
Re-take the photo holding the phone in portrait orientation. If it keeps happening, please email an example.

---

## Known limitations

- **No cloud sync.** Each install is independent. We may add optional sync in a future version.
- **No multi-device sharing of one sale.** You can't have two phones running the same sale in real-time today.
- **AI price quality varies by item.** Recognizable brands, common items in clear photos do best. Niche or damaged items often need a manual override.
- **AI requires internet.** The rest of the app works offline.
- **Tags target US Letter / Avery 5160 only** in the current release.

---

## Bug reports & feature requests

Email **support.yardtag@gmail.com**.

Most useful info to include:
- What you were trying to do
- What you expected to happen
- What actually happened
- Any screenshots
- Your phone model, OS version, and app version (Settings → About)

For feature requests, a sentence on **why** is more useful than a sentence on **what** — the underlying need usually shapes the design more than the proposed solution.

---

## App version & changelog

The current app version is shown in Settings → About. Major release notes are posted on the App Store and Play Store listings.
