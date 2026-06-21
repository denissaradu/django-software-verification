# Django Software Verification Project

## Overview

This project documents the **manual software verification** of a Django CRUD web application used for managing student records.

The application was cloned from an existing open-source Django project and set up locally for testing. During the verification process, I configured the application environment, resolved setup issues, executed manual test scenarios, identified defects, and documented the testing results.

The purpose of this project is to demonstrate my practical QA skills in:

* understanding an existing application
* setting up a test environment
* performing functional verification of a CRUD application
* identifying and documenting defects
* creating QA documentation for test execution and findings

---

## Project Scope

The application under test is a simple **Student Management CRUD application** built with Django.
It allows users to:

* create student records
* view the student list
* open student details
* edit student information
* delete student records

The verification scope focused on the **Student CRUD flow** and the validation behavior of the input fields.

---

## Objectives

The main objectives of this verification project were:

* to validate the core CRUD functionality of the application
* to check whether the application handles valid and invalid input correctly
* to identify usability or validation issues
* to document defects and testing results in a structured QA format
* to simulate a real software verification workflow on an existing application

---

## Test Environment

* **Application type:** Django web application
* **Language / framework:** Python, Django
* **Database:** SQLite
* **Operating system:** Windows
* **Testing type:** Manual functional testing
* **Scope:** Student CRUD module

---

## Test Approach

The verification process was performed manually and focused on the main user flows of the application.

### Functional areas tested

* **Create Student**
* **Read / View Student List**
* **Student Details page**
* **Edit Student**
* **Delete Student**
* **Input validation behavior**
* **Negative scenarios and edge cases**

### Test design focus

The test scenarios covered:

* successful creation of records with valid data
* behavior when mandatory fields are empty
* duplicate records
* invalid data in fields that should accept specific formats
* very long values
* leading and trailing spaces
* delete confirmation behavior
* persistence of changes after refresh

---

## Setup and Technical Work

Before testing the application, I also had to set up and troubleshoot the project locally.
This included:

* cloning the original repository
* creating a Python virtual environment
* resolving Python version compatibility issues
* installing project dependencies
* adjusting the project settings to run locally
* fixing environment-related issues such as:

  * database configuration
  * allowed hosts configuration
  * middleware configuration
  * local server execution

This part of the work was valuable because it simulated a realistic scenario where a QA engineer must first understand and prepare the application before starting verification.

---

## Key Verification Findings

During testing, I identified several behaviors and validation gaps in the application.

### Examples of findings

* the application prevents saving completely empty required fields
* duplicate student records are allowed
* the identity number field accepts values longer than expected
* validation for numeric-only fields is weak or missing
* leading and trailing spaces are normalized in some cases
* fields containing only spaces are not saved, but the behavior is not clearly communicated to the user
* delete action requires confirmation and works correctly after confirmation

These observations were documented as part of the QA deliverables included in this repository.

---

## QA Deliverables Included

This repository includes QA documentation created during the verification process.

### `qa-docs/bug-reports.md`

Contains the defects / issues identified during manual testing, including:

* title / summary
* steps to reproduce
* expected result
* actual result
* severity / impact

### `qa-docs/test-execution-summary.md`

Contains the execution summary of the manual verification, including:

* scope of testing
* executed scenarios
* observed results
* general conclusions

---

## Skills Demonstrated

Through this project, I practiced and demonstrated the following QA-related skills:

* manual functional testing
* exploratory testing
* test scenario execution
* defect identification and reporting
* verification of CRUD functionality
* negative testing and edge case testing
* analysis of validation behavior
* test documentation
* environment setup and troubleshooting
* understanding an existing application before testing it

---

## Future Improvements

The next planned step for this project is to extend it with **test automation**.

Potential next steps:

* create automated test cases for the Student CRUD flows
* automate happy-path and negative scenarios
* add UI test automation using **Pytest + Playwright** or **Pytest + Selenium**
* organize the automation project using a reusable structure
* optionally integrate the tests into a CI workflow

---

## Repository Purpose

This repository is part of my QA portfolio and is intended to showcase my practical approach to software verification on a real application, from setup and troubleshooting to test execution and documentation.

It reflects how I approach:

1. understanding an application
2. reproducing and investigating issues
3. validating functionality
4. documenting results clearly and professionally

---
