```
use practice;

alter table employees
add constraint chk_age
check (age > 18);

alter table employees
add constraint chk_salary
check (salary > 0);

alter table employees
add constraint chk_bonus
check (bonus <= salary);

alter table employees
add constraint chk_dept
check (dept in ('HR', 'IT', 'Sales', 'Finance'));

alter table employees
add constraint chk_joinyear
check (join_year > 2000);

alter table employees
add constraint chk_experience
check (experience >= 0);

alter table employees
add constraint chk_max_age
check (age < 65);

alter table employees
add constraint chk_min_salary
check (salary >= 15000);

alter table employees
add constraint chk_phone
check (char_length(phone) = 10);

alter table employees
add constraint chk_email
check (email like '%@%');

alter table employees
add constraint chk_exp_age
check (experience <= age - 18);

alter table employees
add constraint chk_bonus_nonneg
check (bonus >= 0);

alter table employees
add constraint chk_max_salary
check (salary <= 200000);

alter table employees
add constraint chk_dep_upper
check (dept = upper(dept));

alter table employees
add constraint chk_future_year
check (join_year <= year(curdate()));

alter table employees
add constraint chk_age_exp
check (age <> experience);

alter table employees
add constraint chk_hr_salary
check (not (dept = 'HR' and salary < 25000));

alter table employees
add constraint chk_salary_multiple
check (salary % 100 = 0);

alter table employees
add constraint chk_year_format
check (join_year between 1900 and 2100);

alter table employees
add constraint chk_age_range
check (age between 21 and 60);

alter table employees 
drop check chk_age_range;

use practice;

create table staffs
(
staff_id int,
name varchar(100),
dept_is int,
salary decimal(10, 2),
join_date date
);

alter table employees
alter column salary set default 20000;

alter table employees
alter column salary drop default;

alter table employees
alter column date set default (current_date);

alter table staffs
add constraint pk_staff primary key (staff_id);

alter table staffs
drop primary key;

alter table staffs
rename column dept_is to dept_id;

alter table staffs
add constraint pk_staff_composite
primary key (staff_id, dept_id);

alter table staffs
add constraint fk_dept
foreign key (dept_id)
references depts(dept_id);

alter table depts
add constraint pk_dept
primary key (dept_id);

alter table staffs 
drop foreign key fk_dept;

drop table employees;

CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    salary DECIMAL(10,2),
    dept VARCHAR(50),
    join_year INT,
    experience INT,
    bonus DECIMAL(10, 2),
    email varchar(255),
    phone varchar(100)
    );

INSERT INTO employees 
(emp_id, name, age, salary, dept, join_year, experience, bonus, email, phone) 
VALUES
(1, 'Ravi Kumar', 28, 45000.00, 'IT', 2020, 4, 5000.00, 'ravi.kumar@example.com', '9876543210'),
(2, 'Priya Sharma', 35, 75000.00, 'HR', 2015, 10, 8000.00, 'priya.sharma@example.com', '9123456780'),
(3, 'Amit Verma', 42, 120000.00, 'Finance', 2010, 15, 15000.00, 'amit.verma@example.com', '9988776655'),
(4, 'Sneha Reddy', 30, 60000.00, 'Sales', 2018, 7, 6000.00, 'sneha.reddy@example.com', '9012345678'),
(5, 'Arjun Mehta', 25, 38000.00, 'IT', 2021, 3, 3000.00, 'arjun.mehta@example.com', '9345678123'),
(6, 'Kavya Nair', 38, 85000.00, 'Finance', 2012, 14, 10000.00, 'kavya.nair@example.com', '9456123789'),
(7, 'Rohit Das', 45, 95000.00, 'HR', 2008, 20, 12000.00, 'rohit.das@example.com', '9567123498'),
(8, 'Meera Joshi', 29, 42000.00, 'Sales', 2019, 5, 4000.00, 'meera.joshi@example.com', '9678234512'),
(9, 'Suresh Iyer', 50, 150000.00, 'Management', 2005, 25, 20000.00, 'suresh.iyer@example.com', '9789345621'),
(10, 'Ananya Gupta', 27, 55000.00, 'IT', 2022, 2, 5000.00, 'ananya.gupta@example.com', '9890456723');

select name, salary,
case 
when salary >= 80000 then 'High'
when salary between 40000 and 79999 then 'Medium'
else 'Low'
end as salary_grade
from employees;

select name, age
from employees
order by
case 
when age < 30 then 1
when age between 30 and 50 then 2
else 3
end;

select name, dept,
case
when dept = 'HR' and salary > 50000 then 'Senior HR'
when dept = 'HR' then 'Junior HR'
else dept
end as role
from employees;


select name,
case 
when bonus is null then 'No Bonus'
else concat('$', bonus)
end as bonus_status
from employees;

update employees
set bonus =
case
when salary > 70000 then 10000
when salary between 40000 and 70000 then 5000
else 2000
end;

select dept,
sum(case when salary > 60000 then 1 else 0 end) 
as high_paid,
sum(case when salary <= 60000 then 1 else 0 end)
as low_paid
from employees
group by dept;

select 
count(case when dept = 'IT' then 1 end) as it_employees,
count(case when dept = 'HR' then 1 end) as hr_employees
from employees;

select name, age,
case
when age < 25 then 'Young'
when age between 25 and 45 then 'Mid-age'
else 'Senior'
end as age_category
from employees;

select name, salary,
case 
when salary > 60000 then 
case 
when salary > 100000 then 'Top Earner'
else 'Above Average'
end
else 'Average or Below'
end as salary_category
from employees;

```
