# Test Plan — Shopping Cart & Checkout

## Objective and scope
Manually verify REQ-008–REQ-015 in SauceDemo with positive and negative functional scenarios for cart and checkout.

## Environment
- Target: https://www.saucedemo.com/
- Public demo credentials: `standard_user` / `secret_sauce`
- Desktop browser; exact browser build and execution date for Assignment 3 were not captured. The historical project baseline (Windows 11 / Edge) is not evidence of the version used for these runs.

## Test approach
1. Prepare the specified cart contents and checkout state before each case.
2. Follow documented steps and compare observed behavior to the *exercise* requirements.
3. Record actual outcomes and PASS/FAIL; preserve historical runs after requirement changes.
4. Escalate ambiguous expected behavior to the simulated BA rather than reporting an application defect based on an unconfirmed assumption.

## Entry and exit criteria
Entry: application accessible, public demo credentials work, test data and exercise requirements available. Exit: all 11 cases executed and reviewed; any deviations or limitations documented.

## Exclusions and limitations
No backend/API/database verification, automated testing, cross-browser matrix, performance or security assessment. No screenshot/video evidence attached. Requirements and tax/price oracle are training assumptions.
