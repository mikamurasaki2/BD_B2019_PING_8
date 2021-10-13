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

AND bc2.CategoryName = 'Путешествия' );

## г)

SELECT DISTINCT LastName, FirstName FROM Reader, Borrowing bor

WHERE Reader.ID = bor.ReaderNR AND EXISTS (

SELECT * FROM Borrowing WHERE bor.ISBN = Borrowing.ISBN 
  
AND bor.CopyNumber = Borrowing.CopyNumber
  
AND bor.ReturnDate = Borrowi.ReturnDate )

## д)

SELECT DISTINCT LastName, FirstName FROM Reader r

WHERE Reader.ID = Borrowing.ReaderNr AND NOT (LastName = 'Иванов' and FirstName = 'Иван')

AND Borrowing.ISBN in (
  
SELECT DISTINCT Borrowing.ISBN FROM Borrowing
  
WHERE Borrowing.ReaderNr in (
  
SELECT Reader.ID FROM Reader WHERE Reader.LastName = 'Иванов'
    
AND Reader.FirstName = 'Иван')
    
)


