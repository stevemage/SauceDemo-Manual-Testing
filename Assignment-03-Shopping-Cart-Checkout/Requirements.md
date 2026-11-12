# Assignment 3 — Exercise Requirements

> These are training requirements, not official SauceDemo specifications.

| ID | Name | Requirement |
|---|---|---|
| REQ-008 | Add Product to Cart | User shall be able to add an available product to the shopping cart. |
| REQ-009 | Remove Product from Cart | User shall be able to remove a previously added product. |
| REQ-010 | Multiple Products | Cart shall support adding multiple different products. |
| REQ-011 | Cart Content | Cart shall display correct products and corresponding prices. |
| REQ-012 | Checkout Information | User shall provide First Name, Last Name and ZIP/Postal Code before order overview. |
| REQ-013 | Order Overview | Before completing purchase, user shall be able to review products and total price. |
| REQ-014 | Complete Purchase | User shall be able to complete a valid purchase and receive confirmation. |
| REQ-015 | Cancel Checkout | User shall be able to cancel checkout before completing purchase. |

## Clarified exercise acceptance criteria

- **REQ-011 / REQ-013:** Approved exercise price oracle: Backpack $29.99; Bike Light $9.99; item total $39.98; exercise tax 8% rounded to $3.20; total $43.18. These are *not* verified official prices/tax rules.
- **REQ-012:** First Name, Last Name and ZIP/Postal Code must be nonempty. Allowed characters and ZIP format are not defined; tests must not invent validation rules.
- **REQ-015:** Cancel from **Checkout: Your Information** returns to **Your Cart**. Cancel from **Checkout: Overview** returns to **Products**. Cart content is preserved, no purchase-completion confirmation is shown, and on restarting checkout the three input fields are empty.

The REQ-015 navigation expectations were clarified during the exercise after the initial TC-017 run.
