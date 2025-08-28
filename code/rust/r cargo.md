## cargo
```
my-workspace/
├─ Cargo.toml         # virtual manifest (no [package]!)
├─ Cargo.lock         # single lockfile for all members
├─ crates/
│  ├─ corelib/
│  │  ├─ Cargo.toml
│  │  └─ src/lib.rs
│  └─ utils/
│     ├─ Cargo.toml
│     └─ src/lib.rs
└─ apps/
   └─ cli/
      ├─ Cargo.toml
      └─ src/main.rs

```

- `Cargo.toml`
```toml
[workspace]
members = [
  "crates/*",
  "apps/*",
]
# Optional: only build these by default (others still in the workspace)
default-members = ["apps/cli"]

# Centralized dependency versions (Cargo 1.64+)
[workspace.dependencies]
serde = "1.0"
anyhow = "1"

# Shared profiles for all members
[profile.release]
lto = "thin"
codegen-units = 1

# (Optional) override registry crates with local paths
[patch.crates-io]
my-internal-crate = { path = "crates/corelib" }
```