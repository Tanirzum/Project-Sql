# Project-sqlDrink_info
Sql-practice-02
---
Create table drink_info
```Sql
CREATE TABLE drink_info
(
    name     VARCHAR(30) NOT NULL,
    cost     DECIMAL     NOT NULL,
    carbs    DECIMAL     NOT NULL,
    color    VARCHAR(20) NOT NULL,
    ice      VARCHAR(20) NOT NULL,
    calories INTEGER     NOT NULL
);
```
---
Adding information
```sql
INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Терновик', 3, 8.4, 'желтый', 'Д', 33)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Голубая луна',2.5,3.2,'синий','Д',12)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Вот тебе на',3.5,8.6,'оранжевый','Д',35)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Лаймовый физз',2.5,5.4,'зеленый','Д',24)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Лаймовый физз',2.5,5.4,'зеленый','Д',24)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Поцелуй',5.5,42.5,'фиолетовый','Д',171)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Горячее золото',3.2,32.1,'оранжевый','Н',135)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Одинокое дерево',3.6,4.2,'красный','Д',17)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Борзая',4,14,'желтый','Д',50)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Бабье лето',2.8,7.2,'коричневый','Н',30)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Лягушка',2.6,21.5,'бронзовый','Д',80)

INSERT INTO drink_info (name, cost, carbs, color, ice, calories)
VALUES ('Сода плюс',3.8,4.7,'красный','Н',19)
```
---
Requests
```Sql
SELECT * FROM drink_info WHERE cost BETWEEN 4 AND 5;

SELECT * FROM drink_info WHERE name like 'О%';

SELECT * FROM drink_info WHERE calories > 30 AND calories < 60;

SELECT * FROM drink_info WHERE name = 'Терновик' OR color = 'Желтый';

SELECT * FROM drink_info WHERE NOT name = 'Лягушка' AND calories > 50;

SELECT * FROM drink_info WHERE NOT name = 'Поцелуй' AND calories BETWEEN 10 AND 20;

SELECT * FROM drink_info WHERE color IN ('желтый','красный','синий','белый','серый');

SELECT * FROM drink_info WHERE color NOT IN ('желтый','красный','синий','белый','серый');

SELECT * FROM drink_info WHERE calories NOT BETWEEN 30 AND 50;

SELECT * FROM drink_info WHERE calories NOT LIKE 'О%'

SELECT * FROM drink_info WHERE name NOT LIKE 'О%'
```
