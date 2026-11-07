# Test Plan – SauceDemo Login

## 1. Objective
Verify selected user-visible login behaviors of https://www.saucedemo.com/ using seven manual test cases.

## 2. Scope
**In scope:** login form visibility, valid login, invalid username, required fields, validation error messages, password masking, and post-login URL.

**Out of scope:** checkout, cart, performance, accessibility audit, security penetration testing, automated tests, cross-browser compatibility, and password recovery.

## 3. Test basis
REQ-001 to REQ-007 are exercise-level assumptions authored for this portfolio, **not official product specifications**. Test expectations must be revised if authoritative requirements differ.

## 4. Environment
- Target: https://www.saucedemo.com/
- Historical baseline: Windows 11 25H2; Microsoft Edge 154.0.4258.48 (64-bit)
- Latest execution: browser/OS version and execution timestamp not independently captured
- Internet connectivity required
- Use a fresh InPrivate session per TC-004 dataset, closing **all** InPrivate windows between datasets to avoid shared private-session state

## 5. Test data
- Valid username: `standard_user`
- Valid password: `secret_sauce` (public SauceDemo demo credential)
- Invalid username: `Standard_user` (capital S)
- Empty fields represented by `""`

## 6. Execution approach
1. Start from a logged-out login page; for data-driven cases use a fresh isolated InPrivate session for each dataset.
2. Execute documented steps, checking the expected behavior **before closing the browser**.
3. Record Actual Result and PASS/FAIL for each dataset.
4. Reuse TC-004 recorded validation messages as evidence for TC-005; explicitly document the evidence linkage.
5. Raise a defect only when the observed behavior demonstrably contradicts an agreed requirement; capture environment, reproduction steps and supporting evidence.

## 7. Exit criteria
All seven test cases executed and reviewed; each data-driven scenario has an Actual Result and status. No claim of complete application coverage is made.

## 8. Risks and limitations
- Requirements are portfolio assumptions, not approved product requirements.
- Results are self-reported observations; no screenshot/video evidence was retained.
- Latest execution date and browser build were not recorded.
- A historical URL discrepancy (BUG-001) did not reproduce during the latest TC-007 run and is not a confirmed current defect.
- Masking verifies display behavior only.
