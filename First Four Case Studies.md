# Brief Overview
Thee 4 files contain 4 different situations, one for a hospital, one for a car rental system, one for a hostel allocation and one for a library. The objective of these 4 case studies is to make sure that data is properly organised to ensure the smooth flow of each of these organisations.

# Library Management System - 1
This project aims to develop a Library Management System for college libraries that stores information about books, members, and transactions in order to automate lending activities, avoid manual record-keeping, and generate reports on issued books and due dates.

# Table 1 - Book
This table contains all details pertaining to the books.
-'Book_ID (Primary Key)
- 'Title'
- 'Author'
- 'Publisher'
- 'ISBN'
- 'Category'
- 'Copies_Available'

# Table 2 - Member
This table pertains to the holders of the library card, i.e. the members. 
-'Member_ID' (Primary Key)
-'Name 
-'Department'
-'Membership_Date'
-'Contact'

# Table 3 - Transaction
This table pertains to every book that is borrowed from the library.
-'Transaction_ID'
-'Book_ID'(Foreign Key to Book)
-'Member_ID'(Foreign Key to Member)
-'Issue_Date' 
-'Return_Date' 
-'Fine'

# Queries
Here, we want the number of times books have been borrowed, name of the borrower, title of the book and fine(if any), a combined table of Member and Transaction and, finally one for Book and Transaction. Queries are given below :- 

```sql

select count(*) from TRANSACTION where Fine > 0;

select MEMBER.Name, BOOK.Title, Transaction.Fine from TRANSACTION inner join BOOK on TRANSACTION.Book_ID = BOOK.Book_ID inner join MEMBER on TRANSACTION.Member_ID = MEMBER.MEMBER_ID;

select * from MEMBER inner join TRANSACTION on TRANSACTION.Member_ID = MEMBER.Member_ID;

select * from BOOK inner join TRANSACTION on TRANSACTION.Book_ID = BOOK.Book_ID where TRANSACTION.Fine > 0;



