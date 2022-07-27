# Project-sqlDevelopers
Sql-practice-01
---
Create table Developers
```Sql
CREATE TABLE developers
(
    id         INTEGER,
    name       VARCHAR(30),
    job        VARCHAR(40),
    age        INTEGER,
    salary     DECIMAL,
    start_work DATE
);
```
---
Adding information
```sql
INSERT INTO developers (id, name, job, age, salary, start_work)
VALUES(1,'Vasya','IOS developer',27,2950.45,'2015-04-18')

INSERT INTO developers (id, name, job, age, salary, start_work)
VALUES(2,'Alexander','Java developer',26,4950.11,'2012-01-24')

INSERT INTO developers (id, name, job, age, salary, start_work)
VALUES(3,'Fedor','Frontend developer',53,7520.11,'2008-05-10')

INSERT INTO developers (id, name, job, age, salary, start_work)
VALUES(4,'Anuar','Java developer',33,3580.89,'2015-02-04')

INSERT INTO developers (id, name, job, age, salary, start_work)
VALUES(5,'Alexey','Java developer',30,3520.24,'2010-02-02')

INSERT INTO developers (id, name, job, age, salary, start_work)
VALUES (6,'Anton','Java developer',26,3000.01,'2017-02-06')

INSERT INTO developers (id, name, job, age, salary, start_work)
VALUES (7, 'Ilyas', 'Android developer', 18, '2023-02-08')

INSERT INTO developers (id, name, job, age, salary, start_work)
VALUES (8, 'Vladimir', 'Php developer', 18, '2023-01-02')
)
```
---
Requests
```Sql
SELECT * FROM developers WHERE job = 'Java developer' AND salary > 3000;

SELECT name, age FROM developers ORDER BY age DESC;

SELECT * FROM developers WHERE job = 'IOS developer' OR job = 'Java developer';

SELECT * FROM developers WHERE start_work >= '2012-12-31';

SELECT * FROM developers ORDER BY name ASC, age DESC;

SELECT * FROM developers WHERE age < 35;

SELECT * FROM developers WHERE NOT job = 'IOS developer';

SELECT * FROM developers WHERE salary IS NULL;

SELECT MIN(age) AS smallestAge FROM developers;

SELECT * FROM developers WHERE salary IS NOT NULL;

SELECT COUNT(id) FROM developers WHERE job = 'Frontend developer';

SELECT AVG(salary) FROM developers WHERE job = 'Java developer';
```
