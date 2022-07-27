# Projec-sqlPractice
Sql-practice-06
---
Create table customers

```Sql
CREATE TABLE products
(
    code         INTEGER  NOT NULL PRIMARY KEY,
    name         CHAR(50) NOT NULL,
    price        REAL     NOT NULL,
    manufacturer INTEGER  NOT NULL
        CONSTRAINT fk_manufacturers_code
            REFERENCES manufacturers
);

CREATE TABLE manufacturers
(
    code INTEGER  NOT NULL PRIMARY KEY,
    name CHAR(50) NOT NULL
);
```
---
Adding information
```sql
INSERT INTO products (code, name, price, manufacturer)
VALUES (1, 'Hard drive', 240, 5),
       (2, 'Memory', 120, 6),
       (3, 'ZIP drive', 150, 4),
       (4, 'Floppy disk', 5, 6),
       (5, 'Monitor', 240, 1),
       (6, 'DVD drive', 180, 2),
       (7, 'CD drive', 90, 2),
       (8, 'Printer', 270, 3),
       (9, 'Toner cartridge', 66, 3),
       (10, 'DVD burner', 180, 2);


INSERT INTO manufacturers (code, name)
VALUES (1, 'Sony'),
       (2, 'Creative Labs'),
       (3, 'Hewlett-Packard'),
       (4, 'Iomega'),
       (5, 'Fujitsu'),
       (6, 'Winchester');
```
---
Task
1. Select the names of all the products in the store.

2. Select the names and the prices of all the products in the store.

3. Select the name of the products with a price less than or equal to $200.

4. Select all the products with a price between $60 and $120.

5. Select the name and price in cents (i.e., the price must be multiplied by 100).

6. Compute the average price of all the products.

7. Compute the average price of all products with manufacturer code equal to 2.

8. Compute the number of products with a price larger than or equal to $180.

9. Select the name and price of all products with a price larger than or equal to $180, and sort first by price (in descending order), and then by name (in ascending order).

10. Select all the data from the products, including all the data for each product's manufacturer.

11. Select the product name, price, and manufacturer name of all the products.

12. Select the average price of each manufacturer's products, showing only the manufacturer's code.

13. Select the average price of each manufacturer's products, showing the manufacturer's name.

14. Select the names of manufacturer whose products have an average price larger than or equal to $150.

15. Select the name and price of the cheapest product.

16. Select the name of each manufacturer along with the name and price of its most expensive product.

17. Select the name of each manufacturer which have an average price above $145 and contain at least 2 different products.

18. Add a new product: Loudspeakers, $70, manufacturer 2.

19. Update the name of product 8 to "Laser Printer".

20. Apply a 10% discount to all products.

21. Apply a 10% discount to all products with a price larger than or equal to $120.

---

Requests
```sql
1. SELECT name FROM products

2. SELECT name,price FROM products

3. SELECT * FROM products WHERE price <= 200

4. SELECT * FROM products WHERE price BETWEEN 60 AND 120

5. SELECT name,price * 100 FROM products

6. SELECT AVG(price) FROM products

7. SELECT AVG(price) FROM products WHERE code = 2;

8. SELECT * FROM products WHERE price >= 180;

9. SELECT name, price FROM products WHERE price>=180 ORDER BY price DESC, name;

10. SELECT * FROM products FULL JOIN manufacturers ON products.manufacturer = manufacturers.code

11. SELECT p.name, p.price, Manufacturer.name FROM products p INNER JOIN manufacturers m on p.manufacturer = m.code

12. SELECT AVG(price),manufacturer FROM products GROUP BY manufacturer

13. SELECT AVG(price),name FROM products GROUP BY name

14. SELECT AVG(price), m.name FROM products p INNER JOIN manufacturers m ON p.manufacturer = m.code GROUP BY m.name;

15. SELECT name,price FROM products ORDER BY price

16. SELECT p.name, p.price, m.name FROM manufacturers m INNER JOIN products p on m.code = p.manufacturer ORDER BY price DESC

17. SELECT m.name FROM manufacturers m INNER JOIN products p on m.code = p.manufacturer GROUP BY m.name HAVING AVG(p.price) >=145 AND COUNT(m.name)>=2

18. INSERT INTO products (code, name, price, manufacturer) VALUES (11, 'Loudspeakers', 70, 2)

19. UPDATE products SET name='Laser Printer' WHERE code = 8;

20. UPDATE products SET price = (price * 0.10) WHERE price > 1

21. UPDATE products SET price= (price * 0.1) WHERE price >= 120;
```
