```sql
SHOW DATABASES ;
CREATE DATABASE abhinav 

USE abhinav ;

CREATE TABLE employee(
 EID  INT PRIMARY KEY AUTO_INCREMENT,
 FirstName varchar(50) NOT NULL,
 LastName varchar(50) NOT NULL,
 Age INT NOT NULL,
 Salary INT NOT NULL,
 Location varchar(50) NOT NULL
)

SHOW TABLES

DESC employee

INSERT INTO employee VALUES(2,'ABHI','TIROLE',21,1500000,'BHOPAL')

DESC employee

SELECT * FROM employee

DROP TABLE employee

INSERT INTO employee(FirstName,LastName,Age,Salary,Location) VALUES ('ABHINAV','TIROLE',21,1500000,'BENGALURU')
INSERT INTO employee(FirstName,LastName,Age,Salary,Location) VALUES ('ABC','XYZ',25,150000,'BHOPAL')
INSERT INTO employee(FirstName,LastName,Age,Salary,Location) VALUES ('ABC','XYZ',25,150000,'BHOPAL')
INSERT INTO employee(FirstName,LastName,Age,Salary,Location) VALUES ('DEF','LMO',22,200000,'INODRE')
INSERT INTO employee(FirstName,LastName,Age,Salary,Location) VALUES ('GHJ','YUI',25,15000,'BHOPAL')


## DATA RETREIVAL
-- give me the employee details having salary more than 1000000 --

SELECT * FROM employee where Salary > 1000000

SELECT FirstName,LastName FROM employee WHERE Salary > 1000000

## DATA UPDATION
-- update the LastName 

UPDATE employee SET LastName = "qwe" WHERE EID = 5


## DATA DELETION
-- delete user details

DELETE FROM employee WHERE EID = 4
```