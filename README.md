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

## 17. 

