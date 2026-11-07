# SauceDemo – Manual Login Testing

A practical manual QA portfolio project covering the login functionality of [SauceDemo](https://www.saucedemo.com/).

## Scope
Seven manually designed and reviewed test cases covering login field visibility, successful and unsuccessful authentication, mandatory fields, validation messages, password masking, and post-login navigation. This is a focused login feature exercise, **not** a full application test or security assessment.

## Results
- **7 test cases: PASS** based on recorded manual observations.
- TC-004: four data-driven scenarios (all PASS).
- TC-005: three validation-message checks (all PASS), evaluated using evidence recorded during TC-004 execution; not a separate rerun.
- No currently reproducible defects were confirmed during this test round.

## Project files
- [`test-plan/Test_Plan.md`](test-plan/Test_Plan.md) – scope, approach, environment and limitations.
- [`test-cases/Login_Test_Cases.xlsx`](test-cases/Login_Test_Cases.xlsx) – requirements, test cases, data sets and execution records.
- [`test-results/Test_Execution_Report.md`](test-results/Test_Execution_Report.md) – execution summary and observed results.
- [`bug-reports/README.md`](bug-reports/README.md) – historical observation and defect-reporting policy.

## Environment
Manual testing on SauceDemo in a desktop browser. Previous baseline: Windows 11 25H2 and Microsoft Edge 154.0.4258.48. The exact browser version and execution date for the latest run were **not recorded**; do not treat the baseline as verified for that run.

## Requirements disclaimer
REQ-001 to REQ-007 are **portfolio exercise assumptions** derived from expected application behavior. They are not official SauceDemo requirements. In particular, REQ-007 assumes navigation to `/inventory.html` after successful login; this URL was observed in the latest run.

## Evidence and reproducibility
Actual Results were recorded by the tester and reviewed for consistency with Expected Results. No screenshots, video captures, browser logs, or independently verifiable execution artifacts are included. Password masking is a visual check, not a claim that the password is encrypted or inaccessible to JavaScript.

## Tools and skills
Manual functional testing, positive/negative testing, test case design, data-driven scenarios, expected vs. actual results, defect triage, documentation and traceability.
