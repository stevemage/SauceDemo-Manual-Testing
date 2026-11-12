# Assignment 3 — Test Execution Report

## Latest result

| Metric | Value |
|---|---:|
| Test cases | 11 |
| PASS | 11 |
| FAIL | 0 |
| BLOCKED | 0 |
| Requirements represented | 8 (REQ-008–REQ-015) |

| Requirement | Test cases | Latest status |
|---|---|---|
| REQ-008 | TC-008 | PASS |
| REQ-009 | TC-009, TC-010 | PASS |
| REQ-010 | TC-011 | PASS |
| REQ-011 | TC-012 | PASS |
| REQ-012 | TC-013, TC-014 | PASS |
| REQ-013 | TC-015 | PASS |
| REQ-014 | TC-016 | PASS |
| REQ-015 | TC-017, TC-018 | PASS |

## TC-013 data-driven execution
Seven negative datasets were reported PASS; see `Test_Data.csv`. The tester reset the fields between datasets.

## TC-017 requirement clarification and history
- **Run 1 (historical): FAIL against the original exercise expectation** that Cancel on Your Information returns to Products. Actual navigation was to Your Cart. This was not classified as a confirmed product defect because the expectation was an unverified exercise assumption.
- **Simulated BA clarification:** expected destination from Your Information is Your Cart; cart contents preserved; no completion confirmation.
- **Run 2 (latest): PASS** after updating TC-017 to the clarified exercise acceptance criteria. Both specified products remained in the cart, each QTY 1.

## TC-018 execution details
1. Cancel from Overview → Products; no completion confirmation — PASS.
2. Open cart → Your Cart — PASS.
3. Backpack QTY 1 and Bike Light QTY 1; no extras — PASS.
4. Click Checkout → Your Information — PASS.
5. First Name, Last Name and ZIP/Postal Code empty — PASS.

## Evidence limitations
Actual results were self-reported; no screenshots, browser logs, API responses, or DB records are attached. Execution dates and browser version were not recorded for this assignment.
