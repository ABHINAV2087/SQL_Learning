```sql
-- Show Databases and Use Specific Database
SHOW DATABASES;
USE abhinav;

-- Show Tables in the Database
SHOW TABLES;

-- Create Table for Courses
CREATE TABLE Course(
  CourseID INT AUTO_INCREMENT,
  CourseName varchar(50) NOT NULL,
  CourseDuration_Months INT NOT NULL,
  CourseFee INT NOT NULL,
  PRIMARY KEY(CourseID)
);

-- Describe the Course Table
DESC Course;

-- Insert Data into the Course Table
INSERT INTO Course(CourseName,CourseDuration_Months,CourseFee) 
VALUES 
  ("The Complete Excel Mastery Course",3,1499),
  ("DSA For Interview Preparation",2,4999),
  ("SQL Bootcamp",1,2999);

-- Select All Data from the Course Table
SELECT * FROM Course;

-- Create Table for Learners
CREATE TABLE Learners(
  LearnerId INT AUTO_INCREMENT,
  LearnerFirstname VARCHAR(50) NOT NULL,
  LearnerLastname VARCHAR(50) NOT NULL,
  LearnerEmail VARCHAR(50),
  LearnerPhoneno VARCHAR(10) NOT NULL,
  LearnerEnrollmentDate TIMESTAMP NOT NULL,
  SelectedCourse INT NOT NULL,
  YearOfExperience INT NOT NULL,
  LearnerCompany VARCHAR(50),
  SourceOfJoining VARCHAR(50) NOT NULL,
  BatchStartDate TIMESTAMP NOT NULL,
  Location VARCHAR(50) NOT NULL,
  PRIMARY KEY(LearnerID),
  UNIQUE key(LearnerEmail),
  FOREIGN KEY(SelectedCourse) REFERENCES Course(CourseId)
);

-- Describe the Learners Table
DESC Learners;

-- Insert Data into the Learners Table
INSERT INTO Learners (LearnerFirstname, LearnerLastname, LearnerPhoneno, LearnerEmail, LearnerEnrollmentDate, SelectedCourse, YearOfExperience, LearnerCompany, SourceOfJoining, BatchStartDate, Location) 
VALUES 
  ("Akash", "Mishra", "9998887776", "akash@gmail.com", '2024-01-21', 1, 4, "Amazon", "LinkedIn", '2024-02-29', "Bengaluru"),
  ("Rishikesh", "Joshi", "9950192388", "carjkop@gmail.com", '2024-03-19', 3, 2, "HCL", "Youtube", '2024-03-25', "Chennai"),
  ("Jeevan", "Hegde", "9657856732", "jeevanhegdek@yahoo.co.in", '2024-01-15', 2, 0, NULL, "Linkedin", '2024-01-16', "Noida"),
  ("Akhil", "George", "7689558930", "akhil.george.8743@gmail.com", '2024-03-13', 3, 4, "Accenture", "Community", '2024-03-25', "Bengaluru"),
  ("Sidhish", "Kumar", "6475765443", "sidhishkumar@gmail.com", '2024-01-10', 1, 4, "Meta", "Youtube", '2024-02-29', "Bengaluru"),
  ("NagaSai", "Sreedhar", "9182937061", "saisreedhar2001@gmail.com", '2024-03-17', 3, 4, "TCS", "Community", '2024-03-25', "Mumbai");

-- Select All Data from the Learners Table
SELECT * FROM Learners;

-- Data Analysis[Employee,Course,Learners]

-- 1. Give me the record of the employee getting the highest salary
SELECT * FROM employee
ORDER BY Salary DESC LIMIT 1;

SELECT MAX(Salary) as max_salary FROM employee;
SELECT MIN(Salary) as min_salary FROM employee;

SELECT * FROM employee
WHERE Salary = (SELECT MAX(Salary) FROM employee);

-- 2. Give me the record of the employee getting the highest salary and age is bigger than 23
SELECT * FROM employee WHERE Age >23 ORDER BY Salary DESC LIMIT 1;

-- 3. Display the number of enrollments on the website
SELECT COUNT(*) as num_of_enrollments FROM Learners;

-- 4. Display the number of enrollments for the courseid = 3[SQL BOOTCAMP]
SELECT COUNT(LearnerId) AS num_of_learner_SQL FROM Learners WHERE SelectedCourse=3;

-- 5. Count the number of learners enrolled in the month of Jan
SELECT COUNT(*) FROM Learners WHERE LearnerEnrollmentDate Like '%-03-%';

SELECT * FROM Learners;

-- 6. Update the Jeevan data with years of experience as 1 and learner company as "Amazon"
UPDATE Learners SET YearOfExperience=2 , LearnerCompany = 'Amazon' WHERE  LearnerID = 3;

SELECT * FROM Learners;

-- 7. Count the number of companies where learners are currently doing their job
-- count -> not null entries are counted
-- Unique count of the companies
SELECT COUNT(DISTINCT LearnerCompany) as distinct_companies FROM Learners;


```