# Assignment 3 — Detailed Test Cases

**Application:** SauceDemo
**Scope:** Shopping Cart & Checkout (REQ-008–REQ-015)
**Test cases:** TC-008–TC-018
**Documentation note:** This document reconstructs the reviewed scenarios and reported observations from the training sessions. Where the original step-by-step wording is unavailable, steps are normalized for readability and must not be represented as verbatim historical records. All requirements and the approved price list are exercise assumptions, not official SauceDemo specifications.

## Common setup

Unless a case states otherwise, sign in with the training account `standard_user` / `secret_sauce`. Start with an empty cart for add-product cases. Verify the stated preconditions before each case; do not assume state carries over from previous executions.

## TC-008 — Add Product to Cart

- **Requirement:** REQ-008
- **Preconditions:** Logged in; Products page displayed; shopping cart empty.
- **Test data:** Sauce Labs Backpack, QTY 1.

| Step | Action | Expected result |
|---|---|---|
| 1 | Add Sauce Labs Backpack from Products. | Cart badge shows `1`; the item's button changes to **Remove**. |
| 2 | Open the shopping cart. | **Your Cart** is displayed. |
| 3 | Inspect cart contents. | Sauce Labs Backpack is listed with QTY `1`; no unintended items. |
| 4 | Select **Continue Shopping**. | Products page is displayed; Backpack button remains **Remove**. |

**Recorded execution:** PASS.

## TC-009 — Remove Product from Products Page

- **Requirement:** REQ-009
- **Preconditions:** Logged in; Products page displayed; cart contains exactly one Backpack.
- **Test data:** Sauce Labs Backpack, QTY 1.

| Step | Action | Expected result |
|---|---|---|
| 1 | Confirm the cart badge before removal. | Badge shows `1`. |
| 2 | Click **Remove** for Backpack on Products. | Button changes to **Add to cart**; cart badge disappears. |
| 3 | Open **Your Cart**. | Cart is empty. |

**Recorded execution:** PASS.

## TC-010 — Remove Product from Your Cart

- **Requirement:** REQ-009
- **Preconditions:** Logged in; Your Cart displayed; cart contains exactly one Backpack.
- **Test data:** Sauce Labs Backpack, QTY 1.

| Step | Action | Expected result |
|---|---|---|
| 1 | Click **Remove** for Backpack in Your Cart. | Backpack is removed; cart is empty; badge is not displayed. |

**Recorded execution:** PASS.

## TC-011 — Add Multiple Different Products

- **Requirement:** REQ-010
- **Preconditions:** Logged in; Products displayed; empty cart.
- **Test data:** Sauce Labs Backpack QTY 1; Sauce Labs Bike Light QTY 1.

| Step | Action | Expected result |
|---|---|---|
| 1 | Add Backpack. | Product is added. |
| 2 | Add Bike Light. | Product is added; badge shows `2`. |
| 3 | Open Your Cart. | Your Cart is displayed. |
| 4 | Inspect all cart rows. | Exactly Backpack and Bike Light appear, each QTY `1`; no other products. |

**Recorded execution:** PASS.

## TC-012 — Verify Cart Product Prices

- **Requirement:** REQ-011
- **Preconditions:** Logged in; cart contains exactly Backpack and Bike Light.
- **Test data / exercise price oracle:** Backpack `$29.99`; Bike Light `$9.99`.

| Step | Action | Expected result |
|---|---|---|
| 1 | Open Your Cart. | Both specified products are displayed. |
| 2 | Compare Backpack's displayed price against the exercise-approved price list. | `$29.99`. |
| 3 | Compare Bike Light's displayed price against the exercise-approved price list. | `$9.99`. |

**Recorded execution:** PASS. **Important:** These prices are a fictional training oracle; discrepancies are not automatically real-world product defects.

## TC-013 — Verify Mandatory Checkout Fields

- **Requirement:** REQ-012
- **Preconditions:** Logged in; Checkout: Your Information displayed; reset/clear all three fields between datasets.
- **Test data:** See table below.

| Dataset | First Name | Last Name | ZIP/Postal Code | Expected validation message |
|---|---|---|---|---|
| DS-01 | *(empty)* | Doe | 50003 | Error: First Name is required |
| DS-02 | John | *(empty)* | 50003 | Error: Last Name is required |
| DS-03 | *(empty)* | *(empty)* | 50003 | Error: First Name is required |
| DS-04 | *(empty)* | *(empty)* | *(empty)* | Error: First Name is required |
| DS-05 | John | Doe | *(empty)* | Error: Postal Code is required |
| DS-06 | John | *(empty)* | *(empty)* | Error: Last Name is required |
| DS-07 | *(empty)* | Doe | *(empty)* | Error: First Name is required |

| Step | Action | Expected result |
|---|---|---|
| 1 | Clear First Name, Last Name, and ZIP/Postal Code. | All fields are empty. |
| 2 | Enter values for the selected dataset. | Values match that dataset. |
| 3 | Click **Continue**. | The corresponding validation message is shown; user remains on Checkout: Your Information. |
| 4 | Repeat steps 1–3 for every remaining dataset. | All seven datasets meet their expected results. |

**Recorded execution:** PASS for DS-01 through DS-07. Character sets and ZIP formats were not specified; no unsupported format-validation assertions are included.

## TC-014 — Checkout with Valid Information

- **Requirement:** REQ-012
- **Preconditions:** Logged in; Checkout: Your Information displayed; cart contains Backpack QTY 1 and Bike Light QTY 1.
- **Test data:** First Name `John`; Last Name `Doe`; ZIP/Postal Code `50003`.

| Step | Action | Expected result |
|---|---|---|
| 1 | Enter all three valid checkout fields. | Fields contain John, Doe, and 50003. |
| 2 | Click **Continue**. | Checkout: Overview is displayed. |

**Recorded execution:** PASS.

## TC-015 — Verify Order Overview

- **Requirement:** REQ-013
- **Preconditions:** Logged in; Checkout: Overview displayed after valid checkout information.
- **Test data:** Backpack QTY 1 `$29.99`; Bike Light QTY 1 `$9.99`; exercise tax rate `8%`, rounded to two decimals.

| Step | Action | Expected result |
|---|---|---|
| 1 | Inspect products and quantities. | Exactly Backpack QTY 1 and Bike Light QTY 1; no additional items. |
| 2 | Verify item prices. | Backpack `$29.99`; Bike Light `$9.99`. |
| 3 | Verify Item Total. | `$39.98`. |
| 4 | Verify Tax. | `$3.20`. |
| 5 | Verify Total. | `$43.18`. |

**Recorded execution:** PASS. Amounts are exercise-defined expectations, not an official price/tax specification.

## TC-016 — Complete Purchase

- **Requirement:** REQ-014
- **Preconditions:** Logged in; valid Checkout: Overview displayed with the selected products.
- **Test data:** Backpack QTY 1; Bike Light QTY 1; valid checkout information.

| Step | Action | Expected result |
|---|---|---|
| 1 | Click **Finish**. | Checkout: Complete! is displayed. |
| 2 | Inspect the confirmation message. | `Thank you for your order!` is displayed. |

**Recorded execution:** PASS. UI confirmation only; backend persistence and order creation were not verified.

## TC-017 — Cancel Checkout from Your Information

- **Requirement:** REQ-015
- **Preconditions:** Logged in; Checkout: Your Information displayed; cart contains Backpack QTY 1 and Bike Light QTY 1.
- **Test data:** Backpack QTY 1; Bike Light QTY 1.
- **BA clarification:** Cancel from **Your Information** navigates to **Your Cart**, preserves cart contents, and does not complete an order.

| Step | Action | Expected result |
|---|---|---|
| 1 | Click **Cancel**. | Your Cart is displayed; no order-completion confirmation appears. |
| 2 | Inspect the cart. | Exactly Backpack QTY 1 and Bike Light QTY 1; no additional products. |

**Execution history:** Initial run FAIL against an obsolete exercise expectation that Cancel would navigate to Products. BA clarification corrected the expectation; updated test re-executed and **PASS**. Preserve the initial FAIL as historical, not a confirmed application defect.

## TC-018 — Cancel Checkout from Overview

- **Requirement:** REQ-015
- **Preconditions:** Logged in using `standard_user` / `secret_sauce`; entered First Name `John`, Last Name `Doe`, ZIP/Postal Code `50003` on Checkout: Your Information; Checkout: Overview displayed; cart contains only the products in Test Data.
- **Test data:** Sauce Labs Backpack QTY 1; Sauce Labs Bike Light QTY 1.
- **BA clarification:** Cancel from **Overview** navigates to **Products**; cart remains unchanged; no order completion confirmation; when checkout is restarted all three information fields are empty.

| Step | Action | Expected result | Recorded actual result | Status |
|---|---|---|---|---|
| 1 | Click **Cancel** and check destination. | Products displayed; no completion confirmation. | Products page displayed; no order completion confirmation. | PASS |
| 2 | Click Shopping Cart icon and check destination. | Your Cart displayed. | Your Cart page displayed. | PASS |
| 3 | Check cart contents. | Exactly specified products and quantities, no others. | Backpack QTY 1, Bike Light QTY 1, no additional products. | PASS |
| 4 | Click **Checkout** and check destination. | Checkout: Your Information displayed. | Checkout: Your Information page displayed. | PASS |
| 5 | Inspect First Name, Last Name and ZIP/Postal Code input fields. | All three fields are empty. | All three fields were empty. | PASS |

**Recorded execution:** PASS. Additional notes: None.

## Overall summary

- 11 test cases (TC-008–TC-018); latest execution result: **11 PASS, 0 FAIL**.
- TC-017 retains a historical FAIL due to an exercise requirement clarification; latest run PASS.
- No confirmed application defects were identified in this assignment.
- Test execution evidence consists of tester-reported observations; no independently verifiable screenshots, API or database evidence were provided.
- Not covered: backend order persistence; checkout behavior with an empty cart; removal of one item from a multi-item cart.
