+++
title = "Write data"
description = "You can easily retreive, create, update or delete entity with the model approach.\n\nThe [cli](https://crates.io/crates/elephantry-cli) helps you to generate entities from your database schema."
weight = 3
[extra]
more="@/documentation/quickstart/index.md#modification"
+++

```rust
#[derive(elephantry::Entity)]
#[elephantry(model = "Model", structure = "Structure")]
struct Entity {
    #[elephantry(pk)]
    id: i32,
    name: String,
}

elephantry.find_all::<Model>(Some("order by name"))?;
elephantry.insert_one::<Model>(entity)?;
elephantry.update_one::<Model>(pk!{id => entity.id}, entity)?;
elephantry.delete_one::<Model>(entity)?;
```
