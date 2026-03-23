# Contributing to StelloVault

Thanks for taking the time to contribute. Here's what you need to know.

## Getting Started

1. Fork the repo and clone your fork
2. Add the upstream remote:
   ```bash
   git remote add upstream https://github.com/anonfedora/stellovault.git
   ```
3. Create a branch from `main`:
   ```bash
   git checkout -b type/short-description
   # e.g. feat/escrow-timeout, fix/oracle-rate-limit, docs/api-readme
   ```

## Branch Naming

| Prefix | Use for |
|--------|---------|
| `feat/` | New features |
| `fix/` | Bug fixes |
| `refactor/` | Code cleanup with no behavior change |
| `docs/` | Documentation only |
| `chore/` | CI, deps, tooling |
| `contract/` | Soroban contract changes |

## Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
type(scope): short description

# Examples
feat(escrow): add release timeout mechanism
fix(oracle): handle rate limit retry correctly
contract(collateral): validate expiry on register
```

## Code Standards

### TypeScript (`server/`)

- Run `npm run lint` and `npm run format` before committing
- `tsc --noEmit` must pass — no type errors
- New endpoints need: controller + route + service layer
- Keep controllers thin; business logic lives in services

### Rust (`contracts/`)

- `cargo fmt` must be clean
- `cargo clippy -- -D warnings` must pass
- Update snapshot tests if contract behavior changes (`cargo test`)
- No `unwrap()` in production paths — use proper error handling

## Pull Requests

- Fill out the PR template completely
- Keep PRs focused — one concern per PR
- Contract changes require extra detail on interface/ABI impact
- All CI checks must pass before merge

## Reporting Issues

Use the issue templates in `.github/ISSUE_TEMPLATE/`. Check existing issues before opening a new one. For the full feature backlog, see `server/migration_issues.md`.

## Security

Do not open public issues for security vulnerabilities. Contact the maintainers directly.
