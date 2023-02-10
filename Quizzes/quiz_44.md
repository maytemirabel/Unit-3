# Quiz 44 

Download the base **cmoon.db** from the Learning Log, and write the SQL statements to solve the questions below:

1) How many tables are there in the database? 
  
      Answer: 4 

2) How many Male inhabitant are Friendly? 

```
gender = "Male" AND state = "Friendly" 
```
Answer: 4 

3) What is the average gold by village? 



4) How many items are there that start with the letter "A"?

Answer: 3

5) How many different jobs are there?



6) What are the items owned by the herbalists?
```
owner = "18" OR owner = "4"
```
Answer: 1 Dagger 




select count(*) from INHABITANT where gender = "Male" and state = "Friendly";

select avg(gold) from INHABITANT group by villageid;

select count(*) from ITEM where item like "A%";

select count(distinct job) from INHABITANT;

select item from ITEM, INHABITANT where INHABITANT.personid = ITEM.owner and INHABITANT.job = "Herbalist";

