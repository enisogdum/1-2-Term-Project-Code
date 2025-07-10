Library Automation System
This project implements a small-scale, file-operation based Library Automation System focusing on the principles of relational databases. It is developed as a term project for the BLM1031 - Structural Programming course.

Table of Contents
Project Overview

Functional Requirements

Author Management

Student Management

Book Management

Book-Author Relationship Management

Student Book Lending/Returning

Program Menus

Student Operations

Book Operations

Author Operations

Coding Requirements

Project Reporting

Project Submission

Contact

Project Overview
The Library Automation System is designed to manage authors, students, books, and their relationships within a library environment. It utilizes file operations (specifically CSV files) and linked list data structures to store and manage information.

Functional Requirements
The system provides the following core functionalities:

Author Management
Add/Delete/Edit/List Authors:

Each author has a name, surname, and an automatically incrementing authorID (1, 2, ..., N).

Authors are stored in a Singly Linked List, sorted by authorID, and persisted in yazarlar.csv.

Information can be deleted or updated, with changes reflected in the CSV file.

Student Management
Add/Delete/Edit/List Students:

Each student has a name, surname, an initial library score of 100, and a unique 8-digit student number.

Student information is stored in a struct within a Doubly Linked List and persisted in Ogrenciler.csv.

Information can be deleted or updated, with changes reflected in the CSV file.

Book Management
Add/Delete/Edit/List Books:

Each book has a name, a 13-digit ISBN number, and a quantity.

For multiple copies of a book, each copy receives a unique tag number (e.g., ISBN_1, ISBN_2, ..., ISBN_N).

Books are stored in a Singly Linked List, sorted by name and then ISBN.

For each book, a separate Singly Linked List is created to store information about its copies, including the tag number and lending status.

The lending status indicates either "RAFTA" (on shelf) or the studentID of the borrowing student.

The relationship between books and their copies is modeled using singly linked lists as shown in Figure 1 (from the project document).

All book and copy data are stored consistently in CSV files.

Book-Author Relationship Management
Associate Books with Authors:

Handles cases where a book has multiple authors and an author has written multiple books.

BookISBN - AuthorID pairings are stored in KitapYazar.csv.

Data from this file is loaded into a dynamic STRUCT ARRAY of size N (number of lines in the file) and kept in memory while the program is running.

Note 1: If an author is deleted from the system, their authorID in KitapYazar.csv should be updated to -1.

Note 2: Operations on unregistered authors or books should be prevented, and warnings should be issued to maintain data integrity.

Student Book Lending/Returning
Lend/Return Books:

Manages consistent storage of lending and return information for multiple books by a student, and multiple students borrowing the same book at different times.

A CSV file and a corresponding struct are designed to store StudentID, BookTagNo, TransactionType (0 for lending, 1 for returning), and Date information (as shown in Figure 3 from the project document).

When a book is lent, its ShelfStatus in the book data structure and corresponding file (as explained in Book Management) must be updated from "RAFTA" to the StudentID.

Note 1: Operations on unregistered students or books should be prevented, and warnings should be issued. If a student's library score becomes negative, the lending operation should be cancelled with a warning.

Note 2: If a book is returned more than 15 days after being borrowed, the student receives a -10 penalty points, and their library score is updated accordingly.

Note 3: If all copies of a book are already lent out, a "TRANSACTION FAILED" warning should be issued.

Program Menus
The application provides the following menu options:

Student Operations
Add, Delete, Update Student: Perform CRUD operations on student information, updating both files and linked lists.

View Student Information: Display personal details (Name, Surname, ID, Score, etc.) and all book transaction history for a student, given their ID or Name-Surname.

List Students Who Have Not Returned Books:

List Penalized Students:

List All Students:

Borrow/Return Book:

Book Operations
Add, Delete, Update Book: Perform CRUD operations on book information, updating both files and linked lists.

View Book Information: List all details for a given book name, including information about its individual copies.

List Books on Shelf:

List Books Not Returned on Time:

Match Book-Author: Update the relevant file and struct array for book-author relationships.

Update Book's Author: Update the relevant file and struct array for book-author relationships.

Author Operations
Add, Delete, Update Author: Perform CRUD operations on author information, updating both files and linked lists.

View Author Information: Display author details and all books written by that author, given the author's name.

Coding Requirements
Design necessary functions for each menu option and operation.

Utilize function pointers to avoid code repetition for similar logic.

All add, delete, and update operations that modify data structures must also save changes to the corresponding files.

Static and global variable usage is forbidden.

All memory allocation must be performed using dynamic memory management functions.

Define appropriate struct declarations for each object in the CSV files.

All generated files must be in CSV format.

Project Reporting
Your report (ÖğrenciNo.pdf) should include:

Sufficient test cases for each function, demonstrating correct functionality.

Command-line output (user input and program output) from running your program.

Contents of all data files after program execution.

A section on sources used and what you gained from this project.

Similar to previous Digital Analysis and Introduction to Structural Programming reports, include a table of contents, contact information, and all outputs.

Project Submission
Video: Create a short video (max 8 minutes) demonstrating your application's functionality. Upload it to a video sharing site. You can narrate details. Remember to introduce yourself visually at the beginning of the video.

Report: Save your work, problem definition, screenshots of your solution, algorithm details, and the video link in a report named ÖğrenciNo.pdf.

Submission Package: Submit a .RAR or .ZIP file named ÖğrenciNo.rar or ÖğrenciNo.zip containing:

ÖğrenciNo.pdf (report file)

ÖğrenciNo.c (source code)

All .CSV files generated from test runs.

Important Notes:

All assignments will be checked for similarity. Assignments found to be similar will be graded as 0.

Upload your project via online.yildiz.edu.tr by the deadline (May 27, 2025, 23:59). The system closes automatically; late submissions via email are not possible.

Save a screenshot as proof of successful upload. Submissions sent by email without proof will not be accepted.

Contact
For questions during the project submission process, contact your lab group supervisor. The supervisor may contact you for in-person or online review after the submission deadline. Ensure your current email and phone number are included in your report.

Email: enis.ogdum@std.yildiz.edu.tr

Good luck!
