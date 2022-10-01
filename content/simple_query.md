+++
title = "Simple query"
description = "Connect to the database, execute a query a tell witch data you want and its type. Elephantry does the rest!"
weight = 0
[extra]
more="@/documentation/quickstart/index.md#primitive-types"
+++

```rust
let elephantry = elephantry::Pool::new(&database_url)?;
let results = elephantry
    .execute("select name from department")?;

for result in &results {
    let name: String = result.get("name");
    println!("{name}");
}
```
