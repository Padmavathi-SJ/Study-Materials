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

```
