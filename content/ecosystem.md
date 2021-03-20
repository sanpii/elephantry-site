+++
title = "Ecosystem"
description = "By enabling the corresponding feature (`config-support`, `r2d2` or `rocket`), elephantry can easily integrate the rust ecosystem."
weight = 4
+++

```rust
// config-support
let mut config = config::Config::new();
config.merge(config::Environment::with_prefix("DATABASE"))?;

let elephantry =
    elephantry::Pool::from_config(&config.try_into()?)?;
```

```rust
// r2d2
let manager =
    elephantry::r2d2::ConnectionManager::new(&database_url);
```

```toml
# rocket
[global.databases.elcaro]
url = "postgresql://localhost/elcaro"
```
