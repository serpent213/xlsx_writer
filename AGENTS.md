# Repository Guidelines

## Project Structure & Module Organization
- `lib/` holds the Elixir source (modules live under the `XlsxWriter.*` namespace).
- `native/xlsx_writer/` contains the Rust NIF implementation built via Rustler.
- `test/` contains ExUnit tests.
- `examples/` contains runnable demo scripts.
- `guides/` holds user-facing documentation.
- `config/` contains Mix configuration.
- `checksum-*.exs` stores precompiled NIF checksums for releases.

## Build, Test, and Development Commands
- `mix deps.get` installs Elixir dependencies.
- `mix test` runs the ExUnit test suite.
- `mix format` formats Elixir code using the repo formatter config.
- `mix run examples/comprehensive_demo.exs` generates sample workbooks showcasing features.
- `mix run examples/builder_demo.exs` runs the Builder API demo.
- `mix docs` builds the HexDocs documentation locally.

## Coding Style & Naming Conventions
- Use `mix format` before committing; the formatter enforces 2-space indentation and an 80-column line length.
- Follow existing module naming (`XlsxWriter.*`) and file naming (`snake_case.ex` / `snake_case.exs`).
- Keep Elixir APIs and Rust NIF interfaces aligned; avoid changing NIF signatures without updating corresponding Elixir wrappers.

## Testing Guidelines
- Tests live in `test/` and follow ExUnit conventions (`*_test.exs`).
- Run `mix test` for all changes; no coverage threshold is enforced in this repo.

## Commit & Pull Request Guidelines
- Commit messages follow a `type: short summary` pattern (e.g., `chore: update deps`, `ci: tweak workflow`, `release: update checksums`).
- PRs should include: a concise summary, tests run (or “not run” with a reason), and links to relevant issues.
- If you change Rust NIF code or precompiled assets, update the `checksum-*.exs` files and reference the release steps in `README.md`.
