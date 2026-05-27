# ym-actions

Reusable GitHub Actions ecosystem for building composable CI/CD workflows.

## Overview

`ym-actions` is a collection of reusable GitHub Actions workflows designed to eliminate duplicated CI logic across repositories.

It provides modular, versioned building blocks for automation on GitHub, including testing, linting, coverage reporting, analysis, and deployment helpers.

Each action is designed to be:

- Reusable across multiple repositories
- Versioned for stability and controlled upgrades
- Opinionated but lightweight
- Composable rather than monolithic

---

## Philosophy

This organisation follows a few core principles:

### 1. Reuse over duplication
CI logic should not be copy-pasted across projects.

### 2. Composability over monoliths
Each workflow should do one job well and be combined with others.

### 3. Explicit versioning
Consumers should control upgrades via versioned references (e.g. `1.x`, `v1`).

### 4. Stability over churn
Breaking changes are isolated into new major versions, not silently introduced.

### 5. Practical engineering
No over-abstraction. No unnecessary complexity. Just reliable CI building blocks.

---

## Structure

Each repository under this organisation represents a single CI capability or workflow domain.

Examples include:

- `laravel-coverage-comment`
- `php-pest-runner`
- `phpstan-analysis`
- `pint-formatter`
- `deploy-actions`

Each repo contains one or more reusable workflows designed for a single responsibility.

---

## Usage Pattern

All workflows are consumed via GitHub’s reusable workflow system:

```yaml id="usage-example"
jobs:
  ci:
    uses: ym-actions/laravel-coverage-comment/.github/workflows/main.yml@1.x
    secrets: inherit
