# PostgreSQL
Repository to track my PostgreSQL learning journey

## PSQL commands

  To get help with SQL commands
      
    \h

  To get help with PSQL commands
    
    \?

  To quit
    
    \q

  To list all the databases

    \l

  To create a database

    CREATE DATABASE <DATABASE-NAME>;

  To connect to a database

    \c <DATABASE-NAME>

  To delete a database

    DROP DATABASE <DATABASE-NAME>;
    # Very dangerous command

  To create table

    CREATE TABLE table_name (
        Column name + data type + constraints if any
    )

    Ex: CREATE TABLE person (
            id INT,
            first_name VARCHAR(50),
            last_name VARCHAR(50),
            gender VARCHAR(6),
            date_of_birth TIMESTAMP,
        )

  To describe (list the tables, views and sequences)

    \d
  
  To describe the structure of a specific table

    \d <TABLE-NAME>

  To create a table with constraints

    Ex: CREATE TABLE person (
            id BIGSERIAL NOT NULL PRIMARY KEY,
            first_name VARCHAR(50) NOT NULL,
            last_name VARCHAR(50) NOT NULL,
            gender VARCHAR(6) NOT NULL,
            date_of_birth TIMESTAMP NOT NULL, 
            )

  To drop a table

    DROP TABLE <TABLE-NAME>

  To add a column

    ALTER TABLE <TABLE-NAME>
    ADD COLUMN <COLUMN-NAME> <DATA-TYPE> [CONSTRAINT];

  To clear

    \! cls

  To list all the tables

    \dt

  To insert values into the table

    Ex: INSERT INTO person (first_name, last_name, gender, date_of_birth, email)
          VALUES ('Jake', 'Jones', 'MALE', date '1990-12-31', 'jake@gmail.com');

  To get certain number of records

    Ex: SELECT * FROM person LIMIT 5;
          # Returns 5 records

  To set an offset (get records after a certain value)

    Ex: SELECT * FROM person OFFSET 5;
          # Skips first 5 records and then returns all the records after that

  SQL standard query - to get certain rows

    Ex: SELECT * FROM person FETCH FIRST 5 ROW ONLY;

  IN command

    Ex: SELECT * FROM person WHERE country IN ('China', 'Poland', 'France');

  BETWEEN command

    Ex: SELECT * FROM person WHERE date_of_birth between '2000-01-01' AND '2015-01-01';

  LIKE operator

    Ex: SELECT * FROM person WHERE email LIKE '%@gmail.com';

  ILIKE operator

    Ex: SELECT * FROM person WHERE country ILIKE 'p%';
          # ILIKE works same as LIKE Operator but ignores CASE-SENSITIVITY

  GROUP BY 

    Ex: SELECT country, COUNT(country) FROM person GROUP BY country;

  GROUP BY HAVING

    Ex: SELECT country, COUNT(country) FROM person GROUP BY country HAVING COUNT(*) > 5;

  Factorial

    Ex: SELECT factorial(5);

  ALIAS - Override the column name

    Ex: SELECT price AS original_price from car;

  COALESCE - To print the first NOT NULL VALUE

    Ex: SELECT COALESCE(email, 'Email Not Provided') from person;

  NULLIF - NULLIF takes two arguments, if num1 = num2 NULL is returned, else num1 is returned

    Ex: SELECT 10 / 0 # Throws an error
        SELECT 10 / NULL # Returns Null
        SELECT 10 / NULLIF(0,0) # Returns Null
        # You can use COALESCE and NULLIF to handle zero division error

  NOW() - To get the date, time, timestamp

    Ex: SELECT NOW(); #  2025-01-15 20:19:38.961026-05
        SELECT NOW()::DATE; # 2025-01-15 
        SELECT NOW()::TIME; # 20:19:38

  To add or subtract a time interval

    Ex: SELECT NOW() - INTERVAL '1 YEAR'; # 2024-01-15 20:19:38.961026-05
        SELECT NOW() - INTERVAL '1 DAY';  # 2025-01-14 20:19:38.961026-05
        SELECT NOW() + INTERVAL '3 MONTHS'; # 2025-04-15 20:19:38.961026-05
        SELECT (NOW() + INTERVAL '3 MONTHS')::DATE; # 2025-04-15
        
  To extract specific day or month or year

    Ex: SELECT EXTRACT(DAY FROM NOW()) # 15
        SELECT EXTRACT(DOW FROM NOW()) # 3 - WEDNESDAY
        SELECT EXTRACT(YEAR FROM NOW()) # 2025
        SELECT EXTRACT(MONTH FROM NOW()) # 1
        SELECT EXTRACT(CENTURY FROM NOW()) # 21 - 21st CENTURY

  AGE function

    Ex: SELECT AGE(NOW()::DATE, date_of_birth) AS age FROM person LIMIT 5;
          # CREATES A NEW COLUMN 'age' AND CALCULATES THE AGE, AND DISPLAYS THE FIRST 5 RECORDS

  

  

  

        

  

  

  









        
