# Задание 1
## а)

SELECT LastName FROM Reader

WHERE Reader.Address = 'Москва';

## б)

SELECT Author, Title FROM Book

JOIN Reader ON Borrowing.ReaderNr = Reader.ID

WHERE Reader.LastName = "Иванов" AND Reader.FirstName = 'Иван';
