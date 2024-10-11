# tokio-postgres-rustls2

> This is a fork of [`tokio-postgres-rustls`](https://github.com/jbg/tokio-postgres-rustls.git).
>
> Unfortunately its development died down, so I decided to pick it up again to ensure it is updated in the future.

This is an integration between the [rustls TLS stack](https://github.com/ctz/rustls)
and the [tokio-postgres asynchronous PostgreSQL client library](https://github.com/sfackler/rust-postgres).

[![Crate](https://img.shields.io/crates/v/tokio-postgres-rustls2.svg)](https://crates.io/crates/tokio-postgres-rustls2)

[API Documentation](https://docs.rs/tokio-postgres-rustls2/)

# Example

```
let config = rustls::ClientConfig::builder()
    .with_root_certificates(rustls::RootCertStore::empty())
    .with_no_client_auth();
let tls = tokio_postgres_rustls2::MakeRustlsConnect::new(config);
let connect_fut = tokio_postgres::connect("sslmode=require host=localhost user=postgres", tls);
// ...
```

# License

tokio-postgres-rustls2 is distributed under the MIT license.
