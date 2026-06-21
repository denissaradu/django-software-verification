# Test Cases – Django Student CRUD Application

## Project

Django Software Verification Project

## Module under test

Student CRUD functionality

## Scope

The following test cases cover the core functionality of the Student Management application:

* Create Student
* View Student List
* View Student Details
* Edit Student
* Delete Student
* Field validation and negative scenarios

---

# Test Cases

## TC-001 – Create a new student with valid data

**Objective:** Verify that a new student can be created successfully using valid input.

**Preconditions:**

* User is on the Student List page.

**Steps:**

1. Click **Create New Student**.
2. Enter a valid **Name**.
3. Enter a valid **Identity Number**.
4. Enter a valid **Address**.
5. Enter a valid **Department**.
6. Click **Save** / **Submit**.

**Expected Result:**

* The student record is created successfully.
* The new student appears in the Student List.
* The saved values are displayed correctly.

---

## TC-002 – View student details from the Student List

**Objective:** Verify that the user can open the details page of an existing student.

**Preconditions:**

* At least one student record exists.

**Steps:**

1. Open the Student List page.
2. Click **Detail** for an existing student.

**Expected Result:**

* The Student Detail page opens successfully.
* The correct student information is displayed.

---

## TC-003 – Edit an existing student with valid data

**Objective:** Verify that an existing student record can be edited successfully.

**Preconditions:**

* At least one student record exists.

**Steps:**

1. Open the Student List page.
2. Click **Edit** for an existing student.
3. Update one or more fields with valid data.
4. Click **Save** / **Submit**.

**Expected Result:**

* The student record is updated successfully.
* The modified values are displayed in the Student List and/or Student Detail page.

---

## TC-004 – Delete an existing student

**Objective:** Verify that a student record can be deleted successfully.

**Preconditions:**

* At least one student record exists.

**Steps:**

1. Open the Student List page.
2. Click **Delete** for an existing student.
3. Confirm the deletion when prompted.

**Expected Result:**

* The selected student is deleted successfully.
* The student no longer appears in the Student List after refresh.

---

## TC-005 – Attempt to create a student with all fields empty

**Objective:** Verify that the application prevents creating a student when required fields are left empty.

**Preconditions:**

* User is on the Create Student page.

**Steps:**

1. Open **Create New Student**.
2. Leave all fields empty.
3. Click **Save** / **Submit**.

**Expected Result:**

* The record is not created.
* Validation prevents submission.
* The user remains on the form page or receives validation feedback.

---

## TC-006 – Attempt to create a student with only the Name field empty

**Objective:** Verify validation when the Name field is missing.

**Preconditions:**

* User is on the Create Student page.

**Steps:**

1. Open **Create New Student**.
2. Leave **Name** empty.
3. Fill the other fields with valid data.
4. Click **Save** / **Submit**.

**Expected Result:**

* The student record is not created.
* A validation error is displayed for the Name field, or the form is rejected.

---

## TC-007 – Attempt to create a student with only spaces in the Name field

**Objective:** Verify how the application handles whitespace-only input in the Name field.

**Preconditions:**

* User is on the Create Student page.

**Steps:**

1. Open **Create New Student**.
2. Enter only spaces in the **Name** field.
3. Fill the remaining fields with valid data.
4. Click **Save** / **Submit**.

**Expected Result:**

* The application should reject whitespace-only input and prevent record creation.

**Actual observation during testing:**

* The form did not save the record when only spaces were entered, but no clear validation message was shown.

---

## TC-008 – Create a student with duplicate data

**Objective:** Verify whether the application allows duplicate student records.

**Preconditions:**

* A student record already exists in the system.

**Steps:**

1. Open **Create New Student**.
2. Enter the same values as an existing student record.
3. Click **Save** / **Submit**.

**Expected Result:**

* Depending on business rules, the application should either:

  * reject duplicates, or
  * allow them if duplicates are accepted by design.

**Actual observation during testing:**

* Duplicate records were accepted.

---

## TC-009 – Enter alphabetic characters in Identity Number

**Objective:** Verify whether the Identity Number field accepts invalid non-numeric values.

**Preconditions:**

* User is on the Create Student page.

**Steps:**

1. Open **Create New Student**.
2. Enter a valid Name.
3. Enter alphabetic characters in **Identity Number**.
4. Fill the remaining fields with valid data.
5. Click **Save** / **Submit**.

**Expected Result:**

* If the field is intended to be numeric, the application should reject alphabetic input and display validation feedback.

**Actual observation during testing:**

* Validation for Identity Number was weak / missing.

---

## TC-010 – Enter special characters in Identity Number

**Objective:** Verify whether the Identity Number field accepts special characters.

**Preconditions:**

* User is on the Create Student page.

**Steps:**

1. Open **Create New Student**.
2. Enter valid data in all fields.
3. In **Identity Number**, enter special characters such as `@#$%`.
4. Click **Save** / **Submit**.

**Expected Result:**

* If the field should be numeric only, the application should reject special characters.

**Actual observation during testing:**

* Validation was not strict enough.

---

## TC-011 – Create a student with a very long Name value

**Objective:** Verify how the application handles unusually long text input in the Name field.

**Preconditions:**

* User is on the Create Student page.

**Steps:**

1. Open **Create New Student**.
2. Enter an excessively long string in **Name**.
3. Fill the remaining fields with valid data.
4. Click **Save** / **Submit**.

**Expected Result:**

* The application should either:

  * save the value correctly if long values are allowed, or
  * display a validation error if a maximum length is exceeded.

**Actual observation during testing:**

* Very long values were accepted.

---

## TC-012 – Create a student with a very long Identity Number

**Objective:** Verify how the application handles very long input in the Identity Number field.

**Preconditions:**

* User is on the Create Student page.

**Steps:**

1. Open **Create New Student**.
2. Enter valid data in all fields.
3. Enter an excessively long value in **Identity Number**.
4. Click **Save** / **Submit**.

**Expected Result:**

* The application should enforce a reasonable length restriction if applicable.

**Actual observation during testing:**

* Very long Identity Number values were accepted.

---

## TC-013 – Create a student with leading and trailing spaces in Name

**Objective:** Verify how the application handles extra spaces before and after the Name value.

**Preconditions:**

* User is on the Create Student page.

**Steps:**

1. Open **Create New Student**.
2. Enter a Name with leading and trailing spaces.
3. Fill the remaining fields with valid data.
4. Click **Save** / **Submit**.

**Expected Result:**

* The application should trim unnecessary spaces and save a normalized value.

**Actual observation during testing:**

* Leading and trailing spaces were normalized and not saved as part of the final value.

---

## TC-014 – Cancel deletion of a student

**Objective:** Verify that cancelling the delete confirmation does not remove the record.

**Preconditions:**

* At least one student record exists.

**Steps:**

1. Open the Student List page.
2. Click **Delete** for an existing student.
3. When the confirmation prompt appears, choose **Cancel**.

**Expected Result:**

* The student record remains in the Student List.
* No deletion occurs.

---

## TC-015 – Verify deleted record is removed after refresh

**Objective:** Verify that deletion is persisted after page refresh.

**Preconditions:**

* A student record exists and is ready to be deleted.

**Steps:**

1. Delete a student record and confirm deletion.
2. Return to the Student List.
3. Refresh the page.

**Expected Result:**

* The deleted record is no longer displayed after refresh.
* The deletion is persisted successfully.

---

# Notes

These test cases were created based on the manual verification performed on the application and reflect both expected behavior and the actual behavior observed during testing.

The test suite can be extended in the future with:

* additional negative test cases
* field boundary validations
* UI / usability checks
* automated test implementation using Pytest + Playwright or Selenium
