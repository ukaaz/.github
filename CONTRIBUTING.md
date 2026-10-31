# Ukaaz Contributing Guidelines

Welcome to the **Ukaaz** project! This document outlines our standard development lifecycle, branch nomenclature, and commit formatting for all contributors across both server and client repositories.

---

## 1. Branch Naming Strategy

Branches should be branched off `main` and follow this naming format:

* **Feature Branches**: `feature/<module-or-short-description>` (e.g., `feature/escrow-milestones`, `feature/bid-timer`)
* **Bug Fixes**: `fix/<short-description>` (e.g., `fix/token-refresh`, `fix/websocket-reconnect`)
* **Refactoring & Tech Debt**: `refactor/<short-description>` (e.g., `refactor/auth-pipeline`)
* **Documentation**: `docs/<short-description>`

---

## 2. Commit Message Convention

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <short description in present tense>

[optional body providing technical context]

[optional footer, e.g. Closes #123]
```

### Allowed Types
* `feat`: A new feature or endpoint
* `fix`: A bug fix
* `refactor`: Code changes that neither fix a bug nor add a feature
* `test`: Adding or updating test cases
* `perf`: Code changes that improve runtime performance
* `docs`: Documentation updates or additions
* `chore`: Build tooling, dependency bumps, or configuration changes

---

## 3. Code Standards & Toolchains

### Server (`ukaaz-server`)
* **Linter & Formatter**: Biome (`pnpm run check` or `pnpm run format`)
* **Type Safety**: Strictly typed TypeScript (`pnpm run build` / `tsc --noEmit`)
* **Database**: Migrations managed through Drizzle ORM (`pnpm run db:generate`)
* **Validation**: Runtime input validation using Zod

### Mobile (`ukaaz-mobile`)
* **Code Formatting**: `dart format --line-length 120 .`
* **Static Analysis**: `flutter analyze`
* **Architecture**: Interface-based repository pattern returning `Result<T, ApiFailure>`
* **State Management**: Riverpod with code generation (`dart run build_runner build`)

---

## 4. Pull Request Checklist

Before submitting a Pull Request:
1. Ensure your branch is rebased or up-to-date with `origin/main`.
2. Verify all local checks (linting, tests, build) pass with zero errors or warnings.
3. Keep PRs focused on a single responsibility to simplify review.
4. Provide a descriptive title and summary of changes.
