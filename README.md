# Off-plan assignment ledger

Live: [https://evgheni34-hash.github.io/offplan-assignment-ledger](https://evgheni34-hash.github.io/offplan-assignment-ledger)

Static GitHub Pages calculator for a Dubai off-plan assignment (переуступка). Buyer and seller ledgers stay on one screen. Share cards stay WhatsApp-short.

## What is free

- **Deal math is always free.** Changing prices, rates, mortgage %, prepaid service charge, and reading the on-screen ledgers never requires payment.
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

- **Buyer:** short payee card (total + who gets what). Mortgage % shows as one line with implied AED. Prepaid service charge shows as one payee line when > 0.
- **Seller image:** four lines — net to seller, NOC / assignment, commission + VAT, ROI. A fifth line `SC продавцу` appears only when prepaid service charge > 0. Full seller estimate stays on screen.
- **Seller text:** short WhatsApp summary (object, totals, 2–3 payee lines, optional one-line SC refund, profit + ROI).

## Mortgage %

Buyer mortgage is a **percent of deal price** (typical 40 / 50 / 60), not an AED loan box. Implied loan = deal price × %. Bank fee and DLD mortgage registration use that AED amount. The implied AED is shown under the % field and on the buyer ledger (`ипотека 50% = … AED`).

## Service charge refund

Enter the prepaid service charge the seller already paid. The buyer refunds that amount to the seller. It is **not** a seller fee: it increases what the buyer pays the seller and seller net proceeds / profit. Combined market-cost % ignores it (transfer, not a transaction cost).

## How to test

1. Open the live URL in a fresh profile or after clearing `unlocked` / `exportCount`.
2. Change a price — tiles and ledgers update without a paywall.
3. **Mortgage %:** turn on «Покупка с привлечением ипотеки». Default 50% of the sample deal (1 195 000) must show **597 500 AED**. Change to 40% → **478 000 AED**; 60% → **717 000 AED**. Bank fee and DLD mortgage registration must move with that AED amount. Buyer tile / «Итого к оплате» include only the one-off mortgage fees, not the loan itself. Buyer text export: one mortgage line with % + implied AED + fees.
4. **Service charge refund:** enter e.g. `8000` in «Предоплаченный service charge». Buyer payee list gets «Возврат service charge продавцу — 8 000 AED». Seller profit adds «Плюс возврат service charge». Seller net / tile profit rise by 8 000. Buyer and seller text each gain one SC line. Seller image stays four lines at 0; at 8 000 it adds `SC продавцу`.
5. Reset to example — mortgage off, SC 0, cards back to the short default.
6. Download or share a card twice. The hint counts down.
7. A third export opens the paywall. Check the WhatsApp link: `https://wa.me/971585668337?text=…` and the prefilled unlock sentence.
8. Switch RU / EN / AR on the paywall. Arabic is RTL.
9. Enter `UNLOCK49`. Paywall closes; export works again. Reload — still unlocked.
