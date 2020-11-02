# show tables in database
`show tables in db_name`

# join on
```
select e.name, s.salary
from employee e
join salaries s
on e.emp_id = s.emp_id
```

# group by
```
select dept_no, count(emp_no)
from dept_emp
group by dept_no
```
