# Django CRUD SQLite – Software Verification Project

## Project Overview

This repository contains a **software verification / QA project** based on the open-source application **Django CRUD SQLite**.

The goal of this project was to practice:

* environment setup and troubleshooting
* manual testing of a web application
* identifying functional issues and validation gaps
* documenting findings in a professional QA format

The tested application is a simple **student management CRUD system** built with **Django** and **SQLite**.

---

## Application Under Test

**Source application:** Django CRUD SQLite
**Technology stack:**

* Python 3.10
* Django 2.1.5
* SQLite
* HTML templates / server-side rendering

---

## Scope of Testing

The following core flows were tested manually:

* **Create student**
* **View student details**
* **Edit existing student**
* **Delete student**
* **Input validation behavior**
* **Basic negative scenarios**

---

## Environment Setup

The project was executed locally on Windows using a Python virtual environment.

### Setup steps

1. Clone the application repository
2. Create and activate a virtual environment
3. Install dependencies from `requirements.txt`
4. Adjust local settings to run with SQLite
5. Start the Django development server
6. Execute manual verification scenarios

---

## Test Environment

* **OS:** Windows
* **Python version:** 3.10
* **Framework:** Django 2.1.5
* **Database:** SQLite
* **Execution type:** Manual testing

---

## Test Scenarios Covered

The following scenarios were checked during verification:

### Create Student

* Create a student with valid data
* Attempt to create a student with empty required fields
* Attempt to create a student with duplicate identity number
* Check behavior for very long input values
* Check handling of leading / trailing spaces

### Read / View Details

* Open student detail page from list
* Verify displayed data matches saved data

### Update Student

* Edit an existing student with valid values
* Edit using special characters / unexpected input
* Check whether validation blocks invalid values

### Delete Student

* Delete an existing student
* Verify confirmation step appears
* Verify record is removed from the list after confirmation

---

## Main Findings

During testing, the following behaviors were observed:

### Working behaviors

* Student records can be created successfully
* Student detail page works correctly
* Edit flow works
* Delete flow works and asks for confirmation
* Required empty fields are not accepted

### Issues / validation gaps

* Duplicate student records are allowed
* Very long values are accepted without visible validation feedback
* Input validation is limited for some fields
* Leading and trailing spaces are trimmed in some cases, but validation behavior is not fully robust

---

## Defects Identified

A defect report was documented for the duplicate record behavior.

See:

* `qa-docs/bug-reports.md`

---

## Test Documentation

Project documentation is stored in the `qa-docs` folder:

* `qa-docs/test-execution-summary.md`
* `qa-docs/bug-reports.md`

---

## Skills Demonstrated in This Project

Through this project I practiced and demonstrated:

* Manual testing of CRUD web applications
* Test scenario execution and defect discovery
* Writing bug reports and test summaries
* Environment setup and troubleshooting
* Working with Python virtual environments
* Understanding of Django project structure
* Basic software verification mindset and QA documentation

---

## Notes

This repository is intended as a **portfolio QA / software verification project** to demonstrate practical testing work on a real application, including setup, execution, findings, and documentation.
