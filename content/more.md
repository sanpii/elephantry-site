+++
title = "More…"
description = "Elephantry supports async queries and have a transaction helper."
weight = 5
[extra]
more="@/documentation/quickstart/index.md#async"
+++

```rust
let r#async = elephantry.r#async();
r#async.execute("select * from department").await?;

let transaction = elephantry.transaction();
transaction.start()?;
// …
transaction.commit()?;
```
