# BWDK Rust SDK — Integration Guide for Agents

You are integrating **BWDK (Buy With DigiKala)** into a Rust project (Actix-web / Axum / Rocket / Warp) via this SDK. Read this file **first**, then consult the companion references below.

## BWDK constants

- **Host:** `https://bwdk-backend.digify.shop`
- **Auth scheme:** `MerchantAPIKeyAuth` — header `Authorization: <api_key>`.
- **Main API module:** `bwdk_sdk::apis::default_api`.
- **Config struct:** `bwdk_sdk::apis::configuration::Configuration`.
- **Crate name:** `bwdk_sdk`.

## Companion references

| File                  | When to read                                                 |
|-----------------------|--------------------------------------------------------------|
| `README.md`           | `Cargo.toml` dependency snippet and feature notes. Follow it verbatim. |
| `FLOWCHART.md`        | Canonical order state machine. All callback/webhook branching MUST match these state names. |
| `docs/DefaultApi.md`  | Exact method names and signatures per endpoint.              |
| `docs/*.md`           | Per-model reference (e.g. `docs/OrderCreate.md`).            |

Do **not** duplicate install or method-signature details here — fetch `README.md`.

## Install

The SDK is a local-path crate. Vendor the `bwdk_sdk/` folder (or add it as a git dependency) and declare it in the host project's `Cargo.toml`:

```toml
[dependencies]
bwdk_sdk = { git = "https://github.com/rznas/bwdk-sdk-rust.git", tag = "vX.Y.Z" }
# or, if vendored locally:
# bwdk_sdk = { path = "./vendor/bwdk_sdk" }
```

## Minimal wrapper pattern

```rust
use bwdk_sdk::apis::configuration::{ApiKey, Configuration};
use bwdk_sdk::apis::default_api;

let mut cfg = Configuration::new();
cfg.base_path = "https://bwdk-backend.digify.shop".to_string();
cfg.api_key = Some(ApiKey {
    prefix: None,
    key: std::env::var("BWDK_API_KEY")?,
});

let order = default_api::order_api_v1_create_order_create(&cfg, payload).await?;
```

Function names are snake_case and OpenAPI-generated (e.g. `order_api_v1_create_order_create`, `order_api_v1_manager_verify_create`). Look them up in `docs/DefaultApi.md`; do **not** guess.

## Integration invariants

1. **SDK only.** Never call BWDK with `reqwest` (directly), `hyper`, `ureq`, or `isahc` for BWDK endpoints.
2. **Callback flow.** After payment, BWDK redirects the customer to your `callback_url`. Load the order (`order_api_v1_manager_retrieve`), match on `order.status` per `FLOWCHART.md`, then call `order_api_v1_manager_verify_create` — `verify` is mandatory before `SHIPPED`.
3. **Errors.** All functions return `Result<T, bwdk_sdk::apis::Error<E>>`. Match on `Error::ResponseError` to see status + body. Retry only on `Error::Reqwest`/transport variants, never on 4xx.
4. **Async runtime:** the client uses `reqwest` under the hood — run calls on a tokio runtime.
5. **Pinning.** Pin by `tag = "vX.Y.Z"` in `Cargo.toml`; never `branch = "main"` in production.

## Project conventions

- Share a single `Configuration` via `Arc<Configuration>` in your application state; it's `Send + Sync`.
- Prefer `?` with your own error type that wraps `bwdk_sdk::apis::Error<E>` rather than unwrapping at call sites.
- Model types in `bwdk_sdk::models::*` derive `Serialize`/`Deserialize` via Serde — use them directly for your own JSON responses instead of re-mapping.
