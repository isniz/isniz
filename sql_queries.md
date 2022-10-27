# SQL Queries

**Overview:**
1. CREATING tables and filling it with correct data;
2. SELECTING to check if everything OK;
3. JOIN tables.

To properly see the power of INNER/LEFT/RIGHT JOINS it is better to use the tables with empty values in some columns.
I chose to use the field of countries and its capitals.
Possible empty values will be in these columns:
- National currency (not every country has it)
- Original official language (for example, Austrians speak German, not "Austrian")
- Capital city (not every country has it)
- City's official website (not every city has it)

## 1. Creating database

    CREATE database capitals;
    USE capitals;
    CREATE table countries(
    -> id INT(10) NOT NULL,                                         // ID column
    -> name VARCHAR(25) NULL,                                       // Country name column
    -> area INT(20) NULL,                                           // Country area column
    -> currency VARCHAR(25) NULL,                                   // Country's national currency column
    -> language VARCHAR(25) NULL                                    // Country's original official language column
    -> PRIMARY KEY (id)
    -> );
    
    CREATE table cities(
    -> id INT(10) NOT NULL,
    -> name VARCHAR(25) NULL,
    -> area INT(20) NULL,
    -> country INT(10) NOT NULL,
    -> website VARCHAR(50) NULL,
    -> PRIMARY KEY (id),
    -> FOREIGN KEY (country) REFERENCES countries(id)
    -> );
