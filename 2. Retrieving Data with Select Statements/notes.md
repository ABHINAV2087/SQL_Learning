# Primary key and Foreign key

### **Primary Key**  
- A **primary key** is a unique identifier for each record in a database table.  
- It ensures that no two rows in a table can have the same value in the primary key column(s).  
- It **cannot contain NULL values** because every record must be uniquely identifiable.  

Example:  
In a **Student** table:  
| StudentID (Primary Key) | Name  | Age |  
|--------------------------|-------|-----|  
| 101                      | Alice | 21  |  
| 102                      | Bob   | 22  |  

Here, `StudentID` is the primary key because it uniquely identifies each student.

---
## Secondary key

A **secondary key** in a database is like a **shortcut** to search for data. It is not the main identifier (like a primary key) but helps you find information based on other attributes.

### Example:
Imagine a **student table**:

| **RollNo** (Primary Key) | **Name**  | **Class** | **City**       |
|---------------------------|-----------|-----------|----------------|
| 1                         | Ravi      | 10        | Mumbai         |
| 2                         | Priya     | 10        | Delhi          |
| 3                         | Arjun     | 11        | Mumbai         |

- **Primary Key**: `RollNo` (unique for each student).
- **Secondary Key**: `City` (used to find all students in a specific city, e.g., Mumbai).

The secondary key makes searching easier but doesn’t ensure unique values.

----

### **Foreign Key**  
- A **foreign key** is a column (or set of columns) in one table that links to the **primary key** in another table.  
- It creates a relationship between two tables.  
- It ensures **referential integrity**, meaning the data in the foreign key column must match an existing value in the referenced primary key column.

Example:  
In a **Course Enrollment** table:  
| EnrollmentID | StudentID (Foreign Key) | Course |  
|--------------|--------------------------|--------|  
| 1            | 101                      | Math   |  
| 2            | 102                      | Science|  

Here, `StudentID` is a foreign key in the **Course Enrollment** table and refers to `StudentID` in the **Student** table.  

This connection ensures that the `StudentID` in **Course Enrollment** must exist in the **Student** table.



______

# Primary key and Unique key


**Primary Key:**
- A **primary key** uniquely identifies each row in a table.
- It **cannot have null values**.
- A table can have only **one primary key**.

**Unique Key:**
- A **unique key** also ensures all values in a column are unique.
- It **can have one null value**.
- A table can have **multiple unique keys**. 


**Key Difference:**  

A **primary key** is mandatory and uniquely identifies records, while a **unique key** is optional and allows one null value.
