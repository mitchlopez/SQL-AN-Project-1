# SQL Day 1 Answers

## Instructions

## **Table - person**

### Create a table called person that records a person's id, name, age, height ( in cm ), city, favorite_color.

#### id should be an auto-incrementing id/primary key - Use type: SERIAL

```sql
CREATE TABLE person (id SERIAL PRIMARY KEY, name VARCHAR(100), age INTEGER, height INTEGER, city VARCHAR(100), favorite_color VARCHAR(50))
```

### Add 5 different people into the person database.

#### Remember to not include the person_id because it should auto-increment.

```sql
INSERT INTO person (name, age, height, city, favorite_color)
VALUES ('Charlie', 27, 168, 'Orlando', 'Blue'),
('Matt', 23, 174, 'Dublin', 'Red'),
('John', 63, 181, 'Boston', 'Gold'),
('Betty', 9, 142, 'Tacoma', 'Pink'),
('Sue', 23, 159, 'San Antonio', 'Black')
```

### List all the people in the person table by height from tallest to shortest.

```sql
SELECT * FROM person
ORDER BY height DESC
```

### List all the people in the person table by height from shortest to tallest.

```sql
SELECT * FROM person
ORDER BY height
```

### List all the people in the person table by age from oldest to youngest.

```sql
SELECT * FROM person
ORDER BY age DESC
```

### List all the people in the person table older than age 20.

```sql
SELECT * FROM person
WHERE age > 20
```

### List all the people in the person table that are exactly 18.

```sql
SELECT * FROM person
WHERE age = 18
```

### List all the people in the person table that are less than 20 and older than 30.

```sql
SELECT * FROM person
WHERE age < 20 OR age > 30
```

### List all the people in the person table that are not 27 (Use not equals).

```sql
SELECT * FROM person
WHERE age != 27
```

### List all the people in the person table where their favorite color is not red.

```sql
SELECT * FROM person
WHERE favorite_color != 'Red'
```

### List all the people in the person table where their favorite color is not red and is not blue.

```sql
SELECT * FROM person
WHERE favorite_color != 'Red' AND favorite_color != 'Blue'
```

### List all the people in the person table where their favorite color is orange or green.

```sql
SELECT * FROM person
WHERE favorite_color = 'Orange' OR favorite_color != 'GREEN'
```

### List all the people in the person table where their favorite color is orange, green or blue (use IN).

```sql
SELECT * FROM person
WHERE favorite_color IN('Orange', 'Green', 'Blue')
```

### List all the people in the person table where their favorite color is yellow or purple (use IN).

```sql
SELECT * FROM person
WHERE favorite_color IN('Yellow', 'Purple')
```

## \*\*Table - orders

## Instructions

### Create a table called orders that records: order_id, person_id, product_name, product_price, quantity.

```sql
CREATE TABLE order (person_id INTEGER, order_id INTEGER, quantity INTEGER, product_price NUMERIC, product_name VARCHAR(50))
```

### Add 5 orders to the orders table.

### Make orders for at least two different people.

### person_id should be different for different people.

```sql
INSERT INTO orders (person_id, order_id, quantity, product_price, product_name)
VALUES (1, 6, 1, 5.99, 'Breakfast Burrito'),
(2, 7, 3, 1.65, 'Chicken Tacos')
(3, 8, 3, 1.75, 'Carne Asada Tacos')
(4, 9, 1, 6.37, 'Nacho Supreme')
(5, 10, 2, 2.49, 'Quesadilla')
```

### Select all the records from the orders table.

```sql
SELECT * FROM orders
```

### Calculate the total number of products ordered.

```sql
SELECT SUM(quantity) FROM orders;
```

### Calculate the total order price.

```sql
SELECT SUM(product_price * quantity) FROM orders;
```

### Calculate the total order price by a single person_id.

```sql
SELECT SUM(product_price * quantity) FROM orders WHERE person_id =2
```

## **Table - artist**

## Instructions

### Add 3 new artists to the artist table. ( It's already created )

```sql
INSERT INTO artist ( name ) VALUES ( 'Tame Impala' );
INSERT INTO artist ( name ) VALUES ( 'Swimming Tapes' );
INSERT INTO artist ( name ) VALUES ( 'Broken Bells' );

```

### Select 10 artists in reverse alphabetical order.

```sql
SELECT * FROM artist ORDER BY name DESC LIMIT 10;

```

### Select 5 artists in alphabetical order.

```sql
SELECT * FROM artist ORDER BY name ASC LIMIT 5;
```

### Select all artists that start with the word 'Black'.

```sql
SELECT * FROM artist WHERE name LIKE 'Black%';
```

### Select all artists that contain the word 'Black'.

```sql
SELECT * FROM artist WHERE name LIKE '%Black%';
```

## **Table - employee**

## Instructions

### 1. List all employee first and last names only that live in Calgary.

```sql
SELECT first_name, last_name FROM employee WHERE city = 'Calgary';
```

### 2. Find the birthdate for the youngest employee.

```sql
SELECT MAX(birth_date) from employee;
```

### 3. Find the birthdate for the oldest employee.

```sql
SELECT MIN(birth_date) from employee;
```

### 4. Find everyone that reports to Nancy Edwards (Use the ReportsTo column). You will need to query the employee table to find the Id for Nancy Edwards

```sql
SELECT * FROM employee WHERE reports_to = 2;
```

### 5. Count how many people live in Lethbridge.

```sql
SELECT COUNT(*) FROM employee WHERE city = 'Lethbridge';
```

## **Table - invoice**

## Instructions

### 1. Count how many orders were made from the USA.

```sql
SELECT COUNT(*) FROM invoice WHERE billing_country = 'USA';
```

### 2. Find the largest order total amount.

```sql
SELECT MAX(total) FROM invoice;
```

### 3. Find the smallest order total amount.

```sql
SELECT MIN(total) FROM invoice;
```

### 4. Find all orders bigger than \$5.

```sql
SELECT * FROM invoice WHERE total > 5;
```

### 5. Count how many orders were smaller than \$5.

```sql
SELECT COUNT(*) FROM invoice WHERE total < 5;
```

### 6. Count how many orders were in CA, TX, or AZ (use IN).

```sql
SELECT COUNT(*) FROM invoice WHERE billing_state in ('CA', 'TX', 'AZ');
```

### 7. Get the average total of the orders.

```sql
SELECT AVG(total) FROM invoice;
```

### 8. Get the total sum of the orders.

```sql
SELECT SUM(total) FROM invoice;
```
