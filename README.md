# Off-plan assignment ledger

Live: [https://evgheni34-hash.github.io/offplan-assignment-ledger](https://evgheni34-hash.github.io/offplan-assignment-ledger)

Static GitHub Pages calculator for a Dubai off-plan assignment (переуступка). Calculator on screen stays free. WhatsApp CTA (`+971 58 566 8337`, «разбор юнита») stays free and is never gated.

**Export paywall:** first 2 successful share/export actions per browser are free (one `localStorage` counter for buyer + seller). Cancelled share does not count. The 3rd and later export/share click, if this browser is not unlocked, opens [Ziina 19 AED](https://pay.ziina.com/EvgheniC/3PHYGSxCy) in a new tab and shows **«Оплатил 19 — открыть экспорт навсегда»**. That control sets `localStorage` unlocked forever in this browser and then continues/enables export. Ziina has no return redirect; the page cannot verify payment and does not pretend a webhook exists. `?paid=1` is the same forever unlock (flag set, query stripped) if a return URL is added later. After the two free exports, hint: «Дальше — 19 AED за безлимитный экспорт в этом браузере».

## Mortgage as LTV %

Buyer mortgage is **LTV % of deal price**. Implied loan = deal price × %. Bank / DLD mortgage fees use that AED amount.

## Prorata when «в аренде» is ON

No raw refund-AED field. No primary remaining-days field. Inputs:

**Shared**

- День сделки / передачи (used for both rent and SC)

**Rent**

- Toggle **«аренда предоплачена до конца контракта»** (default ON when rented)
- Начало контракта
- Окончание контракта
- Аренда в год (AED/year) — used only if prepaid ON

If the toggle is OFF (monthly / not prepaid), rent refund is **0**. Do not invent a rent line.

**Service charge**

- Площадь, кв. фут
- Ставка SC (AED / sq ft / year)
- Derived **SC в год** = area × rate (read-only)
- SC оплачен до

**Deposit**

- Security deposit (absolute AED → buyer, optional)

Remaining days (inclusive):

- Rent: deal date through lease end (0 if deal > lease end)
- SC: deal date through SC prepaid-until (0 if deal past prepaid-until)

Formula (365-day year, not 365.25):

`daily = annual / 365`  
`refund = daily × remaining days`

Directions:

- SC prorata: buyer → seller
- Rent prorata: seller → buyer
- Deposit: → buyer

Required when rented ON (amber empty / green filled): lease start, lease end, deal date, area, SC rate, SC prepaid until. Annual rent required only if prepaid toggle is ON. Deposit optional.

Derived refunds and day counts show on screen. Toggle **off**: fields hide and clear, no WhatsApp lines.

WhatsApp / text — separate lines only if amount > 0:

- `SC buyer→seller X`
- `rent seller→buyer Y`
- `deposit → buyer Z`

## Share cards

- **Buyer:** payee split («Кому и сколько») kept.
- **Seller image:** four lines — net, NOC / assignment, commission + VAT, ROI.
- **Seller text:** title, итого обязательств, directed lines if > 0, profit + ROI. No «Кому и сколько» NOC/agency regroup. No «Разбивка платежей продавца».

## How to test

1. Open the live URL. Calculator and WhatsApp CTA stay free. Export twice (buyer or seller, share or download — one counter). Third export/share click opens Ziina and shows «Оплатил 19 — открыть экспорт навсегда». Tap that control → unlimited export in this browser, no further gate. `?paid=1` also unlocks forever and strips the query. Clearing site data resets the counter and the unlock flag.
2. Mortgage on: 50% of 1 195 000 = **597 500 AED**; 40% → 478 000; 60% → 717 000.
3. «В аренде» on. Required fields start amber; they turn green when filled.
   - День сделки `2026-01-01`
   - Начало контракта `2025-06-01`, окончание `2026-01-10`
   - Предоплата аренды ON, аренда в год `73000` → **10** дн. → rent **2 000** seller→buyer
   - Toggle предоплаты OFF → rent **0**, no rent export line
   - Площадь `1000`, ставка SC `36.5` → SC в год **36 500**
   - SC оплачен до `2026-01-10` → **10** дн. → SC **1 000** buyer→seller
   - Депозит `10000` → buyer
4. If день сделки `2026-01-11` (after lease end / SC prepaid) → both refunds **0**.
5. Toggle off — SC/rent/deposit gone from ledgers and text.
6. Seller card has no «Разбивка». Seller text has no NOC/agency «Кому и сколько».
