# Задание 1

## а)

SELECT lastName FROM reader WHERE address = 'Москва';

## б)

SELECT author, title FROM book 

INNER JOIN borrowing

ON borrowing.ISBN = book.ISBN

INNER JOIN reader

ON reader.ID = borrowing.readerNr 

WHERE reader.firstName = 'Иван' AND reader.lastName = 'Иванов';

## в)

SELECT ISBN FROM BookCat bc1 WHERE bc1.CategoryName = 'Горы'

AND NOT EXISTS ( SELECT * FROM BookCat bc2 WHERE bc2.ISBN = bc1.ISBN 

AND bc2.CategoryName = 'Путешествия' )

## г)

SELECT DISTINCT LastName, FirstName, FROM Reader, Borrowing bor

WHERE Reader.ID = bor.ReaderNR AND EXISTS (

