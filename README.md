# SQL-Hackerrank
1. Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

select * 
from city 
where population >100000 and countrycode='usa';

2. Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.
 select name
from city 
where population > 120000 and countrycode ='usa';
3. query all columns (attributes) for every row in the city table.
select * 
from city;
4. Query all columns for a city in CITY with the ID 1661.
select * 
from city
where id=1661;
5. Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.
 select *
from city
where 
 countrycode='jpn';
6. Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
select name
from city
where countrycode='jpn';
7. Query a list of CITY and STATE from the STATION table.
select CITY,STATE
from STATION;
8. Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
select distinct city
from station
where mod(id, 2) = 0 order by city asc;
9. Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
select count(city) - count(distinct(city))from station;




