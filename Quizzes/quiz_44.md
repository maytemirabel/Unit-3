# Quiz 44 

Download the base **cmoon.db** from the Learning Log, and write the SQL statements to solve the questions below:

1) How many tables are there in the database? 
```
SELECT name from sqlite_master where type = "table";
```
2) How many Male inhabitant are Friendly? 

```
select count(*) from INHABITANT where gender = "Male" and state = "Friendly"
```

3) What is the average gold by village? 

```
select avg(gold) from INHABITANT group by villageid;
```

4) How many items are there that start with the letter "A"?
```
select count(*) from ITEM where item like "A%";
```

5) How many different jobs are there?
```
select count(distinct job) from INHABITANT;
```
6) What are the items owned by the herbalists?
```
select item from ITEM, INHABITANT where INHABITANT.personid = ITEM.owner and INHABITANT.job = "Herbalist";
```
Answer: 1 Dagger 

