# AGENTS.md — BenchCommons

Rules for AI agents and automation working in any BenchCommons repository. Each repo's own `AGENTS.md` adds repo-specific stack and runbooks and takes precedence for that repo.

## Orientation
- Read the repo's `README.md`, its `AGENTS.md` and `docs/specs/` before changing anything.
- Org context lives in [.product](https://github.com/BenchCommons/.product): `ROADMAP.md`, `CONTRACTS.md` and `docs/adr/`.
- Repo roles follow ADR 0001: `catalog-*` holds implementations, `dataset-*` holds inputs; tools, sites and dot repos are the governance.

## Spec-driven development
- Write the spec before the code: `docs/specs/<NNN>-<feature>/{spec,plan,tasks}.md`. One spec per feature, one plan per spec.
- Break large initiatives down in a short `ROADMAP.md` that only lists the child specs.
- Specify a contract between repos only in its owner repo, and link to it from consumers.
- Isolated decisions go in ADRs (`docs/adr/NNNN-title.md`, Nygard format).

## Git
- Use Conventional Commits. Never push to the default branch; open a pull request.
- Never bypass commit signing or rewrite the author. AI co-authorship goes only in a `Co-Authored-By:` trailer.
- Work in branches or worktrees. Remove temporary worktrees (`git worktree remove`, `git worktree prune`) when done.

## Safety
- Before deleting anything (files, branches, repos, images), list exactly what will be deleted and why, and get explicit approval for that list.
- Transfers, renames, visibility changes and other org-level actions need explicit maintainer approval.
- Open items go in issues with checklists, not in docs, code comments or published content.

## Benchmarks
- Use real implementations only. Never fake output or measurements.
- Pin versions, use deterministic inputs, and verify correctness before measuring.
- Report measurements together with their environment. Energy (RAPL) needs bare metal; hosted CI provides only time and memory.
