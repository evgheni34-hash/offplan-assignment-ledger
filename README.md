# Off-plan assignment ledger

Live: [https://evgheni34-hash.github.io/offplan-assignment-ledger](https://evgheni34-hash.github.io/offplan-assignment-ledger)

Static GitHub Pages calculator for a Dubai off-plan assignment (переуступка). Buyer and seller ledgers stay on one screen. Share cards stay WhatsApp-short. **All share/export is free** — no paywall, no unlock code.

WhatsApp CTA (`+971 58 566 8337`) stays for «разбор юнита».

## Mortgage as LTV %

Buyer mortgage is **LTV % of deal price** (typical 40 / 50 / 60). Implied loan = deal price × %. Bank fee and DLD mortgage registration use that AED amount. Implied AED is shown under the % field and on the buyer ledger.

## В аренде

Toggle **Объект в аренде** (off by default). When off, the three fields are hidden and treated as 0 — no WhatsApp lines.

When on, three AED fields (default 0):

| Field | Cashflow | Buyer total | Seller net |
| --- | --- | --- | --- |
| Unused prepaid SC | buyer → seller | + SC | + SC |
| Unused prepaid rent | seller → buyer | − rent | − rent |
| Security deposit | → buyer | − deposit | − deposit |

WhatsApp / text export uses **separate directed lines only if > 0**:

- `SC buyer→seller X`
- `rent seller→buyer Y`
- `deposit → buyer Z`

## Share cards

- **Buyer:** short payee card (total + «Кому и сколько»). Tenancy lines only when on and amount > 0.
- **Seller image:** four lines — net to seller, NOC / assignment, commission + VAT, ROI.
- **Seller text:** title, итого обязательств, directed tenancy lines if > 0, profit + ROI. No «Кому и сколько» / NOC+agency regroup. No «Разбивка платежей продавца» on screen.

## How to test

1. Open the live URL.
2. Change a price — tiles and ledgers update.
3. **LTV %:** turn on mortgage. Default 50% of 1 195 000 = **597 500 AED**. 40% → **478 000**; 60% → **717 000**.
4. **В аренде:** toggle on. Enter SC `8000`, rent `5000`, deposit `10000`. Buyer total and seller net move `+8000 −5000 −10000`. Text export shows three directed lines. Toggle off — fields hide, values zero, no tenancy lines.
5. Confirm there is no «Разбивка платежей продавца» and no 49 AED paywall / unlock field.
6. Share or download many times — every export stays free.
