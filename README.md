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


-- Populate Client table
INSERT INTO Client (ClientID, ClientFirstName, ClientLastName, ClientDoB, Occupation) VALUES
(1, 'Kaiden', 'Hill', '2006-01-15', 'Student'),
(2, 'Alina', 'Morton', '2010-03-22', 'Student'),
(3, 'Fania', 'Brooks', '1983-07-09', 'Food Scientist'),
(4, 'Courtney', 'Jensen', '2006-11-30', 'Student'),
(5, 'Brittany', 'Hill', '1983-05-18', 'Firefighter'),
(6, 'Max', 'Rogers', '2005-09-12', 'Student'),
(7, 'Margaret', 'McCarthy', '1981-12-05', 'School Psychologist'),
(8, 'Julie', 'McCarthy', '1973-04-28', 'Professor'),
(9, 'Ken', 'McCarthy', '1974-04-28', 'Securities Clerk'),
(10, 'Britany', 'O''Quinn', '1984-01-01', 'Violinist'),
(11, 'Conner', 'Gardner', '1998-08-22', 'Licensed Massage Therapist'),
(12, 'Mya', 'Austin', '1960-03-14', 'Parquet Floor Layer'),
(13, 'Thierry', 'Rogers', '2004-07-19', 'Student'),
(14, 'Eloise', 'Rogers', '1984-09-05', 'Computer Security Manager'),
(15, 'Gerard', 'Jackson', '1979-11-11', 'Oil Exploration Engineer'),
(16, 'Randy', 'Day', '1986-12-30', 'Aircraft Electrician'),
(17, 'Jodie', 'Page', '1990-04-03', 'Manufacturing Director'),
(18, 'Coral', 'Rice', '1996-06-26', 'Window Washer'),
(19, 'Ayman', 'Austin', '2002-10-08', 'Student'),
(20, 'Jaxson', 'Austin', '1999-02-11', 'Repair Worker'),
(21, 'Joel', 'Austin', '1973-03-08', 'Police Officer'),
(22, 'Alina', 'Austin', '2010-09-07', 'Student'),
(23, 'Elin', 'Austin', '1962-01-18', 'Payroll Clerk'),
(24, 'Ophelia', 'Wolf', '2004-04-29', 'Student'),
(25, 'Eliot', 'McGuire', '1967-08-14', 'Dentist'),
(26, 'Peter', 'McKinney', '1968-11-25', 'Professor'),
(27, 'Annabella', 'Henry', '1974-12-08', 'Nurse'),
(28, 'Anastasia', 'Baker', '2001-06-07', 'Student'),
(29, 'Tyler', 'Baker', '1984-10-16', 'Police Officer'),
(30, 'Lilian', 'Ross', '1983-09-27', 'Insurance Agent'),
(31, 'Thierry', 'Arnold', '1975-05-30', 'Bus Driver'),
(32, 'Angelina', 'Rowe', '1979-03-12', 'Firefighter'),
(33, 'Marcia', 'Rowe', '1974-08-31', 'Health Educator'),
(34, 'Martin', 'Rowe', '1976-07-24', 'Ship Engineer'),
(35, 'Adeline', 'Rowe', '2005-02-19', 'Student'),
(36, 'Colette', 'Rowe', '1963-06-11', 'Professor'),
(37, 'Diane', 'Clark', '1975-10-04', 'Payroll Clerk'),
(38, 'Caroline', 'Clark', '1960-05-22', 'Dentist'),
(39, 'Dalton', 'Clayton', '1982-11-18', 'Police Officer'),
(40, 'Steve', 'Clayton', '1990-07-12', 'Bus Driver'),
(41, 'Melanie', 'Clayton', '1987-04-02', 'Computer Engineer'),
(42, 'Alana', 'Wilson', '2007-08-29', 'Student'),
(43, 'Carson', 'Byrne', '1995-12-10', 'Food Scientist'),
(44, 'Conrad', 'Byrne', '2007-06-14', 'Student'),
(45, 'Ryan', 'Porter', '2008-10-25', 'Student'),
(46, 'Elin', 'Porter', '1978-06-03', 'Computer Programmer'),
(47, 'Tyler', 'Harvey', '2007-09-02', 'Student'),
(48, 'Arya', 'Harvey', '2008-02-17', 'Student'),
(49, 'Serena', 'Harvey', '1978-11-29', 'School Teacher'),
(50, 'Lilly', 'Franklin', '1976-03-01', 'Doctor'),
(51, 'Mai', 'Franklin', '1994-09-05', 'Dentist'),
(52, 'John', 'Franklin', '1999-11-12', 'Firefighter'),
(53, 'Judy', 'Franklin', '1995-07-23', 'Firefighter'),
(54, 'Katy', 'Lloyd', '1992-12-20', 'School Teacher'),
(55, 'Tamara', 'Allen', '1963-02-14', 'Ship Engineer'),
(56, 'Maxim', 'Lyons', '1985-04-30', 'Police Officer'),
(57, 'Allan', 'Lyons', '1983-09-20', 'Computer Engineer'),
(58, 'Marc', 'Harris', '1980-06-15', 'School Teacher'),
(59, 'Elin', 'Young', '2009-03-11', 'Student'),
(60, 'Diana', 'Young', '2008-11-02', 'Student'),
(61, 'Diane', 'Young', '2006-05-27', 'Student'),
(62, 'Alana', 'Bird', '2003-08-17', 'Student'),
(63, 'Anna', 'Becker', '1979-10-01', 'Security Agent'),
(64, 'Katie', 'Grant', '1977-07-30', 'Manager'),
(65, 'Joan', 'Grant', '2010-12-14', 'Student
