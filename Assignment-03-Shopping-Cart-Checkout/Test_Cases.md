# Assignment 3 — Test Cases and Latest Execution Results

> Results below are tester-reported. Test cases summarize the approved execution flow; no independent run artifacts are included.

## TC-008 — Add Product to Cart
- **Requirement:** REQ-008
- **Preconditions:** Products; logged in; empty cart
- **Test data:** Backpack x1
- **Steps:** Add Backpack; check badge; open cart; verify item and QTY; continue shopping; verify Remove button
- **Expected:** Badge 1; Your Cart lists Backpack QTY 1; Products restored; button Remove
- **Actual (reported):** All checks observed
- **Latest status:** **PASS**

## TC-009 — Remove Product from Products
- **Requirement:** REQ-009
- **Preconditions:** Products; logged in; cart contains only Backpack
- **Test data:** Backpack x1
- **Steps:** Check badge; click Remove on Products; check badge; open cart
- **Expected:** Badge 1 before removal; Add to cart button afterwards; badge disappears; cart empty
- **Actual (reported):** All checks observed
- **Latest status:** **PASS**

## TC-010 — Remove Product from Your Cart
- **Requirement:** REQ-009
- **Preconditions:** Your Cart; logged in; only Backpack present
- **Test data:** Backpack x1
- **Steps:** Click Remove for Backpack; inspect cart and badge
- **Expected:** Cart empty; no badge
- **Actual (reported):** Both observed
- **Latest status:** **PASS**

## TC-011 — Add Multiple Different Products
- **Requirement:** REQ-010
- **Preconditions:** Products; logged in; empty cart
- **Test data:** Backpack x1; Bike Light x1
- **Steps:** Add both; check badge; open cart; verify entries and quantities
- **Expected:** Badge 2; only specified products, each QTY 1
- **Actual (reported):** All checks observed
- **Latest status:** **PASS**

## TC-012 — Verify Cart Product Prices
- **Requirement:** REQ-011
- **Preconditions:** Cart with both specified products
- **Test data:** Backpack $29.99; Bike Light $9.99
- **Steps:** Inspect each product and displayed price against exercise-approved oracle
- **Expected:** Correct products and exercise prices
- **Actual (reported):** Displayed prices matched exercise oracle
- **Latest status:** **PASS**

## TC-013 — Verify Mandatory Checkout Fields
- **Requirement:** REQ-012
- **Preconditions:** Checkout: Your Information; reset fields between datasets
- **Test data:** DS-01–DS-07 in Test_Data.csv
- **Steps:** For each dataset enter specified values, click Continue, inspect error and page
- **Expected:** Required-field error for first missing field; stay on Your Information
- **Actual (reported):** Seven datasets matched expected errors; see Test_Data.csv
- **Latest status:** **PASS**

## TC-014 — Checkout with Valid Information
- **Requirement:** REQ-012
- **Preconditions:** Your Information; cart contains both products
- **Test data:** John / Doe / 50003
- **Steps:** Enter all three values; click Continue
- **Expected:** Checkout: Overview displayed
- **Actual (reported):** Checkout: Overview displayed
- **Latest status:** **PASS**

## TC-015 — Verify Order Overview
- **Requirement:** REQ-013
- **Preconditions:** Checkout: Overview; cart contains both products
- **Test data:** Backpack $29.99 x1; Bike Light $9.99 x1; tax 8%
- **Steps:** Verify products, quantities, no extras, item total, tax and total
- **Expected:** Item $39.98; tax $3.20; total $43.18
- **Actual (reported):** All observed against exercise oracle
- **Latest status:** **PASS**

## TC-016 — Complete Purchase
- **Requirement:** REQ-014
- **Preconditions:** Checkout: Overview; valid information and products
- **Test data:** Backpack x1; Bike Light x1
- **Steps:** Click Finish; inspect completion page and message
- **Expected:** Checkout: Complete! and Thank you for your order!
- **Actual (reported):** Both observed (UI only)
- **Latest status:** **PASS**

## TC-017 — Cancel Checkout from Your Information
- **Requirement:** REQ-015
- **Preconditions:** Your Information; cart contains both products
- **Test data:** Backpack x1; Bike Light x1
- **Steps:** Click Cancel; inspect destination and no completion; inspect cart
- **Expected:** Your Cart; no confirmation; both products preserved QTY 1
- **Actual (reported):** Re-execution matched revised exercise criteria; original run differed from original assumption
- **Latest status:** **PASS**

## TC-018 — Cancel Checkout from Overview
- **Requirement:** REQ-015
- **Preconditions:** Overview; John/Doe/50003 entered; cart contains both products
- **Test data:** Backpack x1; Bike Light x1
- **Steps:** Cancel; inspect destination; open cart; inspect items; click Checkout; inspect fields
- **Expected:** Products; no confirmation; Your Cart; both items QTY 1; Your Information with all three fields empty
- **Actual (reported):** All five steps matched expected results
- **Latest status:** **PASS**
