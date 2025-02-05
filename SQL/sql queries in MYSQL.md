## SQL Queries in MYSQL:

### JOINS
* **natural join** --> will return the column(data) which matches (data and data type) in all tables mentioned and remove duplicates also.
```
select * from orders
natural join customer
natural join salesman;
```
