# Assignment 3 — Test Summary Report

## 1. Test Scope
The exercise covered SauceDemo shopping cart and checkout functionality: adding/removing products, multiple items, cart content and prices, mandatory checkout information, order overview, completing a purchase and cancelling checkout.

## 2. Test Execution Results
Eleven test cases (TC-008–TC-018) were executed. Their latest reported results were **11 PASS, 0 FAIL, 0 BLOCKED**. TC-017 has a historical FAIL against an initial exercise assumption; following a simulated BA clarification and test-case revision, its re-execution was PASS. All eight exercise requirements are represented by at least one executed test, but this is not exhaustive scenario coverage.

## 3. Defects and Issues
No confirmed application defects were reported for this assignment. The TC-017 discrepancy concerned an unconfirmed navigation expectation; the exercise requirement was clarified before the test was updated. The original execution history is retained.

## 4. Risks and Limitations
- Purchase completion was verified through the UI completion page and message only; no API or database evidence confirms backend order processing or persistence.
- Checkout behavior with an empty shopping cart was not tested; expected behavior would require clarification.
- Removing one product from a cart containing multiple different products was not tested; earlier removal cases used a single-item cart.
- Results are tester-reported without screenshots, video, or logs; the exact execution date and browser version were not captured.
- Requirements, approved prices and tax rate were exercise assumptions, not official SauceDemo acceptance criteria.

## 5. Conclusion and Recommendation
All latest executions passed against the agreed exercise expectations. This supports the tested user-visible scenarios but does not establish that the application is defect-free. Before making claims about completed order processing, expand the scope to backend/API or database verification where access and requirements permit. Add targeted cart and checkout negative/combination tests and retain reproducible evidence in future runs.
