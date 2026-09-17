# Changelog

All notable changes to the Fractal Integration Guidelines (FIG) are recorded
here, newest first.

## Versioning

A version number here isn't a measure of how much prose changed — it's
whether something you can *reference by name* still means the same thing.
The stable surface is: the 21 domain slugs and 8 anti-pattern slugs (used
verbatim by anything integrating against `domains-of-integration.md` /
`anti-patterns.md`, including any log or tool that stores those names in an
enum), the six principles and their numbering (cited elsewhere as
"principle 2," "principle 6," and so on), the FACES letters, and the
core/domain-application file structure that [`adopting-fig.md`](generic/adopting-fig.md)
tells forks to sync against.

- **MAJOR** — a slug renamed or removed, a principle renumbered, FACES
  redefined, or the file structure reorganized. Anything that could
  silently break a cross-reference, a fork's own domain guide, or a tool's
  enum. Check your local deviations before pulling.
- **MINOR** — additive and backward-compatible: a new domain, a new
  anti-pattern, a new template, a new domain-application guide (e.g. a
  future `in-hr.md`), expanded guidance inside an existing section. Safe to
  pull without review.
- **PATCH** — wording, clarity, examples, typo fixes. No name, number, or
  structure changes. Always safe to pull.

Where a change was prompted by a specific lesson from using FIG elsewhere —
a repeated seam, a recurring `other` — the entry below says so. That's the
loop from practice back to the guidelines, closing.

## [1.1.0] - 2026-09-17

### Added

- `generic/review-cadence.md` — maps review triggers (a task closing, a
  milestone, a completed project, a broken seam, a circumstances change,
  first adoption somewhere new) to the existing templates, so
  `retrospective.md`'s deliberately undefined "[cycle]" has a stated rule
  for what counts as one. Cross-linked from `START-HERE.md`'s reading
  order and "Where the tools live."

Pure addition, nothing renamed or restructured — MINOR. This entry is
also the first real use of the versioning scheme itself: no
project-level lesson prompted it, it's a direct addition to the core
during the same review that designed the scheme.

## [1.0.0] - 2026-09-17

First tracked version. Everything before this point — from "Initial
commit" through the README repository-structure update — is untracked
prior history. Treat `1.0.0` as the baseline to sync against from here on;
[`adopting-fig.md`](generic/adopting-fig.md) has been updated to record a
version instead of a raw commit hash.

### Added

- `generic/` domain-neutral core: `README.md`, `START-HERE.md`,
  `domains-of-integration.md` (21 domains), `anti-patterns.md` (8
  anti-patterns), `the-human-system.md`, `everyday-life.md`, `examples/`,
  `further-reading.md`, `templates/` (design-doc, postmortem,
  retrospective).
- Domain applications: `in-code.md`, `in-product.md`,
  `product-as-integrator.md`.
- `adopting-fig.md` — how forks sync against this source.
- Root `README.md` with repository structure and license (CC BY 4.0).