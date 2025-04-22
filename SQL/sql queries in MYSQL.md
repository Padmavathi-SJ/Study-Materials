## SQL Queries in MYSQL:

### JOINS
* **natural join** --> will return the column(data) which matches (data and data type) in all tables mentioned and remove duplicates also.
```
select * from orders
natural join customer
natural join salesman;
```

```
select e.name, d.dept_name
from employees e
join departments d 
on d.id = e.department_id
join employee_projects ep 
on ep.employee_id = e.id
join projects p 
on p.id = ep.project_id
where p.project_name = 'Finance Dashboard';
```
```
select d.id, d.dept_name, count(ep.project_id) as project_count
from departments d
join employees e 
on e.department_id = d.id
join employee_projects ep 
on ep.employee_id = e.id
join projects p 
on p.id = ep.project_id
group by d.id, e.id;
```

```
select e.name as employee_name
from employees e
join departments d
on d.id = e.department_id
where d.dept_name = 'Engineering'
and e.id not in (
   select distinct employee_id 
     from employee_projects);

or

select e.name as employee_name
from employees e
join departments d
on d.id = e.department_id
left join employee_projects ep
on ep.employee_id = e.id
where d.dept_name = 'Engineering'
and ep.project_id is null;
```

```
select e.name as employee_name, count(ep.project_id) 
as project_count
from employees e
join employee_projects ep
on ep.employee_id = e.id
group by ep.employee_id;
```

```

select e.name as employee_name, count(ep.project_id) as
project_count
from employees e
join employee_projects ep
on ep.employee_id = e.id
join projects p
on p.id = ep.project_id
group by ep.employee_id
having count(ep.project_id) > 1;
```
