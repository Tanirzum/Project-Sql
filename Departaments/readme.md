# Project-sqlPractice01
Sql-practice-07
---
Create table customers

```Sql
CREATE TABLE Departments
(
    Code   INTEGER PRIMARY KEY NOT NULL,
    Name   VARCHAR             NOT NULL,
    Budget REAL                NOT NULL
);

CREATE TABLE Employees
(
    SSN         INTEGER PRIMARY KEY NOT NULL,
    Name        TEXT                NOT NULL,
    LastName    VARCHAR             NOT NULL,
    Departament INTEGER             NOT NULL,
    CONSTRAINT fk_Departments_Code FOREIGN KEY (Departament)
        REFERENCES departments (code)
);
```
---
Adding information
```sql
INSERT INTO departments (code, name, budget)
VALUES (14, 'IT', 6500),
       (37, 'Accounting', 15000),
       (59, 'Human Resources', 240000),
       (77, 'Research', 5500)

INSERT INTO employees (ssn, name, lastname, departament)
VALUES ('123234877', 'Michael', 'Rogers', 14),
       ('152934485', 'Anand', 'Manikutty', 14),
       ('222364883', 'Carol', 'Smith', 37),
       ('326587417', 'Joe', 'Stevens', 37),
       ('332154719', 'Mary-Anne', 'Foster', 14),
       ('332569843', 'George', 'O', 'Donnell', 77),
       ('546523478', 'John', 'Doe', 59),
       ('631231482', 'David', 'Smith', 77),
       ('654873219', 'Zacary', 'Efron', 59),
       ('745685214', 'Eric', 'Goldsmith', 59),
       ('845657245', 'Elizabeth', 'Doe', 14),
       ('845657246', 'Kumar', 'Swamy', 14)
```
---
Task
1. Select the last name of all employees.

2. Select the last name of all employees, without duplicates.

3. Select all the data of employees whose last name is "Smith".

4. Select all the data of employees whose last name is "Smith" or "Doe".

5. Select all the data of employees that work in department 14.

6. Select all the data of employees that work in department 37 or department 77.

7. Select all the data of employees whose last name begins with an "S".

8. Select the sum of all the departments' budgets.

9. Select the number of employees in each department (you only need to show the department code and the number of employees).

10. Select all the data of employees, including each employee's department's data.

11. Select the name and last name of each employee, along with the name and budget of the employee's department.

12. Select the name and last name of employees working for departments with a budget greater than $60,000.

13. Select the departments with a budget larger than the average budget of all the departments.

14. Select the names of departments with more than two employees.

15. Select the name and last name of employees working for departments with second lowest budget.

16. Add a new department called "Quality Assurance", with a budget of $40,000 and departmental code 11. Add an employee called "Mary Moore" in that department, with SSN 847-21-9811.

17. Reduce the budget of all departments by 10%.

18. Reassign all employees from the Research department (code 77) to the IT department (code 14).

19. Delete from the table all employees in the IT department (code 14).

20. Delete from the table all employees who work in departments with a budget greater than or equal to $60,000.

21. Delete from the table all employees.
---

Requests
```sql
1. SELECT lastname FROM employees

2. SELECT DISTINCT lastname FROM employees

3. SELECT * FROM employees WHERE lastname = 'Smith';

4. SELECT * FROM employees WHERE lastname = 'Smith' OR lastname = 'Doe';

5. SELECT * FROM employees WHERE departament = 14;

6. SELECT * FROM employees WHERE departament BETWEEN 37 AND 77

7. SELECT * FROM employees WHERE name LIKE 'S%'

8. SELECT budget FROM departments

9. SELECT d.code, d.name FROM departments d INNER JOIN employees e on d.code = e.departament

10. SELECT * FROM departments d INNER JOIN employees e on d.code = e.departament

11. SELECT e.name, e.lastname, d.name, d.budget FROM employees e INNER JOIN departments d on d.code = e.departament

12. SELECT e.name, e.lastname FROM employees e INNER JOIN departments d on d.code = e.departament WHERE budget > 60000;

13. SELECT AVG(budget) FROM departments WHERE budget > 67000;

14. SELECT d.name FROM departments d INNER JOIN employees e on d.code = e.departament GROUP BY d.name HAVING count(d.name) > 2

15. SELECT e.name, e.lastname FROM employees e INNER JOIN departments d on e.departament = d.code WHERE budget < 60000

16. INSERT INTO departments (code, name, budget) VALUES (11, 'Quality Assurance', 40000)

    INSERT INTO employees (ssn, name, lastname, departament) VALUES (847-21-9811,'Mary','Moore',11)

17. UPDATE Departments SET Budget = (Budget * 0.9);

18. UPDATE employees SET departament = 14 WHERE departament = 77;

19. DELETE FROM employees WHERE departament = 14;

20. DELETE FROM employees WHERE departament = 59;

21. DELETE FROM Employees2;
```
