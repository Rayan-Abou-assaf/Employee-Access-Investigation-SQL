# Employee-Access-Investigation-SQL
## Project description
Through SQL I was able to retrieve data that included failed login attempts after work hours, and retrieve login attempts on specific dates and outside of Mexico.
Additionally, I was able to retrieve how many workers work in the marketing department, those who work in finance or sales, and employees who are not in the IT department.
### Technologies Used
- SQL
## **Retrieve after hours failed login attempts**
I used a SQL query to retrieve the failed login attempts, the query was ``` SELECT * FROM log_in_attempts WHERE login_time > ‘18:00’; ```.
This query provides me with the necessary data that is every login attempt that occurred after 18:00 o’clock, and this part is provided because of the added filter `WHERE`, and the operator `>`. This data is received from the log_in_attempts table, Which is shown in the query as `SELECT * FROM log_in_attempts`. 
## **Retrieve login attempts on specific dates**
To retrieve all the login attempts on 2022-05-09, and 2022-05-08, ```SELECT * FROM log_in_attempts WHERE login_date = ‘2022-05-09’ AND login_date = ‘2022-05-08’;``` was the input query. This query provides the login attempts that occurred on those dates, which are represented in the query as `WHERE login_dates = ‘2022-05-09’ AND login_date = ‘2022-05-08’;`. From the log_in_attempts table presented as `SELECT * FROM log_in_attempts`
## **Retrieve login attempts outside of Mexico**
To retrieve login attempts outside of Mexico, the query written is ```SELECT * FROM log_in_attempts WHERE NOT country LIKE ‘MEX%’;```. This query has 3 filters `WHERE`, `NOT`, and `LIKE`. `WHERE` specifies what is being filtered, `Not` tells the system to remove Mexico from the countries present in the data, and `LIKE` is used to find all the countries that start with ‘MEX’, with the percentage sign added after MEX. 
## **Retrieve employees in Marketing**
The query used to retrieve who works in the marketing department from the east building  is as follows ```SELECT * FROM employees WHERE department = ‘Marketing’ AND office LIKE ‘EAST%’;```. This query provides all the data of the employees from the employees table who are in the marketing department from the east building by using the `AND` filter, and the `LIKE` filter with `WHERE`.
## **Retrieve employees in Finance or Sales**
To get the data of the employees who work in the Finance or sales departments, the query  is written like this `SELECT * FROM employees WHERE department = ‘Finance’ OR department = ‘Sales’;`. With this query you could get both employees by using the `OR` Filter with the `WHERE` filter as stated in ``WHERE department = ‘Finance’ OR department = ‘Sales’;``. 
## **Retrieve all employees not in IT**
```SELECT * FROM employees WHERE NOT department = ‘IT’;``` is the query used to extract the data of all the employees who don’t work in the IT department by including the `NOT` filter with the `WHERE` filter. 
## **Summary**
With SQL I was able to get all login attempts that  happened after work hours, and on specific days. I was able to retrieve the data of all the employees who worked in the marketing department in the east building, and the employees who worked in finance and sales. 
