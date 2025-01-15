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

  









        
