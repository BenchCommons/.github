# Contributing to BenchCommons

Thank you for helping. These rules apply to every BenchCommons repo unless the repo has its own CONTRIBUTING.md.

## Before you start
- Read the repo's `README.md` and `AGENTS.md`. Org decisions are in [.product](https://github.com/BenchCommons/.product).
- Look for an existing issue. Open one before large changes.

## Specs first
Features and structural changes start with a spec in `docs/specs/<NNN>-<feature>/`:
- `spec.md`: what and why, acceptance criteria, out of scope.
- `plan.md`: how, contracts, decisions.
- `tasks.md`: incremental, testable steps.

One spec covers one feature, and one spec has one plan. A contract between repos is specified once, in the owner repo (see [CONTRACTS.md](https://github.com/BenchCommons/.product/blob/main/CONTRACTS.md)). Cross-repo decisions are ADRs in `.product`.

## Commits and pull requests
- [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `docs:`, `test:`, `ci:`, `chore:`, with an optional scope.
- Signed commits are preferred.
- Open pull requests against the default branch. Never push to it directly.
- Keep each PR focused, and make sure CI passes.
- Open items go in issues with a checklist, not in docs or code comments.

## Benchmarks
- Pin every version: images, packages and tools.
- Inputs must be deterministic, and the expected output is verified before anything is measured.
- Publish raw results together with the environment they came from.
