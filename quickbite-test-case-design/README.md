# QuickBite: Test Case Design from a PRD

QuickBite is a food ordering and delivery app for iOS and Android. Working from its product requirements document, I reviewed the requirements, flagged the gaps, and wrote test cases for the customer-facing order flow: cart, coupons, checkout, payment, order tracking, cancellation and refunds, and ratings.

## Files

| File | Description |
|---|---|
| [QuickBite_Test_Cases.csv](QuickBite_Test_Cases.csv) | All 74 test cases. Opens as a table right here on GitHub. |
| [QuickBite_Test_Cases.xlsx](QuickBite_Test_Cases.xlsx) | The same test cases as an Excel workbook |
| [QuickBite_PRD_Review_and_Testing_Approach.pdf](QuickBite_PRD_Review_and_Testing_Approach.pdf) | Short deck: product overview, the ambiguities I found, and where testing fits across the SDLC |

## Coverage

| Module | Test cases |
|---|---|
| Cart Management | 15 |
| Coupons & Discounts | 15 |
| Checkout & Order Value | 10 |
| Payment | 9 |
| Cancellation & Refund | 6 |
| Ratings & Reviews | 6 |
| Non-Functional | 5 |
| Order Tracking | 4 |
| Business Rules | 4 |
| **Total** | **74** |

- **By type:** Functional 27, Boundary 13, Negative 13, Edge 10, Boundary/Negative 5, Negative/Edge 1, Non-functional 5 (performance, security, compatibility)
- **By priority:** High 46, Medium 24, Low 4

## Test case format

Each test case has an ID, module, scenario, type, priority, preconditions, test steps, test data, expected result, and a requirement reference (FR, NFR or BR). 71 of the 74 cases point to a specific requirement. The other 3 (empty cart, invalid coupon code, declined card) cover behaviour the PRD implies but never states.

## PRD ambiguities I flagged

1. The minimum order value for checkout (100) conflicts with the free-delivery threshold (orders above 99).
2. "Above X" wording leaves it unclear whether the boundary value itself qualifies.
3. No refund rule is defined for a cancelled Cash on Delivery order.
4. The guest checkout flow is left unclear.

Test cases that touch a gap or an unclear rule are marked in the reference column (for example, `FR-12 (ambiguous)` or `FR-7 (gap)`).
