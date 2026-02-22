# yak-map

Zellij plugin for visualizing yak task state. Displays the task tree from `yx ls` with assignment and status annotations.

## Build

```bash
rustup target add wasm32-wasip1 && cargo build --release --target wasm32-wasip1
```
