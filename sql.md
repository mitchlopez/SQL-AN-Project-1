# SQL Day 1 Answers

## Instructions

## Table - person

### Create a table called person that records a person's id, name, age, height ( in cm ), city, favorite_color.

#### id should be an auto-incrementing id/primary key - Use type: SERIAL

`CREATE TABLE person (id SERIAL PRIMARY KEY, name VARCHAR(100), age INTEGER, height INTEGER, city VARCHAR(100), favorite_color VARCHAR(50))`

### Add 5 different people into the person database.

#### Remember to not include the person_id because it should auto-increment.

```INSERT INTO person (name, age, height, city, favorite_color)
VALUES ('Charlie', 27, 168, 'Orlando', 'Blue'),
('Matt', 23, 174, 'Dublin', 'Red'),
('John', 63, 181, 'Boston', 'Gold'),
('Betty', 9, 142, 'Tacoma', 'Pink'),
('Sue', 23, 159, 'San Antonio', 'Black')
```

### List all the people in the person table by height from tallest to shortest.

```SELECT * FROM person
ORDER BY height DESC
```

### List all the people in the person table by height from shortest to tallest.

```SELECT * FROM person
ORDER BY height
```

### List all the people in the person table by age from oldest to youngest.

````SELECT * FROM person
ORDER BY age DESC ```

### List all the people in the person table older than age 20.

``` SELECT * FROM person
WHERE age > 20 ```

### List all the people in the person table that are exactly 18.

``` SELECT * FROM person
WHERE age = 18 ```

### List all the people in the person table that are less than 20 and older than 30.(Is this a typo?)

``` SELECT * FROM person
WHERE age < 20 AND age > 30```

### List all the people in the person table that are not 27 (Use not equals).

``` SELECT * FROM person
WHERE age != 27```

### List all the people in the person table where their favorite color is not red.

```SELECT * FROM person
WHERE favorite_color != 'Red' ```

### List all the people in the person table where their favorite color is not red and is not blue.

``` SELECT * FROM person
WHERE favorite_color != 'Red' AND favorite_color != 'Blue' ```

### List all the people in the person table where their favorite color is orange or green.

``` SELECT * FROM person
WHERE favorite_color = 'Orange' OR favorite_color != 'GREEN' ```

### List all the people in the person table where their favorite color is orange, green or blue (use IN).

``` SELECT * FROM person
WHERE favorite_color IN('Orange', 'Green', 'Blue') ```

### List all the people in the person table where their favorite color is yellow or purple (use IN).

``` SELECT * FROM person
WHERE favorite_color IN('Yellow', 'Purple') ```
````
