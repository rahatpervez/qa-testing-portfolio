# Sweet Shop: Web Application Testing & Bug Report

[Sweet Shop](https://sweetshop.netlify.app/) is a small demo e-commerce site. I tested it page by page with Chrome DevTools open the whole time, then wrote up every confirmed issue with where it happens, its severity, what I did, and screenshots.

## File

| File | Description |
|---|---|
| [SweetShop_Bug_Report.pdf](SweetShop_Bug_Report.pdf) | The full report (14 pages, with screenshots) |

## Results

I logged 22 potential issues while testing. Of those, **12 were confirmed bugs**. The rest were false alarms I corrected after a closer look, duplicates, or checks that passed. Those are covered at the end of the report too.

| Severity | Count |
|---|---|
| Critical | 2 |
| High | 3 |
| Medium | 2 |
| Low | 5 |

## Confirmed bugs

| ID | Issue | Severity |
|---|---|---|
| BUG-07 | "Add to Basket" never adds anything | Critical |
| BUG-20 | Login accepts any password | Critical |
| BUG-21 | Order placed with an empty basket | High |
| BUG-12 | Payment fields accept junk data | High |
| BUG-18 | No sign-up option exists | High |
| BUG-01 | "About" link broken on the Basket page | Medium |
| BUG-19 | Wham Bars product photo is broken | Medium |
| BUG-02 | Social icons go nowhere | Low |
| BUG-04 | Bubble Gums image missing alt text | Low |
| BUG-06 | 20% Off banner only on the About page | Low |
| BUG-09 | Promo code gives no feedback | Low |
| BUG-22 | jQuery loaded inconsistently across pages | Low |

## How I tested

- Explored every page first (Home, Sweets, Login, Basket, About), then went through each flow deliberately.
- Used the Console and Network tabs to find the cause, not just the symptom. For example, the basket never updates because `getCart()` calls `JSON.parse()` on the string "ERROR".
- Reproduced key bugs more than once with different data. The empty-basket order went through three separate times.
- Kept the false alarms and passing checks in the report, so the full scope of testing is visible.
