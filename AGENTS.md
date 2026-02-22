# yak-map

Zellij plugin (WASI) for visualizing yak task state. Displays the task tree from `yx ls` with assignment and status annotations.

## Build

Requires Rust with the `wasm32-wasip1` target:

```bash
rustup target add wasm32-wasip1
cargo build --release --target wasm32-wasip1
```

The output binary is at `target/wasm32-wasip1/release/yak-map.wasm`.

## Architecture

- Single-binary Zellij plugin compiled to WASI (`wasm32-wasip1`)
- Entry point: `src/main.rs`
- Plugin manifest: `plugin.yaml`
- `build.rs` runs at compile time

## Runtime

The plugin reads task state from the `/host/.yaks` directory inside Zellij. This is Zellij's host filesystem mount — it maps to the `.yaks/` directory in the project root where the plugin is loaded.

## Testing

```bash
cargo test
```

Dev dependencies (e.g. `tempfile`) are used for tests only.
