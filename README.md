# database-fundamental-notes
--UNION
--Combine the results of more than one query into one result set of data

--Select all the names in the school
Select firstname, lastname from Student --17
UNION
Select firstname,lastname from Staff --10
--OH NO! We lost 2 people:(
--Union uses distinct by default

Select firstname, lastname from Student --17
UNION ALL
Select firstname,lastname from Staff --10
-- to return duplicates use UNION ALL

--Rules
--Can combine any number of queries
Select firstname,lastname from Student
UNION ALL
Select firstname,lastname from Staff 

--Combine being combined must have similar datatypes
Select firstname,Birthdate from Student
UNION ALL
Select firstname,lastname from Staff 

--Column names are determined from the first query
Select firstname'StudentFirstName',lastname from student--17
UNION ALL
Select firstname'StaffFirstName',lastname from staff--10

--Order By
Select firstname,lastname,city from student
order by lastname asc
Select firstname,lastname,city from student
order by lastname desc

Select firstname,lastname,city from student
order by lastname asc,firstname asc


--If you order by you apply it after the query
Select firstname,lastname from Student
UNION 
Select firstname,lastname from Staff
order by lastname asc
