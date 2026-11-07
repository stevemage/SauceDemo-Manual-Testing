# Test Execution Report – SauceDemo Login

## Summary
**7/7 test cases PASS** based on tester-reported manual observations. **0 FAIL**. TC-005 uses evidence from TC-004, not an independent execution. Execution date and exact browser version were not recorded.

| Test case | Result | Evidence summary |
|---|---|---|
| TC-001 | PASS | Username and Password fields visible on login page |
| TC-002 | PASS | Products page displayed; Logout option available in application menu |
| TC-003 | PASS | Invalid username rejected; invalid-credentials message shown |
| TC-004 | PASS | Four datasets: three rejected, one accepted |
| TC-005 | PASS | Appropriate messages observed for three missing-field scenarios (reused from TC-004) |
| TC-006 | PASS | Password characters displayed as dots, not readable text |
| TC-007 | PASS | Products page displayed; URL `https://www.saucedemo.com/inventory.html` |

## Data-driven observations

| Case | Dataset | Actual Result | Status |
|---|---|---|---|
| TC-004 | DS-01 (both empty) | Login rejected. `Epic sadface: Username is required` | PASS |
| TC-004 | DS-02 (password empty) | Login rejected. `Epic sadface: Password is required` | PASS |
| TC-004 | DS-03 (username empty) | Login rejected. `Epic sadface: Username is required` | PASS |
| TC-004 | DS-04 (valid credentials) | Login accepted. (Destination not separately recorded for this dataset.) | PASS |
| TC-005 | DS-01 | Missing-username message as recorded for TC-004 DS-01 | PASS |
| TC-005 | DS-02 | Missing-password message as recorded for TC-004 DS-02 | PASS |
| TC-005 | DS-03 | Missing-username message as recorded for TC-004 DS-03 | PASS |

## Detailed observations
- **TC-001:** Both Username and Password input fields were visible on the login page.
- **TC-002:** The Products page was displayed. The Logout option was available in the application menu.
- **TC-003:** The login attempt was rejected. Error: `Epic sadface: Username and password do not match any user in this service`.
- **TC-006:** The password characters were displayed as `............` (masking dots).
- **TC-007:** The Products page was displayed and the browser URL was `https://www.saucedemo.com/inventory.html`.

## Defects and caveats
No current defect was confirmed. REQ-001 to REQ-007 are portfolio assumptions, not authoritative SauceDemo specifications.
