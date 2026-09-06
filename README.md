# Off-plan assignment ledger

Live: [https://evgheni34-hash.github.io/offplan-assignment-ledger](https://evgheni34-hash.github.io/offplan-assignment-ledger)

Static GitHub Pages calculator for a Dubai off-plan assignment (переуступка). **Calc and share/export are free** — no paywall, no UNLOCK49.

WhatsApp CTA (`+971 58 566 8337`) stays for «разбор юнита».

## Mortgage as LTV %

Buyer mortgage is **LTV % of deal price**. Implied loan = deal price × %. Bank / DLD mortgage fees use that AED amount.

## Prorata when «в аренде» is ON

No raw refund-AED field. No primary remaining-days field. Inputs:

**Shared**

- День сделки / передачи (used for both rent and SC)

**Rent**

- Начало контракта
- Окончание контракта
- Аренда в год (AED/year)

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

Required when rented ON (amber empty / green filled): lease start, lease end, deal date, annual rent, area, SC rate, SC prepaid until. Deposit optional.

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

1. Open the live URL. No paywall. Export many times — always free.
2. Mortgage on: 50% of 1 195 000 = **597 500 AED**; 40% → 478 000; 60% → 717 000.
3. «В аренде» on. Required fields start amber; they turn green when filled.
   - День сделки `2026-01-01`
   - Начало контракта `2025-06-01`, окончание `2026-01-10`
   - Аренда в год `73000` → **10** дн. → rent **2 000** seller→buyer
   - Площадь `1000`, ставка SC `36.5` → SC в год **36 500**
   - SC оплачен до `2026-01-10` → **10** дн. → SC **1 000** buyer→seller
   - Депозит `10000` → buyer
4. If день сделки `2026-01-11` (after lease end / SC prepaid) → both refunds **0**.
5. Toggle off — SC/rent/deposit gone from ledgers and text.
6. Seller card has no «Разбивка». Seller text has no NOC/agency «Кому и сколько».
