# Off-plan assignment ledger

Live: [https://evgheni34-hash.github.io/offplan-assignment-ledger](https://evgheni34-hash.github.io/offplan-assignment-ledger)

Static GitHub Pages calculator for a Dubai off-plan assignment (переуступка). Buyer and seller ledgers stay on one screen. Share cards stay WhatsApp-short.

## What is free

- **Deal math is always free.** Changing prices, rates, mortgage, and reading the on-screen ledgers never requires payment.
- **The first 2 successful share/exports per browser are free.** Buyer or seller, text or image, share or download — they share one counter in `localStorage` (`exportCount`).
- Cancelled share sheets do not count. A failed export does not count.

## One-time unlock — 49 AED

After the 2 free cards, further share/export opens a paywall (AR / RU / EN):

1. **Primary:** WhatsApp to `+971 58 566 8337` with a prefilled ask, e.g. `Хочу unlock калькулятора переуступки — 49 AED`.
2. **Secondary:** enter the unlock code. On success the browser stores `localStorage.unlocked = "true"` forever. Reload keeps access. The paywall never shows again.

No Stripe, no subscription, no ads, no CRM.

### Unlock code (operator-only)

The public page never shows the code — not in helper text, not in the WhatsApp prefill, not as a readable string in page source. Brokers send it manually after AED 49.

- Code: `UNLOCK49` (case-insensitive, spaces ignored)
- On success the app sets `localStorage.unlocked = "true"`

To reset a browser for testing: DevTools → Application → Local Storage → clear `unlocked` and `exportCount`.

## Share cards

- **Buyer:** short payee card (total + who gets what).
- **Seller image:** four lines — net to seller, NOC / assignment, commission + VAT, ROI. Full seller estimate stays on screen.
- **Seller text:** short WhatsApp summary (object, totals, 2–3 payee lines, profit + ROI).

## How to test

1. Open the live URL in a fresh profile or after clearing `unlocked` / `exportCount`.
2. Change a price — tiles and ledgers update without a paywall.
3. Download or share a card twice. The hint counts down.
4. A third export opens the paywall. Check the WhatsApp link: `https://wa.me/971585668337?text=…` and the prefilled unlock sentence.
5. Switch RU / EN / AR on the paywall. Arabic is RTL.
6. Enter `UNLOCK49`. Paywall closes; export works again. Reload — still unlocked.
