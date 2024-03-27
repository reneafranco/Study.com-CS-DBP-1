# Study.com-CS-DBP-1

1 - Create the database tables based on the provided Entity Relationship Diagram (ERD).

-- Create Authors table
CREATE TABLE Authors (
    AuthorID INT PRIMARY KEY,
    AuthorFirstName VARCHAR(50),
    AuthorLastName VARCHAR(50),
    AuthorNationality VARCHAR(50)
);

-- Create Books table
CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    BookTitle VARCHAR(100),
    BookAuthor INT,
    Genre VARCHAR(50),
    FOREIGN KEY (BookAuthor) REFERENCES Authors(AuthorID)
);

-- Create Clients table
CREATE TABLE Clients (
    ClientID INT PRIMARY KEY,
    ClientFirstName VARCHAR(50),
    ClientLastName VARCHAR(50),
    ClientDoB INT,
    Occupation VARCHAR(50)
);

-- Create Borrowers table
CREATE TABLE Borrowers (
    BorrowID INT PRIMARY KEY,
    ClientID INT,
    BookID INT,
    BorrowDate DATE,
    FOREIGN KEY (ClientID) REFERENCES Clients(ClientID),
    FOREIGN KEY (BookID) REFERENCES Books(BookID)
);


-- Populate Author table
INSERT INTO Author (AuthorID, AuthorFirstName, AuthorLastName, AuthorNationality)
VALUES
(1, 'Sofia', 'Smith', 'Canada'),
(2, 'Maria', 'Brown', 'Brazil'),
(3, 'Elena', 'Martin', 'Mexico'),
(4, 'Zoe', 'Roy', 'France'),
(5, 'Sebastian', 'Lavoie', 'Canada'),
(6, 'Dylan', 'Garcia', 'Spain'),
(7, 'Ian', 'Cruz', 'Mexico'),
(8, 'Lucas', 'Smith', 'USA'),
(9, 'Fabian', 'Wilson', 'USA'),
(10, 'Liam', 'Taylor', 'Canada'),
(11, 'William', 'Thomas', 'Great Britain'),
(12, 'Logan', 'Moore', 'Canada'),
(13, 'Oliver', 'Martin', 'France'),
(14, 'Alysha', 'Thompson', 'Canada'),
(15, 'Isabelle', 'Lee', 'Canada'),
(16, 'Emily', 'Clark', 'USA'),
(17, 'John', 'Young', 'China'),
(18, 'David', 'Wright', 'Canada'),
(19, 'Thomas', 'Scott', 'Canada'),
(20, 'Helena', 'Adams', 'Canada'),
(21, 'Sofia', 'Carter', 'USA'),
(22, 'Liam', 'Parker', 'Canada'),
(23, 'Emily', 'Murphy', 'USA');

-- Populate Book table
INSERT INTO Book (BookID, BookTitle, BookAuthor, Genre)
VALUES
(1, 'Build your database system', 1, 'Science'),
(2, 'The red wall', 2, 'Fiction'),
(3, 'The perfect match', 3, 'Fiction'),
(4, 'Digital Logic', 4, 'Science'),
(5, 'How to be a great lawyer', 5, 'Law'),
(6, 'Manage successful negotiations', 6, 'Society'),
(7, 'Pollution today', 7, 'Science'),
(8, 'A gray park', 2, 'Fiction'),
(9, 'How to be rich in one year', 8, 'Humor'),
(10, 'Their bright fate', 9, 'Fiction'),
(11, 'Black lines', 10, 'Fiction'),
(12, 'History of theater', 11, 'Literature'),
(13, 'Electrical transformers', 12, 'Science'),
(14, 'Build your big data system', 1, 'Science'),
(15, 'Right and left', 13, 'Children'),
(16, 'Programming using Python', 1, 'Science'),
(17, 'Computer networks', 14, 'Science'),
(18, 'Performance evaluation', 15, 'Science'),
(19, 'Daily exercise', 16, 'Well being'),
(20, 'The silver uniform', 17, 'Fiction'),
(21, 'Industrial revolution', 18, 'History'),
(22, 'Green nature', 19, 'Well being'),
(23, 'Perfect football', 20, 'Well being'),
(24, 'The chocolate love', 21, 'Humor'),
(25, 'Director and leader', 22, 'Society'),
(26, 'Play football every week', 20, 'well being'),
(27, 'Maya the bee', 13, 'Children'),
(28, 'Perfect rugby', 20, 'Well being'),
(29, 'The end', 23, 'Fiction'),
(30, 'Computer security', 1, 'Science'),
(31, 'Participate', 22, 'Society'),
(32, 'Positive figures', 3, 'Fiction');
