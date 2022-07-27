Sql-practice-05
---
Create table customers

```Sql
CREATE TABLE runtime_developers
(
    id SERIAL NOT NULL PRIMARY KEY,
    name VARCHAR(25) NOT NULL,
    last_name VARCHAR(25) NOT NULL,
    job VARCHAR(50) NOT NULL,
    salary DECIMAL NOT NULL 
)
```
---
Adding information
```sql
INSERT INTO runtime_developers (name, last_name, job, salary) 
VALUES ('Tanirbergen','Zamanbek','Java developer',1.455)

INSERT INTO runtime_developers (name, last_name, job, salary) 
VALUES ('Sayan','Amanbekov','IOS developer',3.246)

INSERT INTO runtime_developers (name, last_name, job, salary)
VALUES('Ayan','Armanov','GO developer',2.546)

INSERT INTO runtime_developers (name, last_name, job, salary)
VALUES ('Bekzat','Bazarbai','Front-end developer',1.656)

INSERT INTO runtime_developers (name, last_name, job, salary)
VALUES ('Jaras','Alibekov','Java developer',4.156)

INSERT INTO runtime_developers (name, last_name, job, salary)
VALUES ('Sultan','Esentaev','Python developer',3.956)

INSERT INTO runtime_developers (name, last_name, job, salary)
VALUES ('Damir','Esenov','Scala developer',1.156)
```
---
Requests
```Sql
UPDATE runtime_developers SET job = 'Java developer' WHERE name = 'Ayan';

DELETE FROM runtime_developers WHERE name = 'Sultan';

UPDATE runtime_developers SET job='Full-Stack developer' WHERE name='Bekzat';

ALTER TABLE runtime_developers ADD COLUMN emaill VARCHAR(50)

UPDATE runtime_developers SET emaill = 'tanirbergen.zamanbeu@bk.ru' WHERE name='Tanirbergen';

UPDATE runtime_developers SET emaill = 'Sayan@mail.ru' WHERE name='Sayan';

SELECT * FROM runtime_developers WHERE name LIKE 'B%t' AND job = 'Front-end developer';

DELETE FROM runtime_developers WHERE job = 'Java developer';

SELECT id, name FROM runtime_developers WHERE emaill IS NULL

ALTER TABLE runtime_developers RENAME emaill TO email

ALTER TABLE runtime_developers DROP COLUMN email

```
