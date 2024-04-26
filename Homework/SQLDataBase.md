SQL TABLES
=============

By Juan Manuel Carrillo

Tables
------------

### Students Data

sql
DROP TABLE IF EXISTS Studentsdata;
CREATE table Studentsdata (
    # Auto_increment,
    Id Integer PRIMARY KEY NOT NULL ,
    Name Varchar(20) NOT NULL ,
    LastName Varchar(30) NOT NULL ,
    AKA Varchar(10),
    created_at TIMESTAMP NOT NULL DEFAULT current_timestamp
);



<details>
<summary>Inserts</summary>

sql
INSERT INTO Studentsdata (id, Name,LastName, aka) VALUES
('0105123', 'Santiago', 'Arizti Bonilla', 'Santi'),
('0224604', 'Paulina','Barba Mendoza', 'Pau'),
('0216980', 'Edgar Leonardo', 'Díaz Rizo', 'Leo'),
('0216229', 'Uma Paola', 'Gálvez Miranda', 'Uma'),
('0229386', 'Misael','García González', 'Misael'),
('0228431','Daniela', 'García Ray ', 'Dani'),
('0224767','Jorge Andrés', 'González Polit', 'Polit'),
('0225509','Natanael ', 'González Ramos', 'Nata'),
('0220279','Zabdy Elizabet', 'Leos Luna', 'Zabdy'),
('0225118', 'Héctor', 'Macias Lara', 'Héctor'),
('0234847','Marcos Gerardo ', 'De La Cruz Orozco', 'Marcos'),
('0225512', 'Daniel',  'Mendoza Guajardo','Mendoza'),
('0224260', 'Alejandro', 'Mercado Coello', 'Alex'),
('0260523','José Andrés',  'Núñez Favela', 'Andrés'),
('0225511', 'Myriam' , 'Ochoa Garciarce', 'Myriam'),
('0218797', 'Schedar Emilio',  'Rodríguez Aquino', 'Schedar'),
('0227412', 'Santiago Mariano', 'Sánchez Castillo', 'Santiago'),
('0213663', 'Eduardo', 'Solano Jaime', 'Eduardo'),
('0224679', 'Rodrigo' ,  'Castiello Gonzalez', 'Castiello'),
('0224764', 'Bernardo',  'Blanchet Ramírez', 'Bernardo'),
('0224758', 'Diego' , 'Gutiérrez Maisterrena', 'Diego'),
('0214221', 'Juan Manuel' , 'Carrillo Contardo', 'Juanma');

</details>

### Assitance Date

sql
DROP TABLE IF EXISTS AsistanceDate;
Create table AsistanceDate (
    ClassDate Date NOT NULL ,
    ClassNumber INT AUTO_INCREMENT PRIMARY KEY NOT NULL
);


<details>
<summary>Inserts</summary>

sql
INSERT INTO AssistanceDate (ClassDate) VALUES
('2024-02-10'),
('2024-02-17'),
('2024-02-24'),
('2024-03-02'),
('2024-03-09'),
('2024-03-16'),
('2024-03-23'),
('2024-04-13'),
('2024-04-20');
</details>



### Assitance 

sql
DROP TABLE IF EXISTS Assistance;
Create table Assistance (
    Id Integer  NOT NULL ,
    ClassNumber Integer NOT NULL ,
    Assistance VARCHAR(10) NOT NULL,
    FOREIGN KEY (Id) REFERENCES Studentsdata(id)
);


<details>
<summary>Inserts</summary>

sql

INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0224604',1, 'present'),
('0216980',1, 'absent'),
('0216229',1, 'present'),
('0229386',1, 'present'),
('0228431',1, 'absent'),
('0224767',1, 'present'),
('0225509',1, 'present'),
('0220279',1, 'present'),
('0225118',1, 'present'),
('0234847',1, 'present'),
('0225512',1, 'present'),
('0224260',1, 'present'),
('0260523',1, 'absent' ),
('0225511',1, 'present'),
('0218797',1, 'absent' ),
('0227412',1, 'present'),
('0213663',1, 'virtual'),
('0224679',1, 'present'),
('0224764',1, 'present'),
('0224758',1, 'virtual');
INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0214221', 1 , 'absent'); --No estaba enrolado
INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0224604', 2, 'present'),
('0216980', 2, 'absent'),
('0216229', 2, 'present'),
('0229386', 2, 'absent'),
('0228431', 2, 'present'),
('0224767', 2, 'present'),
('0225509', 2, 'present'),
('0220279', 2, 'present'),
('0225118', 2, 'present'),
('0234847', 2, 'present'),
('0225512', 2, 'present'),
('0224260', 2, 'absent'),
('0260523', 2, 'present'),
('0225511', 2, 'present'),
('0218797', 2, 'present'),
('0227412', 2, 'present'),
('0213663', 2, 'virtual'),
('0224679', 2, 'present'),
('0224764', 2, 'absent'),
('0224758', 2, 'virtual'),
('0214221', 2, 'present');
INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0224604',3, 'present'),
('0216980',3, 'present'),
('0216229',3, 'present') ,
('0220279',3, 'present'),
('0225118',3, 'present'),
('0234847',3, 'absent'),
('0225512',3, 'present'),
('0224260',3, 'present'),
('0260523',3, 'absent'),
('0225511',3, 'present'),
('0218797',3, 'present'),
('0227412',3, 'present'), -- (rojiblanco)
('0213663',3, 'virtual'),
('0224679',3, 'present'),
('0224764',3, 'present'),
('0224758',3, 'absent'),
('0214221',3, 'present');
INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0224604',4, 'present'),
('0216980',4, 'present'),
('0216229',4, 'present'),
('0229386',4, 'present'),
('0228431',4, 'present'),
('0224767',4, 'present'),
('0225509',4, 'present'),
('0220279',4, 'absent'),
('0225118',4, 'present'),
('0234847',4, 'absent'),
('0225512',4, 'present'),
('0224260',4, 'present'),
('0260523',4, 'present'),
('0225511',4, 'present'),
('0218797',4, 'present'),
('0227412',4, 'present'),
('0213663',4, 'present'),
('0224679',4, 'present'),
('0224764',4, 'present'),
('0224758',4, 'absent'),
('0214221',4, 'present');
INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0224604',5, 'present'),
('0216980',5, 'absent'),
('0216229',5, 'present'),
('0229386',5, 'present'),
('0228431',5, 'present'),
('0224767',5, 'present'),
('0225509',5, 'present'),
('0220279',5, 'present'),
('0225118',5, 'present'),
('0234847',5, 'present'),
('0225512',5, 'late'),
('0224260',5, 'present'),
('0260523',5, 'present'),
('0225511',5, 'present'),
('0218797',5, 'present'),
('0227412',5, 'present'),
('0213663',5, 'present'),
('0224679',5, 'present'),
('0224764',5, 'present'),
('0224758',5, 'present'),
('0214221',5, 'present');
INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0224604',6, 'absent'),
('0216980',6, 'present'),
('0216229',6, 'present'),
('0229386',6, 'present'),
('0228431',6, 'present'),
('0224767',6, 'present'),
('0225509',6, 'present'),
('0220279',6, 'present'),
('0225118',6, 'absent'),
('0234847',6, 'present'),
('0225512',6, 'present'),
('0224260',6, 'absent'),
('0260523',6, 'present'),
('0225511',6, 'present'),
('0218797',6, 'present'),
('0227412',6, 'absent'),
('0213663',6, 'present'),
('0224679',6, 'present'),
('0224764',6, 'present'),
('0224758',6, 'present'),
('0214221',6, 'present');
INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0224604',7, 'present'),
('0216980',7, 'present'),
('0216229',7, 'present'),
('0229386',7, 'present'),
('0228431',7, 'present'),
('0224767',7, 'late'),
('0225509',7, 'present'),
('0220279',7, 'present'),
('0225118',7, 'present'),
('0234847',7, 'present'),
('0225512',7, 'present'),
('0224260',7, 'present'),
('0260523',7, 'absent'),
('0225511',7, 'present'),
('0218797',7, 'absent'),
('0227412',7, 'present'),
('0213663',7, 'absent'),
('0224679',7, 'present'),
('0224764',7, 'present'),
('0224758',7, 'absent'),
('0214221',7, 'present');
INSERT INTO Assistance (Id, ClassNumber, Assistance) VALUES
('0224604',8, 'present'),
('0216980',8, 'absent'),
('0216229',8, 'present'),
('0229386',8, 'present'),
('0228431',8, 'present'),
('0224767',8, 'present'),
('0225509',8, 'present'),
('0220279',8, 'present'),
('0225118',8, 'absent'),
('0234847',8, 'present'),
('0225512',8, 'present'),
('0224260',8, 'present'),
('0260523',8, 'present'),
('0225511',8, 'present'),
('0218797',8, 'present'),
('0227412',8, 'absent'),
('0213663',8, 'present'),
('0224679',8, 'present'),
('0224764',8, 'present'),
('0224758',8, 'absent'),
('0214221',8, 'present');

</details>


### Quizzes 

sql
DROP TABLE IF EXISTS Quizzes;
Create table Quizzes (
    QuestionNumber INT AUTO_INCREMENT PRIMARY KEY NOT NULL ,
    Question Varchar(30) NOT NULL
);


<details>
<summary>Inserts</summary>

sql
INSERT INTO Quizzes (Question) VALUES
('Algo que no sepan de mí'),
('Qué carrera estudiaste'),
('Color Favorito'),
('Donde Naciste'),
('Libro Favorito'),
('Cumpleaños'),
('Hobby'),
(NULL),
('Artista favorito');

</details>



### AnsewrsQ 

sql
DROP TABLE IF EXISTS AnswerQ;
Create table AnswerQ (
    Id Integer NOT NULL ,
    QuestionNumber Integer  NOT NULL ,
    Responses Varchar(100) ,
    Correct Bool,
    FOREIGN KEY (Id) REFERENCES Studentsdata(id)
);


<details>
<summary>Inserts</summary>

sql
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0224604', 1, 'No me gustan las oreo'),
('0216980', 1, 'soy capricornio'),
('0216229', 1, 'Nací en el 2000'),
('0229386', 1, 'Soy de Celaya'),
('0228431', 1, 'Ballet'),
('0224767', 1, 'No me gusta el menudo'),
('0225509', 1, 'De chico estuve en silla de ruedas 1 año'),
('0220279', 1, 'No me gusta mi nombre porque es difícil escribir y pronunciar'),
('0225118', 1, 'Prefiero cualquier deporte sobre futbol soccer'),
('0234847', 1, 'No me gustan los champiñones'),
('0225512', 1, 'Se supone que el corazón tiene 3 conductos para sangre al cerebro, yo nací con 2'),
('0224260', 1, 'No me gusta el plátano'),
('0260523', 1, 'Tennis'),
('0225511', 1, 'Me encanta el cine, menos comercial'),
('0218797', 1, NULL),
('0227412', 1, 'O- de sangre'),
('0213663', 1, 'Arritmia permanente'),
('0224679', 1, 'Me he roto las dos rodillas, jugando fut y brincando bardas, no me gusta la c.d.m'),
('0224764', 1, 'No me gusta el jitomate, ultra Atlista.'),
('0224758', 1, 'Me gustan todos los deportes pero más el fut. Dejé todo por el futbol.');
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0214221', 1, 'No estaba enrolado en la clase todavía');
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0224604', 2, 'IID'),
('0216980', 2, 'IIN'),
('0216229', 2, 'IIN'),
('0229386', 2, NULL),
('0228431', 2, 'IID'),
('0224767', 2, 'IIN'),
('0225509', 2, 'IIN'),
('0220279', 2, 'IME'),
('0225118', 2, 'IIN'),
('0234847', 2, 'IIN'),
('0225512', 2, 'IIN'),
('0224260', 2, NULL),
('0260523', 2, 'Finanzas UAG'),
('0225511', 2, 'IIN'),
('0218797', 2, 'IID'),
('0227412', 2, 'IIN'),
('0213663', 2, 'IME Ags.'),
('0224679', 2, 'IIN'),
('0224764', 2, NULL),
('0224758', 2, 'IIN'),
('0214221', 2, 'IIN');
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0224604', 3, 'red'),
('0216980', 3, 'green'),
('0216229', 3, 'pink'),
('0229386', 3, 'blue'),
('0228431', 3, 'black'),
('0224767', 3, 'blue'), -- sky blue
('0225509', 3, NULL),
('0220279', 3, 'black'),
('0225118', 3, 'blue'),
('0234847', 3, NULL),
('0225512', 3, 'blue'),
('0224260', 3, 'green'),
('0260523', 3, NULL),
('0225511', 3, 'white'),
('0218797', 3, 'red'),
('0227412', 3, 'red'), -- (rojiblanco)
('0213663', 3, 'morado'),
('0224679', 3, 'green'),
('0224764', 3, 'blue'),
('0224758', 3, NULL),
('0214221', 3, 'green');
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0224604', 4, 'Guadalajara'),
('0216980', 4, 'Guadalajara'),
('0216229', 4, 'Guadalajara'),
('0229386', 4, 'Brian, TX'),
('0228431', 4, 'Zapopan'),
('0224767', 4, 'Guadalajara'),
('0225509', 4, 'Sahuayo, MICH'),
('0220279', 4, NULL),
('0225118', 4, 'Guadalajara'),
('0234847', 4, NULL),
('0225512', 4, 'Guadalajara'),
('0224260', 4, 'Guadalajara'),
('0260523', 4, 'Durango'),
('0225511', 4, 'Guadalajara'),
('0218797', 4, 'Mazatlán'),
('0227412', 4, 'Guadalajara'),
('0213663', 4, 'Aguascalientes'),
('0224679', 4, 'Guadalajara'),
('0224764', 4, 'Guadalajara'),
('0224758', 4, NULL),
('0214221', 4, 'Guadalajara');
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0224604',5 , 'En Llamas, Susan'),
('0216980',5 , NULL),
('0216229',5 , 'Los 5 Lenguajes del Amor'),
('0229386',5 , 'Game of Thrones'),
('0228431',5 , 'La Travesía del Viajero del Alba'),
('0224767',5 , 'Crimen y Castigo'),
('0225509',5 , 'Hábitos Atómicos'),
('0220279',5 , 'Leonora, Elena Poniatouska'),
('0225118',5 , 'Never Split the Difference, FBI'),
('0234847',5 , 'Sherlock Holmes'),
('0225512',5 , 'La Biblia, Dios'),
('0224260',5 , 'Basta de Historias, Oppenheimer'),
('0260523',5 , 'Outliers, Max'),
('0225511',5 , 'El Rey de Hierro'),
('0218797',5 , 'Harry Potter y la P. Filosofal'),
('0227412',5 , 'Los Cuatro Acuerdos'),
('0213663',5 , 'The Ocean at the end of the Lake'),
('0224679',5 , 'Inferno, Dan Brown'),
('0224764',5 , 'Memorias de Hadriano'),
('0224758',5 , 'El Monje que Vendió su Ferrari'),
('0214221',5 , 'La Tormenta de Espadas (GoT 3)');
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0224604', , NULL),
('0216980', 6, '01-20'),
('0216229', 6, '04-05'),
('0229386', 6, '12-15'),
('0228431', 6, '07-12'),
('0224767', 6, '01-22'),
('0225509', 6, '02-24'),
('0220279', 6, '10-06'),
('0225118', 6, NULL),
('0234847', 6, '01-08'),
('0225512', 6, '01-24'),
('0224260', 6, NULL),
('0260523', 6, '07-29'),
('0225511', 6, '10-19'),
('0218797', 6, '12-14'),
('0227412', 6, NULL),
('0213663', 6, '07-29'),
('0224679', 6, '08-10'),
('0224764', 6, '11-30'),
('0224758', 6, '12-23'),
('0214221', 6, '02-06');
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0224604', 7, 'Patinar en hielo'),
('0216980', 7, 'Nadar'),
('0216229', 7, 'Bailar'),
('0229386', 7, 'Futbol'),
('0228431', 7, 'Pilates'),
('0224767', 7, 'Armar Legos'),
('0225509', 7, 'Componer música'),
('0220279', 7, 'Tocar piano'),
('0225118', 7, 'Jugar basket'),
('0234847', 7, 'Ir al cine'),
('0225512', 7, 'Escuchar música'),
('0224260', 7, 'Hiking'),
('0260523', 7, NULL),
('0225511', 7, 'Tejer'),
('0218797', 7, NULL),
('0227412', 7, 'Ir al estadio'),
('0213663', 7, NULL),
('0224679', 7, 'Ir al estadio'),
('0224764', 7, 'Hiking'),
('0224758', 7, NULL),
('0214221', 7, 'Correr');
INSERT INTO AnswerQ (id, QuestionNumber, Responses) VALUES
('0224604', 8, NULL),
('0216980', 8, NULL),
('0216229', 8, NULL),
('0229386', 8, NULL),
('0228431', 8, NULL),
('0224767', 8, NULL),
('0225509', 8, NULL),
('0220279', 8, NULL),
('0225118', 8, NULL),
('0234847', 8, NULL),
('0225512', 8, NULL),
('0224260', 8, NULL),
('0260523', 8, NULL),
('0225511', 8, NULL),
('0218797', 8, NULL),
('0227412', 8, NULL),
('0213663', 8, NULL),
('0224679', 8, NULL),
('0224764', 8, NULL),
('0224758', 8, NULL),
('0214221', 8, NULL);
</details>




### OptionQ 

sql
DROP TABLE IF EXISTS OptionQ;
Create Table OptionQ (
    QuestionNumber Integer NOT NULL ,
    NumOQ Integer PRIMARY KEY NOT NULL
);



<details>
<summary>Inserts</summary>

sql


</details>



### AnswersOQ 

sql
DROP TABLE IF EXISTS AnswersOQ;
Create table AnswersOQ (
    NumOQ Integer PRIMARY KEY NOT NULL ,
    ResponsesOQ Varchar(100) NOT NULL ,
    Correct Bool NOT NULL
);


<details>
<summary>Inserts</summary>

sql


</details>


Diagrams
------------

mermaid
erDiagram
    STUDENTSDATA ||--o{ ASSISTANCE : has
    STUDENTSDATA {
        int Id PK "Primary Key"
        varchar Name
        varchar LastName
        varchar AKA "Also Known As"
        timestamp created_at "Creation Date"
    }
    ASSISTANCEDATE ||--o{ ASSISTANCE : corresponds
    ASSISTANCEDATE {
        date ClassDate
        int ClassNumber PK "Primary Key"
    }
    ASSISTANCE {
        int Id FK "Foreign Key"
        int ClassNumber FK "Foreign Key"
        varchar Assistance
    }
    STUDENTSDATA ||--o{ ANSWERQ : has
    ANSWERQ {
        int Id FK "Foreign Key"
        int QuestionNumber FK "Foreign Key"
        varchar Responses
        bool Correct
    }
    QUIZZES ||--o{ ANSWERQ : includes
    QUIZZES {
        int QuestionNumber PK "Primary Key"
        varchar Question
    }
    QUIZZES ||--o{ OPTIONQ : includes
    OPTIONQ {
        int QuestionNumber FK "Foreign Key"
        int NumOQ PK "Primary Key"
    }
    OPTIONQ || ANSWERSOQ : has
    ANSWERSOQ {
        int NumOQ FK "Foreign Key"
        varchar ResponsesOQ
        bool Correct 
    }
