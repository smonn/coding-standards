# Guide to the coding standards

[CODING_STANDARDS.md](CODING_STANDARDS.md) is the complete policy and takes precedence if the two documents disagree. This optional guide explains existing choices and supplies extra examples; it adds no rules or exceptions. Downstream repositories can use the standards without copying this guide.

The sections follow the standards, collecting their longer explanations and extra examples.

## Purpose and scope

[Standards](CODING_STANDARDS.md#purpose-and-scope)

SOC 2, HIPAA, PCI DSS, and GDPR illustrate audit and regulatory regimes.

## Design principles

[Standards](CODING_STANDARDS.md#design-principles)

Two similar blocks are cheaper than a wrong abstraction. A module whose interface is as complex as its body adds cost without hiding anything.

## Architecture

[Standards](CODING_STANDARDS.md#architecture)

Most rules in Testing follow from functional core, imperative shell. The core is the main value of the software; dependencies there tie that value to someone else's releases, licensing, and security. Mapping database rows and ORM entities to domain objects isolates schema changes.

The shell supplies values such as current time, a generated ID, or a seed. External dependencies behind ports include databases, IdPs, email, payments, and queues.

## Contracts and migrations

[Standards](CODING_STANDARDS.md#contracts-and-migrations)

Plain SQL migration files and a language-agnostic runner let the schema outlive any one language, framework, or ORM.

## Background work and integrations

[Standards](CODING_STANDARDS.md#background-work-and-integrations)

Email, file and media processing, and bulk jobs are examples of work that can run after the response when the response does not depend on their completion.

## Infrastructure and deployment

[Standards](CODING_STANDARDS.md#infrastructure-and-deployment)

OpenTofu and Terraform are examples of infrastructure-as-code tools.

## Code organization

[Standards](CODING_STANDARDS.md#code-organization)

`controllers/`, `services/`, and `models/` are examples of technical directory groupings, as opposed to a domain such as `billing/`.

## Testing

[Standards](CODING_STANDARDS.md#testing)

A real filesystem or test account offers further examples of real dependencies for shell integration tests. Property-based tests also suit invariants such as idempotence and monotonicity, alongside roundtrips.

## Static analysis and deterministic checks

[Standards](CODING_STANDARDS.md#static-analysis-and-deterministic-checks)

Toolchain version files include `rust-toolchain.toml` and the `toolchain` line in `go.mod`, alongside `.nvmrc` for Node.js. Warnings that never fail the build become noise.

## Dependencies

[Standards](CODING_STANDARDS.md#dependencies)

`Cargo.lock` is another ecosystem lockfile. Renovate and Dependabot offer scheduled dependency-update PRs; grouping automated updates reduces review load.

## Security

[Standards](CODING_STANDARDS.md#security)

Layered controls are also called defense in depth. bcrypt is another example of a slow, salted password-hashing algorithm, alongside Argon2id.

## UI

[Standards](CODING_STANDARDS.md#ui)

Input types include `number`, `date`, `tel`, and `url`, as well as `email`; these select appropriate keyboards and browser validation. Restructured fields are another example of meaning-preserving API shape changes. Cypress offers another real-browser end-to-end testing option alongside Playwright.

## Scope and change discipline

[Standards](CODING_STANDARDS.md#scope-and-change-discipline)

Shipping a new API with a usage lets reviewers see how it is used and avoids landing unused APIs.

## Version control and PRs

[Standards](CODING_STANDARDS.md#version-control-and-prs)

Shared issue and PR templates make each contribution cover the same aspects.

## Review

[Standards](CODING_STANDARDS.md#review)

Google warns that cleaning up later is a common way for codebases to degrade. The local exception process records the decision to accept technical debt instead of relying on that promise alone.

The [Refactoring catalog](https://refactoring.com/catalog/) provides names for discussing code smells: Primitive Obsession, Data Clumps, Feature Envy, and Shotgun Surgery. These names provide shared vocabulary.

## CRAP scoring

[Standards](CODING_STANDARDS.md#shared-checks)

[CRAP](https://www.artima.com/weblogs/viewpost.jsp?thread=210575) (Change Risk Anti-Patterns; Savoia and Evans, 2007) combines cyclomatic complexity and coverage:

`complexity² × (1 − coverage)³ + complexity`

Coverage ranges from 0 to 1. The formula uses cyclomatic complexity; Rust's cognitive-complexity score measures something different.

## TypeScript

[Standards](CODING_STANDARDS.md#typescript)

Unlike `@ts-ignore`, `@ts-expect-error` fails once the directive is no longer needed. That makes an obsolete suppression visible.
