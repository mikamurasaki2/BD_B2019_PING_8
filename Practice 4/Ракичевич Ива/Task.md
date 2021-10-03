# Задание 1
## а)

SELECT reader.LastName FROM Reader reader

WHERE reader.Address = 'Москва';

## б)

SELECT book.Author, book.Title FROM Book book

JOIN Borrowing borrowing ON reader.ID = borrowing.ReaderNr

JOIN Book book ON borrowing.ISBN = book.ISBN

WHERE reader.LastName = 'Иванов' AND reader.FirstName = 'Иван';

