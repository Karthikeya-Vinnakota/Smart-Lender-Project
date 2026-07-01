# Entity Relationship Diagram (ERD)

## Project
Smart Lender – AI Loan Approval Prediction

## Purpose
The ERD represents the database structure for storing customer information, loan details, employment information, property details, loan applications, and prediction results.

## Entities
- Customer
- Employment
- Loan
- Property
- LoanApplication
- Prediction

### Customer
- CustomerID (Primary Key)
- Name
- Gender
- Age
- Education
- Marital Status

### Employment
- EmploymentID (Primary Key)
- CustomerID (Foreign Key)
- Applicant Income
- Co-Applicant Income
- Self Employed

### Loan
- LoanID (Primary Key)
- Loan Amount
- Loan Term
- Credit History

### Property
- PropertyID (Primary Key)
- Property Area

### Loan Application
- ApplicationID (Primary Key)
- CustomerID (Foreign Key)
- EmploymentID (Foreign Key)
- LoanID (Foreign Key)
- PropertyID (Foreign Key)

### Prediction
- PredictionID (Primary Key)
- ApplicationID (Foreign Key)
- Predicted Status
- Confidence Score

## Relationships

- One Customer can submit many Loan Applications.
- One Customer has one Employment record.
- Each Loan Application refers to one Loan.
- Each Loan Application refers to one Property.
- Each Loan Application produces one Prediction.
