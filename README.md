# Database Sanitization Automation Script
## Overview

This Bash script automates:

1. Production database cloning

2. Sensitive data sanitization

3. Secure credential retrieval from AWS Secrets Manager

4. Dynamic column type detection

5. Full-table and column-level sanitization

6. Designed for creating safe staging/testing environments from production data.

## Demo

- Example data from Database before running sanitization script
  <img width="736" height="354" alt="image" src="https://github.com/user-attachments/assets/150b46bf-e548-4820-b697-69867ba7aea5" />

- Example data from Database after sanitization script
  <img width="736" height="354" alt="image" src="https://github.com/user-attachments/assets/214f31a6-c364-4208-9102-adfb957e9a52" />

Note: It is just an example DB, this script is effective on any size of database.



## Features

1. Secure credential retrieval from AWS Secrets Manager

2. Automated database clone (mysqldump + restore)

3. Column type–aware sanitization:

4. Text fields → masked values

5. Numeric fields → zeroed

6. Dates → normalized

7. ENUM → first valid enum value

8. Binary → reset to 0

## Supports:

1. Full table sanitization

2. Specific column sanitization

3. Temporary credentials file with restricted permissions

4. Automatic cleanup

## Technologies Used

1. Bash scripting

2. AWS CLI

3. MySQL

4. jq

5. Information Schema queries

# Use Case

This script is useful when:

-  Creating sanitized staging databases

-  Sharing data with QA

- Migrating data without exposing PII

- Compliance requirements (GDPR-style masking)

## Requirements

1. AWS CLI configured

2. jq installed

3. MySQL client installed

4. Secrets stored in AWS Secrets Manager

## How It Works

1. Fetch credentials from AWS Secrets Manager

2. Create secure temporary .my.cnf

3. Clone production database

4. Detect column data types dynamically

5. Apply sanitization logic based on column type

6. Clean up credentials

## Disclaimer

This is a demonstration script.
Do not use directly in production without review and testing.
