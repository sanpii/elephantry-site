+++
title = "Entity"
description = "Instead of retreive fields one by one, you can aggregate a row of result in a `struct`."
weight = 2
+++

```rust
#[derive(Debug, elephantry::Entity)]
struct Employee {
    id: i32,
    name: String,
}

let results = elephantry
    .query::<Employee>("select id, name from employee", &[])?;

for employee in employees {
    dbg!(employee);
}
```
