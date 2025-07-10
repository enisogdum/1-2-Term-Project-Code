📚 Library Automation System

This project implements a small-scale, file-based Library Automation System inspired by relational database principles. It was developed as a term project for the BLM1031 - Structural Programming course at Yıldız Technical University.

⸻

📂 Table of Contents
	•	Project Overview
	•	Functional Requirements
	•	Author Management
	•	Student Management
	•	Book Management
	•	Book-Author Relationship Management
	•	Student Book Lending/Returning
	•	Program Menus
	•	Student Operations
	•	Book Operations
	•	Author Operations
	•	Coding Requirements
	•	Project Reporting
	•	Project Submission
	•	Contact

⸻

📌 Project Overview

The system is designed to manage authors, students, books, and their relationships in a library environment. It uses linked lists for data structures and CSV files for persistent storage.

⸻

🛠️ Functional Requirements

📖 Author Management
	•	Add, delete, edit, and list authors.
	•	Each author has a name, surname, and auto-incrementing authorID (1, 2, …, N).
	•	Authors are stored in a singly linked list, sorted by ID, and saved in Yazarlar.csv.

👨‍🎓 Student Management
	•	Add, delete, edit, and list students.
	•	Each student has a name, surname, an initial score of 100, and a unique 8-digit student number.
	•	Students are managed using a doubly linked list and saved in Ogrenciler.csv.

📚 Book Management
	•	Add, delete, edit, and list books.
	•	Each book has a name, 13-digit ISBN, and quantity.
	•	Each copy gets a unique tag like ISBN_1, ISBN_2, etc.
	•	Stored using singly linked lists, including a sublist for book copies.
	•	Lending status: either “RAFTA” or a student’s ID.
	•	Data is stored in CSV format (e.g., Kitaplar.csv, KitapOrnekleri.csv).

🔗 Book-Author Relationship Management
	•	Handle many-to-many relationships: a book can have multiple authors, and an author can write multiple books.
	•	Relationships are stored in KitapYazar.csv.
	•	Data is loaded into a dynamic struct array during runtime.

⚠️ If an author is deleted, their ID in KitapYazar.csv is replaced with -1.
⚠️ Invalid authors or books are blocked with warnings.

🔄 Student Book Lending/Returning
	•	Multiple books can be borrowed/returned by multiple students.
	•	Lending records include: StudentID, BookTagNo, TransactionType (0: lend, 1: return), Date.
	•	Data is stored in OduncIslemleri.csv.

⚠️ Lending is denied if the student’s score is negative.
⚠️ Late returns (after 15 days) deduct 10 points.
⚠️ If no copies are available, transaction fails.

⸻

📋 Program Menus

🧑‍🎓 Student Operations
	•	Add/Delete/Update students
	•	View student info by ID or name
	•	List:
	•	Students who haven’t returned books
	•	Penalized students
	•	All students
	•	Borrow/Return books

📘 Book Operations
	•	Add/Delete/Update books
	•	View book details
	•	List:
	•	Books on shelf
	•	Overdue books
	•	Match or update book-author relationships

✍️ Author Operations
	•	Add/Delete/Update authors
	•	View author info and their books

⸻

💡 Coding Requirements
	•	Use function pointers to avoid repetition
	•	All changes must update both memory and files
	•	No global or static variables
	•	Use dynamic memory allocation only
	•	Define appropriate structs for each CSV format
	•	All files must be in CSV format

⸻

📑 Project Reporting

Your ÖğrenciNo.pdf must include:
	•	Functional test cases with screenshots or terminal outputs
	•	Contents of all CSV files after execution
	•	Explanation of your sources and what you learned
	•	Proper structure (table of contents, contact info, etc.)

⸻

📦 Project Submission

Deadline: May 27, 2025 – 23:59
Submission: via online.yildiz.edu.tr

Submission Package (ÖğrenciNo.zip or .rar) must include:
	•	ÖğrenciNo.pdf (report)
	•	ÖğrenciNo.c (source code)
	•	All .csv files from your tests
	•	Video link (max 8 minutes, introduce yourself)

⚠️ Assignments will be scanned for plagiarism. Identical submissions will be graded 0.

⚠️ Late submissions will not be accepted. Keep a screenshot of your successful upload.

⸻

📬 Contact

For any project-related questions, contact your lab assistant before the deadline.
They may request an online or in-person review afterward.

📧 Email: enis.ogdum@std.yildiz.edu.tr
