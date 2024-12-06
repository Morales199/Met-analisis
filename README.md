# Met-analisis

select * from met
limit 5; 

select count(distinct category) 
from met; 

select count(distinct title) 
from met; 

/*select distinct country
from met;*/

-- How many pieces are in the American Decorative Art collection? 3948
select count(*) from met;

--Count the number of pieces where the category includes ‘celery’
select * from met 
where category like '%celery%'
limit 5;

--Find the title and medium of the oldest piece(s) in the collection.
select min(date) from met; 

--Find the top 10 countries with the most pieces in the collection.
select country, count(*) from met
group by country
order by count(*) desc
limit 10;

--Find the categories HAVING more than 100 pieces. 
SELECT category, COUNT(*)
FROM met
GROUP BY 1
HAVING COUNT(*) > 100;

--Count the number of pieces where the medium contains ‘gold’ or ‘silver’.
select medium, count(*) 
from met
where medium like '%gold%'
or medium like '%silver%'
GROUP BY 1
ORDER BY 2 DESC;



