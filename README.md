# Banking Management System Database

## Overview

This project implements a database schema for a Banking Management System (BMS) to manage customer information, bank details, and account information. The database schema is designed using MySQL and includes the following tables:
- `CUSTOMER_PERSONAL_INFO`
- `CUSTOMER_REFERENCE_INFO`
- `BANK_INFO`
- `ACCOUNT_INFO`

## Database Schema

### Table: CUSTOMER_PERSONAL_INFO
This table stores personal information of customers.

| Column Name                | Data Type    | Constraints                        |
|----------------------------|--------------|------------------------------------|
| CUSTOMER_ID                | VARCHAR(5)   | PRIMARY KEY                        |
| CUSTOMER_NAME              | VARCHAR(30)  | NOT NULL                           |
| DATE_OF_BIRTH              | DATE         | NOT NULL                           |
| GUARDIAN_NAME              | VARCHAR(30)  |                                    |
| ADDRESS                    | VARCHAR(50)  |                                    |
| CONTACT_NO                 | BIGINT(10)   |                                    |
| MAIL_ID                    | VARCHAR(30)  |                                    |
| GENDER                     | CHAR(1)      |                                    |
| MARITAL_STATUS             | VARCHAR(10)  |                                    |
| IDENTIFICATION_DOC_TYPE    | VARCHAR(20)  |                                    |
| ID_DOC_NO                  | VARCHAR(20)  |                                    |
| CITIZENSHIP                | VARCHAR(10)  |                                    |

### Table: CUSTOMER_REFERENCE_INFO
This table stores reference information for customers.

| Column Name                | Data Type    | Constraints                        |
|----------------------------|--------------|------------------------------------|
| CUSTOMER_ID                | VARCHAR(5)   | PRIMARY KEY, FOREIGN KEY           |
| REFERENCE_ACC_NAME         | VARCHAR(20)  |                                    |
| REFERENCE_ACC_NO           | BIGINT(16)   |                                    |
| REFERENCE_ACC_ADDRESS      | VARCHAR(50)  |                                    |
| RELATION                   | VARCHAR(25)  |                                    |

### Table: BANK_INFO
This table stores information about banks.

| Column Name                | Data Type    | Constraints                        |
|----------------------------|--------------|------------------------------------|
| IFSC_CODE                  | VARCHAR(15)  | PRIMARY KEY                        |
| BANK_NAME                  | VARCHAR(25)  |                                    |
| BRANCH_NAME                | VARCHAR(25)  |                                    |

### Table: ACCOUNT_INFO
This table stores information about customer accounts.

| Column Name                | Data Type    | Constraints                        |
|----------------------------|--------------|------------------------------------|
| ACCOUNT_NO                 | BIGINT(16)   | PRIMARY KEY                        |
| CUSTOMER_ID                | VARCHAR(5)   | FOREIGN KEY                        |
| ACCOUNT_TYPE               | VARCHAR(10)  |                                    |
| REGISTRATION_DATE          | DATE         |                                    |
| ACTIVATION_DATE            | DATE         |                                    |
| IFSC_CODE                  | VARCHAR(10)  | FOREIGN KEY                        |
| INTEREST                   | DECIMAL(7,2) |                                    |
| INITIAL_DEPOSIT            | BIGINT(10)   |                                    |
