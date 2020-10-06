### Aggregate functions
* Aggregate functions perform a calculation on a set of rows and return a single row.

* `AVG` function is used to find average of a particular column. 
```sql
SELECT 
	AVG (age) AS avg_age -- calculate avg age
FROM
	customers;
```
**output**
```
       avg_age       
---------------------
 24.2000000000000000
```
* `MAX` function is used to find max of a particular column. 
```sql
SELECT 
	MAX( age) AS max_age
FROM
	customers;
```
**output**
```
 max_age 
---------
    29
```
* `MIN` function is used to find max of a particular column. 
```sql
SELECT 
	MIN (age) AS min_age
FROM
	customers;
```
**output**
```
 min_age 
---------
    19
```
* `SUM` function is used to find total of a particular column. 
```sql
SELECT 
	SUM(quantity) AS total_quantity --total quantity ordered by all customers
FROM
	orders;
```
**output**
```
 total_quantity 
----------------
      12
```
#### GROUP BY 
* This clause is used to group the rows that has identical data. In the above query we are grouping `customer_id` and making a total of order quantity.
`customer_id` 1 has ordered total 3 no of items in 2 times.  
```sql
SELECT 
	customer_id, SUM(quantity) AS total_quantity
FROM
	orders
GROUP BY 
    customer_id
ORDER BY 
	customer_id;
```
**output**
```
 customer_id | total_quantity 
-------------+----------------
        1    |           3
        3    |           1
        4    |           3
        5    |           5 
```