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
