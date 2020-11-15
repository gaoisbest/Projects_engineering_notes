# Create
```
drop table if exists table_a;
create table table_a as
```

# Select
- `select a from table where a like %str%`: return records that contains `str`, for example, `xxxstryyy`
- `select a from table where a (not) like str%`: return records that start with `str`, for example, `strxxxyyy`
- `select a from table where a is null`: `a` is `null`, otherwise, `a is not null`
- `select a from table where a in (a1, a2, a3)`


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
