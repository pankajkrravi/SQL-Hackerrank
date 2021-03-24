# SQL-Hackerrank
### 1. Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

select * 
from city 
where population >100000 and countrycode='usa';

### 2. Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.
 select name
from city 
where population > 120000 and countrycode ='usa';

### 3.query all columns (attributes) for every row in the city table.
select * 
from city;

### 4. Query all columns for a city in CITY with the ID 1661.
select * 
from city
where id=1661;

## 5. Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.
 select *
from city
where 
 countrycode='jpn';
 
## 6. Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
select name
from city
where countrycode='jpn';

## 7.  Query a list of CITY and STATE from the STATION table.
select CITY,STATE
from STATION;

## 8. Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
select distinct city
from station
where mod(id, 2) = 0 order by city asc;

## 9. Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
select count(city) - count(distinct(city))from station;

## 10. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

select distinct city
from station 
where city like 'a%' OR city like 'e%' OR city like 'i%' OR city like 'o%' OR city like 'u%';

## 11. Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.
select distinct city
from station 
where city like '%a' OR city like '%e' OR city like '%i' OR city like '%o' OR city like '%u';

## 12. Weather Observation Station 8

Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

select distinct city
from station 
where (city like '%a' OR city like '%e' OR city like '%i' OR city like '%o' OR city like '%u')AND 
(city like 'a%' OR city like 'e%' OR city like 'i%' OR city like 'o%' OR city like 'u%');

## 13. Weather Observation Station 9
Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

select distinct city
from station 
where not(city like 'a%' OR city like 'e%' OR city like 'i%' OR city like 'o%' OR city like 'u%');

## 14. Weather Observation Station 10
Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

select distinct city
from station 
where not(city like '%a' OR city like '%e' OR city like '%i' OR city like '%o' OR city like '%u');

## 15. Weather Observation Station 11

Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.


select distinct city
from station 
where not(city like '%a' OR city like '%e' OR city like '%i' OR city like '%o' OR city like '%u')or 
not(city like 'a%' OR city like 'e%' OR city like 'i%' OR city like 'o%' OR city like 'u%');

## 16. Weather Observation Station 12
Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

select distinct city
from station 
where not(city like '%a' OR city like '%e' OR city like '%i' OR city like '%o' OR city like '%u')and 
not(city like 'a%' OR city like 'e%' OR city like 'i%' OR city like 'o%' OR city like 'u%');

## 17. Higher Than 75 Marks

Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

select name from students
where marks > 75
order by right(name,3),id;

## 18. Employee Names

Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.


select name 
from employee
order by name;

## 19. Employee Salaries

Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

select name
from employee
where salary > 2000
and months <10;

## 20.Weather Observation Station 17

Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in STATION is greater than . Round your answer to  decimal places.

### Note: Not all database systems support the SELECT TOP clause. MySQL supports the LIMIT clause to select a limited number of records, while Oracle uses FETCH FIRST n ROWS ONLY and ROWNUM.

select round(LONG_W,4)
from station
where LAT_N > 38.7780
order by LAT_N limit 1;

## 21.  Weather Observation Station 18  ###################################################################

Consider P1(a,b)  and P2(c,d)to be two points on a 2D plane.

a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
 c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
d happens to equal the maximum value in Western Longitude (LONG_W in STATION).
Query the Manhattan Distance between points P1 and P2 and round it to a scale of  decimal places.

select round(abs(min(lat_n)-max(lat_n))+abs(min(long_w)-max(long_w)),4) from station;


### 22. Revising Aggregations - The Sum Function

Query the total population of all cities in CITY where District is California.

select sum(population)
from city
where district='California';

### 23. Revising Aggregations - Averages

Query the average population of all cities in CITY where District is California.

select avg(population)
from city
where district='California'

### 24. Average Population

Query the average population for all cities in CITY, rounded down to the nearest integer.

select FLOOR(avg(population))
from city;

## ==========================================Note: FLOOR() =====================
Syntax

Description of floor.gif follows
Description of the illustration floor.gif

Purpose

FLOOR returns largest integer equal to or less than n.

This function takes as an argument any numeric datatype or any nonnumeric datatype that can be implicitly converted to a numeric datatype. The function returns the same datatype as the numeric datatype of the argument.
**Examples**

The following example returns the largest integer equal to or less than 15.7:

SELECT FLOOR(15.7) "Floor" FROM DUAL;

     Floor
----------
        15
        
#### 25. Japan Population
Query the average population for all cities in CITY, rounded down to the nearest integer.


select sum(population)
from city
where countrycode='JPN';

## 26. Population Density Difference

Query the difference between the maximum and minimum populations in CITY.

select
max(population) - min(population)
from city;

## 27. Asian Population

Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

select sum(city.population)
from city,country
where city.countrycode=country.code 
and 
country.CONTINENT ='Asia';

### 28. African Cities

Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

select  city.name
from city,country
where city.countrycode=country.code 
and 
country.CONTINENT ='Africa';

## 29. Average Population of Each Continent

Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

select co.continent, floor(avg(c.population))
from city c join country co
on c.countrycode = co.code
group by co.continent;

### Note : TRUNC(n,i): The TRUNC function returns n truncated to i decimal places. If i is omitted, then n is truncated to 0 places. i can be negative to truncate (make zero) n digits left of the decimal point. Following is the example of TRUNC function, with i as positive, zero and negitive values.
### FLOOR(n): The FLOOR function returns the largest INTEGER that is equal to or less than n.

### 30. 

**solution- 1
 SELECT 
    CASE
        WHEN Grades.Grade > 7
        THEN Students.Name
        WHEN Grades.Grade <= 7
        THEN NULL
    END, Grades.Grade, Students.Marks FROM Students INNER JOIN Grades ON Students.Marks BETWEEN Grades.Min_Mark AND Max_Mark ORDER BY Grades.Grade DESC, Students.Name ASC, Students.Marks ASC;
    ------------------------------------------------------
**    solution -- 2
  SELECT Students.Name, Grades.Grade, Students.Marks 
  FROM Students 
  INNER JOIN Grades ON Students.Marks BETWEEN Grades.Min_Mark AND Max_Mark
  WHERE Grades.Grade > 7 ORDER BY Grades.Grade DESC, Students.Name ASC;
  
SELECT null, Grades.Grade, Students.Marks 
FROM Students INNER JOIN Grades ON Students.Marks BETWEEN Grades.Min_Mark AND Max_Mark 
WHERE Grades.Grade <= 7 
ORDER BY Grades.Grade DESC,Students.Marks ASC;

----------------------------------------------------------------------------------------------------------------------------------------------------------------
