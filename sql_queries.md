# SQL Queries

**Overview:**
1. CREATING tables and filling it with correct data;
2. SELECTING to check if everything OK;
3. JOIN tables.

To properly see the power of INNER/LEFT/RIGHT JOINS it is better to use data that could be represented in two sets with fractions intersecting:

<img src="images/intersection.png" title="Sets intersection" height="300"/>

On the image above we can clearly see what result of SQL JOINS will look like:
- The dark area of intersection is the result of INNER JOIN
- The dark plus green area represents the result of LEFT JOIN
- The dark plus purple area represents the result of RIGHT JOIN

I chose to use: 1) the collection of phone numbers connected the company it is operated by; 2) the collection of people's ID where not everyone has a phone number.

## 1. Creating database

    CREATE DATABASE phones;
    USE phones;
    
    CREATE table info(
    -> id INT(10) NOT NULL,
    -> phone_number BIGINT NULL,                                            // Phone number row
    -> operator VARCHAR(55) NULL,                                           // Operator's name row
    -> PRIMARY KEY (id)
    -> );
    
    CREATE table accounts(
    -> id INT(10) NOT NULL,
    -> name VARCHAR(25) NULL,                                               // First name
    -> surname VARCHAR(25) NULL,                                            // Last name
    -> phone_number BIGINT NULL,                                            // Phone number
    -> PRIMARY KEY (id)
    -> );

I filled the tables with this data:

![Filled](images/filled_tables.png)
