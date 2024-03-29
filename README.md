# DBMS-LAB

Syllabus

1. Design a database schema for an application with ER diagram from a problem description**.
2. Creation, modification, configuration, and deletion of databases using UI and SQL Commands **.
3. Creation of database schema - DDL (create tables, set constraints, enforce relationships, create indices, delete and modify tables). Export ER diagram from the database and verify relationships** (with the ER diagram designed in step 1).
4. Database initialization - Data insert, Data import to a database (bulk import using UI and SQL Commands)**.
5. Practice SQL commands for DML (insertion, updating, altering, deletion of data, and viewing/querying records based on condition in databases)**.
6. Implementation of built-in functions in RDBMS**.
7. Implementation of various aggregate functions in SQL**.
8. Implementation of Order By, Group By & Having clause **.
9. Implementation of set operators nested queries, and join queries **.
10. Implementation of queries using temp tables.
11. Practice of SQL TCL commands like Rollback, Commit, Savepoint **.
12. Practice of SQL DCL commands for granting and revoking user privileges **.
13. Practice of SQL commands for creation of views and assertions ** .
14. Implementation of various control structures like IF-THEN, IF-THEN-ELSE, IF-THEN-ELSIF, CASE, WHILE using PL/SQL **.
15. Creation of Procedures, Triggers and Functions**.
16. Creation of Packages **.
17. Creation of Cursors **.
18. Creation of PL/SQL blocks for exception handling **.
19. Database backup and restore using commands.
20. Query analysis using Query Plan/Show Plan.
21. Familiarization of NoSQL Databases and CRUD operations**.
22. Design a database application using any front end tool for any problem selected. The
application constructed should have five or more tables**.
** mandatory

# Practice Questions

Design a normalized database schema for the following requirement.

### The requirement: A library wants to maintain the record of books, members, book issue, book
return, and fines collected for late returns, in a database. The database can be loaded with book
information. Students can register with the library to be a member. Books can be issued to
students with a valid library membership. A student can keep an issued book with him/her for a
maximum period of two weeks from the date of issue, beyond which a fine will be charged. Fine
is calculated based on the delay in days of return. For 0-7 days: Rs 10, For 7 – 30 days: Rs 100,
and for days above 30 days: Rs 10 will be charged per day.

### Sample Database Design
BOOK (Book_Id, Title, Language_Id, MRP, Publisher_Id, Published_Date, Volume, Status) // Language_Id, Publisher_Id are FK (Foreign Key)

AUTHOR(Author_Id, Name, Email, Phone_Number, Status)

BOOK_AUTHOR(Book_Id, Author_Id) // many-to-many relationship, both columns are PKFK
(Primary Key and Foreign Key)

PUBLISHER(Publisher_id, Name, Address)

MEMBER(Member_Id, Name, Branch_Code, Roll_Number, Phone_Number, Email_Id, Date_of_Join, Status)

BOOK_ISSUE(Issue_Id, Date_Of_Issue, Book_Id, Member_Id, Expected_Date_Of_Return, Status) // Book+Id and Member_Id are FKs

BOOK_RETURN(Issue_Id, Actual_Date_Of_Return, LateDays, LateFee) // Issue_Id is PK and FK

LANGUAGE(Language_id, Name) //Static Table for storing permanent data

LATE_FEE_RULE(FromDays, ToDays, Amount) // Composite Key

## EXERCISES
1. Create a normalized database design with proper tables, columns, column types, and
constraints
2. Create an ER diagram for the above database design.
3. Write SQL commands to
  a. Create a database by name Library. Drop the database and re-create it.
  b. Create DDL statements and create the tables and constraints (from the design) in the database created in step-a (Library)
  Notes: [ Create a script file and execute it. Create the script file in such a way that,,if the table exists, drop the tables and recreate )]
  c. Create and execute DROP TABLE command in tables with and without FOREIGN KEY constraints.
  d. Create and execute ALTER TABLE command in tables with data and without data.
  e. Create and execute SQL commands to build indices on Member_Id and Book_Id on table Book_Issue.
  f. Create and execute GRANT/REVOKE commands on tables.
  g. Create and execute SQL commands to insert data into each of the tables designed
  h. Learn and execute bulk import of data to tables from CSV files (insert 1000 records of books into the BOOK table from a CSV file).
  i. Create and execute UPDATE/DELETE commands on tables. Try to update/delete rows with Primary and Foreign Keys. Try bulk updates or deletes using SQL UPDATE statement

4. Write SQLQuery to retrieve the following information
  a. Get the number of books written by a given author
  b. Get the list of publishers and the number of books published by each publisher
  c. Get the names of authors who jointly wrote more than one book.
  d. Get the list of books that are issued but not returned
  e. Get the list of students who reads only ‘Malayalam’ books
  f. Get the total fine collected for the current month and current quarter
  g. Get the list of students who have overdue (not returned the books even on due date)
  h. Calculate the fine (as of today) to be collected from each overdue book.
  i. Members who joined after Jan 1 2021 but has not taken any books

5. Book return should insert an entry into the Book_Return table and also update the status in
Book_Issue table as ‘Returned’. Create a database TRANSACTION to do this operation
(stored procedure).

6. Create a database view ‘Available_Books’, which will list out books that are currently
available in the library

7. Create a database procedure to add, update and delete a book to the Library database (use parameters).

8. Use cursors and create a procedure to print Books Issue Register (page wise – 20 rows in a page)

9. Create a history table (you may use the same structure without any keys) for the MEMBER table and copy the original values of the row being updated to the history table using a TRIGGER.

10. NoSQL Exercise
  a. Practice Mongo DB CRUD operations. Refer: https://docs.mongodb.com/manual/crud/
  b. You may use a MongoDB local installation or cloud MongoDB services like MongoDB Atlas for this exercise
  c. For documentation: Refer: https://docs.mongodb.com/manual/introduction/

11.Application Development Problem examples:
1) Inventory Control System.
2) Material Requirement Processing.
3) Hospital Management System.
4) Railway Reservation System.
5) Personal Information System.
6) Web Based User Identification System.
7) Timetable Management System.
8) Hotel Management System.
