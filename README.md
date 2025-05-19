# Car_-dekho_Analysis_MySQL_2024

create database cars;
use cars;

-- 1) Read Data 
select * from car_dekho;

-- 2) Total Cars: To get a count of total records
select count(*) from car_dekho;

-- 3) The manager asked the employee how many cars will be available in 2023?
select count(*) from car_dekho where year=2023;

-- 4) The manager asked the employee how many cars will be available in 2020,2021,2022?
-- 1st Approch
select count(*) from car_dekho where year in(2020,2021,2022);
-- 2nd Aprroch
select count(*) from car_dekho where year=2020;
select count(*) from car_dekho where year=2021;
select count(*) from car_dekho where year=2022;

-- 5) Client asked me to print the total of all cars by year . i don't see all the details.
select year, count(*) from car_dekho group by year;

-- 6) Client asked to car dealer agent How many diesel cars will be there in 2020?
select count(*) from car_dekho where fuel="Diesel" and year=2020;

-- 7) Client asked to car dealer agent How many Petrol cars will be there in 2020?
select count(*) from car_dekho where fuel="Petrol" and year=2020;

-- 8) The manager told the employee to give a print all the fuel cars(petrol,diesel,& CNG) come by all year.
select year,count(*) from car_dekho where fuel="Petrol" group by year;
select year,count(*) from car_dekho where fuel="Diesel" group by year;
select year,count(*) from car_dekho where fuel="CNG" group by year;

-- 9) The manager said there were more than 100 cars in a given year,which year had more than 100 cars?
select year,count(*) from car_dekho group by year having count(*)>100;

-- 10)  The manager said to the employee all cars count details 2015  and 2023; we need a complete list.
select count(*) from car_dekho where year  between 2015 and 2023 ; 

-- 11) The manager said to the employees  all cars details between  2015 and 2023. we need a complete list.
select * from car_dekho where year between 2015 and 2023 ; 

