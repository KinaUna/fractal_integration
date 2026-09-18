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

## [1.3.0] - 2026-09-18

### Added

- `landed` and `landed_date` on seam entries (`log-schema.json`,
  `log-template.md`) — orthogonal to `status`: a seam can be
  `status: closed` (the fix is done and verified) while still
  `landed: branch` (not yet merged to the trunk, let alone deployed).
  Surfaced by the first real entries logged against Kumunita: work there
  happens on a long-lived `release` branch not yet reconciled with `main`,
  and `status: closed` alone couldn't say whether "closed" meant "closed
  on a branch" or "closed and live." A gap surfaced by first use — the
  loop the versioning policy above describes, closing.

Pure addition, nothing renamed or restructured — MINOR.

## [1.2.0] - 2026-09-17

### Added

- `generic/templates/log-schema.json` and `generic/templates/log-template.md`
  — the log format `retrospective.md` and `postmortem.md` have referenced
  since `1.0.0` ("log each in the seam log") without it existing anywhere
  in this repo. Previously drafted as private, maintainer-only material;
  moved here because the schema and template hold no personal data — only
  the entries you'd write with them do — so there was no real reason to
  keep them out of the public, forkable core.
- `generic/review-ritual.md` — when a lesson logged through the above
  earns an edit to these guidelines rather than staying a private note:
  the promotion tiers, the scheduled core review, and the promotion
  criteria. Fills in the question `review-cadence.md` (1.1.0) explicitly
  deferred.

### Changed

- `templates/retrospective.md` and `templates/postmortem.md` now link
  "the seam log" to `log-template.md` / `log-schema.json` instead of
  naming an artifact with no destination. Wording only, nothing renamed
  or restructured.

Pure addition plus a clarity fix — nothing renamed, nothing restructured
— MINOR.

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