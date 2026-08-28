# Integration in Code

## Boundaries are contracts
- Every public surface — API, module export, event, schema, config — is a
  linkage point between parts. We treat public interfaces as more precious
  than implementation: they outlast it.
- **Public surface is permanent integration cost.** Every public thing we
  add is a cost paid by every other part, forever. Add with care.
- Record boundary decisions in ADRs (in the owning repo, or in this repo's
  `templates/` for cross-cutting ones). A seam chosen silently will be
  re-litigated by whoever hits it next.

## Seams are where we test
- Unit tests for parts. Integration tests for seams. End-to-end for the
  critical path. All three; each answers a different question.
- Test boundary behavior specifically: error paths, timeouts, partial
  failure, concurrent use, bad input from a real consumer.
- **Green CI with red production means we tested the parts, not the seams.**

## Shorten the feedback loops
- The goal is the shortest honest path from change to signal:
  typecheck → lint → unit → integration → deploy → metrics.
- Each layer must answer a *different* question, or it's ceremony.
- Observability (logs, metrics, traces) is the production feedback loop.
  New seams get instrumentation by default, not as follow-up.

## Coupling discipline
- Minimize coupling, but preserve necessary coupling. We cut coupling to
  *maintain* a boundary, not to create one.
- Watch both failure modes:
  - **Under-differentiation:** the [god module](./anti-patterns.md) — one part
    everyone depends on, nothing testable in isolation.
  - **Over-differentiation:** the [distributed monolith](./anti-patterns.md)
    — many parts, no integration; every change touches five services.
- Prefer few stable interfaces over many unstable ones.

## Judge the whole
- Performance, reliability, security, and UX are emergent. They only exist
  in the integrated system.
- Verify with the system: load tests, end-to-end flows with realistic data,
  real users. "My function is fast" is not a system property.

## Definition of Done (integration clauses)
- Works in context, not in isolation.
- Seams tested; failure paths exercised.
- Observable: we can tell it worked, and we can tell when it fails.
- Contracts documented; dependents notified before changes ship.
- No silent assumptions across boundaries.
- The [three tests](./START-HERE.md) are run and recorded: closed-loop?
  copy-paste? whole-person?
