# SauceDemo – Manual Testing Portfolio

A practical manual software QA portfolio based on [SauceDemo](https://www.saucedemo.com/).

The project demonstrates manual test analysis, test case design, test execution, defect handling, requirements clarification, and test reporting.

## Project Structure

### Assignment 1 – Login Testing

**Status: Completed**

Seven manually designed and reviewed test cases covering:

- Login field visibility
- Successful and unsuccessful authentication
- Mandatory field validation
- Error messages
- Password masking
- Navigation after successful login

**Results:** 7 test cases passed.

**Documentation:**

- [Test Plan](Assignment-01-Login-Testing/test-plan/Test_Plan.md)
- [Test Cases and Test Data](Assignment-01-Login-Testing/test-cases/Login_Test_Cases.xlsx)
- [Test Execution Report](Assignment-01-Login-Testing/test-results/Test_Execution_Report.md)
- [Bug Reports](Assignment-01-Login-Testing/bug-reports/README.md)

### Assignment 3 – Shopping Cart & Checkout Testing

**Status: Completed**

Eleven manually designed and executed test cases covering:

- Adding and removing products from the shopping cart
- Adding multiple different products
- Cart content and price verification
- Mandatory checkout fields
- Checkout with valid information
- Order overview and total price verification
- Purchase completion
- Checkout cancellation from two different pages

**Results:** 11 test cases passed in their latest execution. TC-017 has a historical failed execution associated with a subsequently clarified requirement.

**Documentation:**

- [Assignment Overview](Assignment-03-Shopping-Cart-Checkout/README.md)
- [Requirements](Assignment-03-Shopping-Cart-Checkout/Requirements.md)
- [Test Plan](Assignment-03-Shopping-Cart-Checkout/Test_Plan.md)
- [Test Cases](Assignment-03-Shopping-Cart-Checkout/Test_Cases.md)
- [Test Data](Assignment-03-Shopping-Cart-Checkout/Test_Data.csv)
- [Test Execution Report](Assignment-03-Shopping-Cart-Checkout/Test_Execution_Report.md)
- [Test Summary Report](Assignment-03-Shopping-Cart-Checkout/Test_Summary_Report.md)

## Test Environment

- Application: SauceDemo
- Operating system: Windows 11
- Browser: Microsoft Edge
- Testing approach: Manual functional testing

The previously documented baseline was Windows 11 25H2 and Microsoft Edge 154.0.4258.48. Exact environment versions and execution dates were not consistently recorded for all tests.

## Requirements Disclaimer

All requirements in this repository are portfolio exercise specifications derived from expected application behavior.

They are not official SauceDemo requirements.

Some acceptance criteria and test data were defined specifically for training purposes.

## Evidence and Limitations

Test execution results are based on observations recorded by the tester.

The repository does not currently include independently verifiable screenshots, video recordings, or backend execution evidence.

Successful order completion was verified through the user interface only. Backend processing and database persistence were not tested.

Passing test cases do not demonstrate that the application is free of defects.

## Skills Demonstrated

- Manual functional testing
- Positive and negative testing
- Test case design
- Data-driven testing
- Requirements analysis and clarification
- Expected versus actual results
- Defect triage and retesting
- Test execution reporting
- Test coverage analysis
- Test summary reporting

## Future Work

**Assignment 4 – Test Design Techniques**

Planned topics include:

- Equivalence Partitioning
- Boundary Value Analysis
- Decision Tables

The goal is to improve systematic test coverage and identification of negative and boundary scenarios.