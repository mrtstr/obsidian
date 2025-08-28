### build process
- In **[[python]] + Poetry**:
    - `pyproject.toml` → declares deps
    - `poetry.lock` → pins exact versions
    - `poetry install --no-root` → reproducible environment
    -   software is distributed using `packages` and distributed on `pypi.org` (public registry) or your private code artifactory
- In **[[rust]] + [[r cargo]]**:
    - `Cargo.toml` → declares deps
    - `Cargo.lock` → pins exact versions
    - `cargo build` → resolves using the lockfile (if present)
    - builds are stores under `target/`
    - software is distributed using `crate` and distributed on `crates.io` (public registry) or your private code artifactory

# anki

START
Basic
- how does the [[r build process]] in [[rust]] with [[r cargo]] compares to [[python]] and poetry? Name equivalent concepts.
Back: 
### build process
- In **[[python]] + Poetry**:
    - `pyproject.toml` → declares deps
    - `poetry.lock` → pins exact versions
    - `poetry install --no-root` → reproducible environment
    -   software is distributed using `packages` and distributed on `pypi.org` (public registry) or your private code artifactory
- In **[[rust]] + [[r cargo]]**:
    - `Cargo.toml` → declares deps
    - `Cargo.lock` → pins exact versions
    - `cargo build` → resolves using the lockfile (if present)
    - builds are stores under `target/`
    - software is distributed using `crate` and distributed on `crates.io` (public registry) or your private code artifactory

Tags: code rust
<!--ID: 1756392328300-->
END
