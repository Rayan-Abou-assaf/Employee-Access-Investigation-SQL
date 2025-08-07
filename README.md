# Employee Access Investigation using SQL
**Part of the Google Cybersecurity Professional Certificate**
## Project Objective

This project simulates a real-world security investigation where, as a cybersecurity analyst, I used SQL to query a company's database. The primary goal was to identify potential security anomalies and conduct internal audits by analyzing employee login data and departmental records.
### Technologies Used

    SQL (Structured Query Language)

    Relational Databases

    Command-Line Interface (CLI)

## **The Investigation: Key Tasks & Findings**

I performed several queries to investigate different potential security and compliance issues.
## Task 1: Identifying Suspicious After-Hours Activity
   ### Scenario: The company has a policy that all work should be completed by 18:00. Any login attempts after this time are considered unusual and must be reviewed.
```
    Query:
    code SQL

    SELECT * 
    FROM log_in_attempts 
    WHERE login_time > '18:00';

    Insight: This query successfully isolated all login attempts that occurred outside of standard business hours, providing a targeted list for further investigation into potential unauthorized access.
```
## Task 2: Detecting Geographically Unusual Logins
  ### Scenario: All company employees are based in Mexico. Any login attempt from another country is a major security red flag that could indicate a compromised account.
```
    Query:
    code SQL

    SELECT * 
    FROM log_in_attempts 
    WHERE country NOT LIKE 'MEX%';

    Insight: Using NOT LIKE effectively filtered out all domestic logins, immediately flagging international attempts that require immediate follow-up by the security team.
```
## Task 3: Filtering Events for Specific High-Risk Dates
  ### Scenario: The security team was alerted to potential threats on two specific dates (May 8th and May 9th, 2022) and needed to review all login activity for those days.
```
    Query:
    code SQL
    
   SELECT * 
   FROM log_in_attempts 
   WHERE login_date = ‘2022-05-09’ AND login_date = ‘2022-05-08’;

    Insight: The IN operator provided a clean and efficient way to retrieve all relevant records from both dates in a single query, which is more effective than using OR for multiple values.
```
## Task 4: Conducting Internal Departmental Audits 
  ###  Scenario: As part of a compliance check, I needed to retrieve lists of employees based on their department to verify access levels and team rosters.
  
  - To find all Marketing employees in the East building:
```  
 code SQL

SELECT * FROM employees WHERE department = 'Marketing' AND office LIKE 'EAST%';
```
    
- To create a list of all Finance and Sales employees:
```
code SQL

SELECT * FROM employees WHERE department IN ('Finance', 'Sales');
```
- To identify all non-IT employees for a security policy update:
```
code SQL

        SELECT * FROM employees WHERE NOT department = 'IT';

    Insight: These queries demonstrate the ability to use SQL for internal auditing, using AND, IN, and NOT operators to create precise employee lists for security and compliance purposes.
```
## **Project Summary & Key Takeaways**

This project was a practical exercise in using SQL as a primary tool for cybersecurity analysis. I successfully demonstrated my ability to perform crucial tasks such as data filtering, pattern recognition, and anomaly detection. I am confident in my ability to write targeted SQL queries to investigate potential security incidents and support internal audits.
