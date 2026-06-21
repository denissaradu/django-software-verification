# Bug Reports – Django CRUD SQLite Verification Project

## Bug 1 – Duplicate student records are allowed

**ID:** BUG-001  
**Severity:** Medium  
**Priority:** Medium  
**Environment:** Localhost / Django app running on Python 3.10

### Summary
The application allows creating multiple student records with the same Identity Number, which can lead to duplicate entries.

### Preconditions
- Application is running locally
- User is on the **Create New Student** page

### Steps to Reproduce
1. Open the **Create New Student** form
2. Enter a valid student name
3. Enter an Identity Number that already exists in the system
4. Fill in the remaining required fields
5. Click **Save**

### Expected Result
The application should prevent duplicate student records or validate that the Identity Number is unique.

### Actual Result
The record is saved successfully even when the Identity Number already exists.

### Status
Open