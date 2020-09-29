+++
title = "More…"
description = "Elephantry supports async queries and have a transaction helper."
weight = 4
+++

```rust
let r#async = elephantry.r#async();
r#async.execute("select * from department").await?;

let transaction = elephantry.transaction();
transaction.start()?;
// …
transaction.commit()?;
```
