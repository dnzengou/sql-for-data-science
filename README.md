# SQL coding

## Sources
*[Chinook DB source](https://archive.codeplex.com/?p=chinookdatabase)
*[github DB repo](https://github.com/lerocha/chinook-database)
*[scripts](http://web.vietxam.com/sql/sqlite/)
*[more scripts](https://github.com/LucasMcL/15-sql_queries_02-chinook/blob/master/chinook-queries.sql)
*[other scripts](https://github.com/wblakecannon/DataCamp/blob/master/05-importing-data-in-python-(part-1)/3-working-with-relational-databases-in-python/ordering-your-sql-records-with-order-by.py)

*[DB Browser for SQLite](https://sqlitebrowser.org/)

***

## Module 1

1. 
SELECT * FROM Employees

2. 
SELECT FirstName, LastName, Birthdate, Address, City, State
FROM Employees

3. 
SELECT * FROM Tracks
LIMIT 20

***


## Module 2

1. SELECT Count(TrackId)
FROM Track
WHERE Milliseconds >= 5000000

2. SELECT count(DISTINCT i.InvoiceId)
FROM Invoices as i
WHERE i.Total between 5 and 15

3. SELECT FirstName, LastName, Company, State
FROM Customers
WHERE State in ('RJ', 'DF', 'AB', 'BC', 'CA', 'WA', 'NY')

4. 
SELECT InvoiceId, InvoiceDate, CustomerId, Total
FROM Invoices
WHERE CustomerId in (56, 58) AND (Total >= 1.00 and Total <= 5.00)

5. 
SELECT t.Name, COUNT(t.Name)
FROM Tracks t
WHERE t.Name like 'All%'

6. 
SELECT c.Email
FROM Customers c
WHERE c.Email like 'J%gmail.com'

7. 
SELECT i.InvoiceId, i.Total
FROM Invoices i
WHERE i.BillingCity in ('Brasilia', 'Edmonton', 'Vancouver')
ORDER BY invoiceId DESC

8. 
SELECT i.CustomerId , COUNT(i.InvoiceId)
FROM Invoices i
GROUP BY i.CustomerId
ORDER BY COUNT(i.InvoiceId) DESC


***

## Module 3

1.
SELECT t.Name
FROM Tracks t
WHERE t.AlbumId = ( select a.AlbumId
FROM Albums a
WHERE a.Title = 'Californication')

2.
SELECT c.CustomerId, c.FirstName, c.LastName, c.City, c.Email, COUNT(i.InvoiceId)
FROM Customers c join Invoices i
ON c.CustomerId = i.CustomerId
GROUP BY c.CustomerId

3.
SELECT t.Name, a.Title, ar.Name, t.TrackId
FROM Artists ar
INNER JOIN Albums a
ON ar.ArtistId = a.ArtistId
INNER JOIN Tracks t
ON a.AlbumId = t.AlbumId






