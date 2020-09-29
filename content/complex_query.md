+++
title = "Complex queries"
description = "You can write queries as complex as you like."
weight = 1
+++

```rust
let elephantry = elephantry::Pool::new(database_url)?;
let results = elephantry
    .query::<(String, String)>(include_str!("query.sql"), &[])?;

for result in results {
    println!("{:?}", result);
}
```

```sql
with ranking as (
    select department.name as department,
        employee.first_name || ' ' || employee.last_name as name,
        rank() over (partition by department order by day_salary)
    from employee
    join department
        on department.department_id = employee.department_id
    order by department, rank
)
select row(department, name) from ranking
```
