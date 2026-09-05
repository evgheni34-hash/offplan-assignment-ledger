# Off-plan assignment ledger

Live: [https://evgheni34-hash.github.io/offplan-assignment-ledger](https://evgheni34-hash.github.io/offplan-assignment-ledger)

Static GitHub Pages calculator for a Dubai off-plan assignment (переуступка). **Calc and share/export are free** — no paywall, no UNLOCK49.

WhatsApp CTA (`+971 58 566 8337`) stays for «разбор юнита».

## Mortgage as LTV %

Buyer mortgage is **LTV % of deal price**. Implied loan = deal price × %. Bank / DLD mortgage fees use that AED amount.

## Prorata when «в аренде» is ON

No raw refund-AED field for SC or rent. Inputs:

- Annual service charge (AED/year)
- Annual rent (AED/year)
- Remaining days, **or** transfer date + prepaid-through date (remaining days derived, inclusive)
- Security deposit (absolute AED → buyer)

Formula (365-day year, not 365.25):

`daily = annual / 365`  
`refund = daily × remaining days`

Directions:

- SC prorata: buyer → seller
- Rent prorata: seller → buyer
- Deposit: → buyer

Derived refunds show on screen. Toggle **off**: fields hide and zero, no WhatsApp lines.

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
3. «В аренде» on. SC year `36500`, rent year `73000`, remaining days `10` → SC **1 000** buyer→seller, rent **2 000** seller→buyer. Or handover `2026-01-01` + prepaid through `2026-01-10` → same 10 days. Deposit `10000` → buyer.
4. Toggle off — SC/rent/deposit gone from ledgers and text.
5. Seller card has no «Разбивка». Seller text has no NOC/agency «Кому и сколько».
