## packaging formats

![[py wheel#wheel (`.whl`)]]

![[py sdist#sdist (`.tar.gz`)]]

# anki

START
Basic
[[py packaging formats]] for [[python]]
- differences when which to choose

Back: 
Both should be published: [[py wheel]] for common platforms (Linux manylinux/musllinux, macOS universal2, Windows), plus an [[py sdist]] fallback
### wheel (`.whl`)
- **Built (binary) distribution**: ready to install—no compiling on the user’s machine.
- Contains compiled extensions (`.so`/`.pyd`) + your Python files + metadata.

### sdist (`.tar.gz`)
- **Source distribution**: your source code + build config.
- Pip will **build** from sdist on the user’s machine if no compatible wheel exists.
- Requires toolchain at install time (Rust, C toolchain, headers).
- Useful for transparency, reproducible builds, and letting uncommon platforms build their own wheels.

Tags: code python
<!--ID: 1759138897672-->
END