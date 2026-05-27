<p align="center">
  <img src="https://raw.githubusercontent.com/ym-actions/.github/main/logo.png" alt="ym-actions Logo" width="300" />
</p>

<p align="center">
  <strong>Reusable GitHub Actions ecosystem for building composable CI/CD workflows.</strong>
</p>

<p align="center">
  <a href="https://github.com/ym-actions/.github/blob/main/LICENSE"><img src="https://img.shields.io/github/license/ym-actions/.github?style=flat-square&color=blue" alt="License" /></a>
  <a href="https://github.com/ym-actions"><img src="https://img.shields.io/badge/workflows-reusable-success?style=flat-square&color=8A2BE2" alt="Reusable Workflows" /></a>

</p>

---

## ⚙️ Overview

`ym-actions` is a curated collection of reusable GitHub Actions workflows designed to eliminate duplicated CI/CD logic across repositories. It provides modular, versioned, and highly optimized building blocks for automation, including testing, coverage reporting, formatting, and static analysis.

Each action in the ecosystem is:

- **Zero-Config by Default:** Works out of the box with sensible defaults for Laravel and PHP.
- **Highly Configurable:** Customize PHP versions, extensions, asset building, and thresholds.
- **Versioned for Stability:** Target major tags (e.g., `@1.x`) to receive updates without breaking changes.
- **Composable:** Combine multiple actions to build your ideal pipeline without bloated monolithic scripts.

---

## 🧱 The Ecosystem

Here are the active actions available in the `ym-actions` organization:

| Action / Workflow                                                                        | Description                                                                           | Primary Stack |
| :--------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------ | :------------ |
| [**`laravel-coverage-comment`**](https://github.com/ym-actions/laravel-coverage-comment) | Runs Pest test suite, parses coverage, and posts interactive summary comments on PRs. | Laravel / PHP |
| `php-pest-runner`                                                                        | Optimized Pest unit testing workflow with parallel execution support.                 | PHP / Pest    |
| `phpstan-analysis`                                                                       | Runs PHPStan static analysis with configurable rule levels and cache.                 | PHP / PHPStan |
| `pint-formatter`                                                                         | Validates and auto-formats PHP code using Laravel Pint.                               | Laravel / PHP |
| `deploy-actions`                                                                         | Handles streamlined deployments to staging and production environments.               | Multi-stack   |

---

## 🧠 Philosophy

Our ecosystem is guided by five core principles:

1. **Reuse over Duplication:** CI configurations should not be copy-pasted across your projects. Fix bugs or add features in one place, and let all projects inherit the updates.
2. **Composability:** Write small, single-purpose workflows that do one job exceptionally well. Combine them in your main workflow file.
3. **Explicit Versioning:** Consumers maintain complete control over upgrades by pinning to major version branches (e.g., `@1.x`).
4. **Stability over Churn:** Breaking changes are strictly isolated to new major versions (e.g., `@2.x`). We never introduce silent breaking changes.
5. **Practical Engineering:** No unnecessary abstractions. We use native actions and standard tools to keep workflow runtimes fast and easy to debug.

---

## ⚡ Usage Pattern

To consume workflows from the ecosystem, reference them using GitHub's reusable workflow syntax:

```yaml
jobs:
  tests:
    uses: ym-actions/laravel-coverage-comment/.github/workflows/main.yml@1.x
    permissions:
      contents: read
      pull-requests: write
    with:
      min-coverage: 80
      fail-on-low-coverage: true
```

---

## 🔢 Versioning Strategy

All workflows follow semantic major version branches:

- `1.x` — Stable, active major line. Receives non-breaking updates, performance improvements, and bug fixes.
- `2.x` — Next major version. Reserved for breaking changes.
- `main` — Active development and testing. **Not recommended for production workflows.**

Pin your configurations to major branches to stay up-to-date safely:

```yaml
@1.x
```

---

## 🤝 Contributing

We welcome contributions to improve workflow performance, expand stack support, or enhance documentation. Please check individual repository contribution guides for details.

---

## 📄 License

The workflows and configurations in this organization are open-sourced under the [MIT License](../LICENSE).
