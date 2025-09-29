### sdist (`.tar.gz`)
- **Source distribution**: your source code + build config.
- Pip will **build** from sdist on the user’s machine if no compatible wheel exists.
- Requires toolchain at install time (Rust, C toolchain, headers).
- Useful for transparency, reproducible builds, and letting uncommon platforms build their own wheels.