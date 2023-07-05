------creating database----
create database bookdb;

------creating table--------
CREATE TABLE bookdb.books (
b_id int,
title varchar(20),
year int,
price int,
primary key (b_id)
);

------creating table--------
create table bookdb.authors(
a_id int,
name varchar(20),
age int,
b_id int,
primary key (a_id),
foreign key (b_id) references books(b_id)
);

------inserting data--------
insert into bookdb.books values
(1,'biology',1999,599),
(2,'micro biology',2001,999),
(3,'biochemistry',2008,799),
(4,'cellur biology',2016,1199),
(5,'genetic engineering',2022,2599);

------inserting data--------
insert into bookdb.authors values
(1,'ruban',40,2),
(2,'akash',35,3),
(3,'billy',56,5),
(4,'varun',46,1),
(5,'rithik',43,4);

------------Retrieve all the books from the database----------
SELECT * FROM bookdb.books;

------------Retrieve the details of a book based on its title------------
SELECT * FROM bookdb.books where title='biochemistry';

------------Update the price of a book----------------
update bookdb.books set price=499 where title='cell biology';

------------Delete a book from the database based on its title-----------
delete from bookdb.books where title='microbiology';

------------to calculate and display the average price of all the books in the database-----------
select avg(price) from bookdb.books;

------------perform a query to retrieve books along with their respective authors---
SELECT books.title,authors.name FROM bookdb.books
join bookdb.authors on bookdb.books.b_id=bookdb.authors.b_id;
