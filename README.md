# 🚗 Car Rental System -- Manual Testing Portfolio

A structured manual testing project for a **Java console-based Car
Rental System**, covering booking workflows, billing calculations,
return operations, invalid inputs, edge cases, and end-to-end scenarios.

This testing project includes **29 manually executed test cases**
designed to validate both normal user flows and failure-prone scenarios.

## 📌 Project Overview

The Car Rental System allows users to view available cars, rent a car,
enter customer information, select rental duration, calculate rental
cost, confirm or cancel bookings, return rented cars, and rent returned
cars again.

## 🧪 Test Summary

  Metric                                Result
  ------------------- ------------------------
  Total Test Cases                          29
  Passed                                    25
  Failed                                     4
  Pass Rate                              86.2%
  Fail Rate                              13.8%
  Priority Coverage     Critical, High, Medium
  Execution Status                   Completed

**Overall result:** 25 of 29 test cases passed. Core menu navigation,
standard billing calculations, booking cancellation, car return,
re-rental, and multi-customer workflows worked successfully. Four cases
failed around booking validation and billing edge-case handling.

## 🎯 Testing Scope

-   Main menu navigation
-   Valid and invalid menu selection
-   Car availability display
-   Successful car booking
-   Booking cancellation
-   Rental confirmation
-   Invalid car ID handling
-   Already-rented car validation
-   Customer input validation
-   One-day and long-duration billing
-   Zero and negative rental-day validation
-   Non-numeric rental duration
-   Successful and invalid car returns
-   Duplicate return attempts
-   Re-renting after return
-   Multiple customer rentals
-   Cancel-and-rebook workflow

## 📊 Test Results by Module

  Module               Total   Passed   Failed
  ----------------- -------- -------- --------
  Menu Navigation          6        6        0
  Booking                 11        8        3
  Billing                  5        4        1
  Return Workflow          5        5        0
  End-to-End               2        2        0
  **Total**           **29**   **25**    **4**

## ❌ Failed Test Cases

  -----------------------------------------------------------------------
  Test Case ID      Scenario          Priority          Result
  ----------------- ----------------- ----------------- -----------------
  TC-BOOK-002       Book C901 for 3   Critical          Fail
                    days and verify                     
                    successful                          
                    booking state                       

  TC-BOOK-07        Enter invalid car High              Fail
                    ID during booking                   

  TC-BOOK-08        Attempt to rent   Critical          Fail
                    an already rented                   
                    car                                 

  TC-BILL-04        Enter negative    Critical          Fail
                    rental days                         
  -----------------------------------------------------------------------

### Key Risk Areas

1.  **Booking-state reliability** --- successful booking behavior and
    car availability state should be reviewed.
2.  **Invalid car selection handling** --- invalid IDs should be
    rejected consistently.
3.  **Duplicate rental prevention** --- an already-rented car must not
    be rentable again.
4.  **Negative billing input validation** --- negative rental duration
    must be rejected before billing or confirmation.

Three of the four failed cases have **Critical** priority and should be
fixed before release.

## 🧭 Menu Navigation Testing

The main menu was tested with valid options, unsupported numeric
options, and non-numeric input.

-   Main menu displayed correctly
-   Rent a Car opened the correct workflow
-   Return a Car opened the correct workflow
-   Exit closed the application correctly
-   Unsupported numeric input was handled
-   Non-numeric menu input was handled without application failure

**Module Result: 6/6 Passed**

## 📅 Booking Testing

Booking tests covered normal rental flows, cancellation, confirmation
behavior, invalid car selection, already-rented cars, car ID format, and
customer information.

Successful scenarios included available-car display, correct C902 and
C903 billing, booking cancellation, lowercase confirmation input, and
tested customer-input scenarios.

Failed scenarios involved the C901 booking case, invalid car ID booking,
and prevention of renting an already-rented car.

**Module Result: 8/11 Passed**

## 💳 Billing and Edge-Case Testing

  Scenario            Expected Behavior                 Result
  ------------------- --------------------------------- --------
  C901 for 1 day      800.00 taka                       Pass
  C902 for 365 days   182,500.00 taka                   Pass
  0 rental days       Reject invalid duration           Pass
  -3 rental days      Reject negative duration          Fail
  Non-numeric days    Reject gracefully without crash   Pass

The negative rental-duration failure is a significant validation risk
because the application should never allow a negative rental period or
negative billing amount.

**Module Result: 4/5 Passed**

## 🔄 Return Workflow Testing

-   Currently rented car returned successfully
-   Non-rented car return attempt was rejected
-   Invalid car ID return attempt was handled
-   Second return attempt for the same car was rejected
-   Returned car became available for rental again

**Module Result: 5/5 Passed**

## 🔁 End-to-End Testing

Two complete workflow scenarios passed:

-   Two different customers successfully rented two different cars
    independently.
-   A canceled C903 booking did not block a later successful booking of
    the same car.

**Module Result: 2/2 Passed**

## 🧠 Test Design Techniques Applied

-   Positive testing
-   Negative testing
-   Functional testing
-   Input validation testing
-   Boundary-value testing
-   Billing verification
-   State-transition testing
-   Edge-case testing
-   End-to-end testing
-   Error-handling validation

## 🛠️ Technology & Testing Environment

  Category               Technology
  ---------------------- --------------------------
  Application Type       Java Console Application
  Programming Language   Java
  Testing Type           Manual Testing
  Test Documentation     Structured Test Cases
  Version Control        Git
  Repository Hosting     GitHub

## 📂 Suggested Repository Structure

``` text
Car-Rental-System/
├── CarRentalSystem.java
├── README.md
├── testing/
│   └── Car_Rental_System_Manual_Test_Cases.docx
└── screenshots/
    ├── passed-tests/
    └── failed-tests/
```

## 🚦 QA Assessment

### Strengths

-   Menu navigation is stable
-   Standard billing calculations work correctly
-   Booking cancellation works correctly
-   Return workflow is reliable
-   Cars can be rented again after successful return
-   Multi-customer rental workflow works correctly
-   Most invalid and boundary inputs are handled successfully

### Areas for Improvement

-   Strengthen booking-state management
-   Reject invalid car IDs consistently
-   Enforce car availability before creating a rental
-   Add strict validation for negative rental duration
-   Regression-test all failed Critical-priority scenarios

### Recommendation

**Conditional GO / Fix Before Release**

The application demonstrates stable core functionality with an **86.2%
test pass rate**, but the failed Critical-priority cases involving
duplicate rental prevention, booking reliability, and negative
rental-duration validation should be fixed and regression-tested before
a production release.

## 👤 Author

### Masuduzzaman Niloy

**Software Quality Assurance (SQA) Enthusiast**

Focused on Manual Testing, API Testing, Database Testing, Test Case
Design, Defect Reporting, and Test Automation.

------------------------------------------------------------------------

⭐ This repository demonstrates practical manual testing skills through
structured test design, execution results, edge-case validation, and QA
assessment of a Java-based Car Rental System.
