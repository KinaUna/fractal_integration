# Review Ritual — when a logged lesson earns a change here

[`review-cadence.md`](review-cadence.md) answers *when to hold a review*
— which template fits a closed task, a milestone, a finished project, a
broken seam. It deliberately leaves one question open: whether what a
review turns up should change *these guidelines*, not just the project
it came from. This doc is that question.

Without an answer, a log of seams and FACES scores
([`templates/log-template.md`](templates/log-template.md)) drifts toward
one of two named failures: **signals without loops** — entries pile up,
nothing acts on them — or **reflection without actuation** — a review
happens, nothing gets edited, nothing recorded as to why not.

## Three tiers of trigger

**Capture-only — always waits for the next scheduled review.**
A closed task, a milestone (`templates/retrospective.md`), ordinary
circumstances-change (`templates/postmortem.md`, or a reopened
`templates/design-doc.md`). These write to the log and stop there. No
edit to your guidelines, no changelog entry, at the moment they happen.

**Direct promotion — allowed immediately, capped at MINOR/PATCH.**
A project-completed retro, or a first-adoption-into-a-new-domain moment.
Both are infrequent, and both are the triggers most likely to produce
something purely additive — a new domain, anti-pattern, template, or
domain guide — rather than a rename or restructure. If one of these
surfaces something that would actually need a MAJOR change, log it and
**defer it to the next scheduled review** instead of shipping it in the
moment. A MAJOR made in the afterglow of finishing a project is a
worse-quality decision than the same MAJOR made on schedule with the
whole log in view.

**Escape hatch — uncapped, bypasses the calendar entirely.**
A circumstances-change severe enough to be postmortem-worthy *and*
recurring across more than one system, or `log-schema.json`'s own
repeated-`other` threshold (three `other` values logged against the same
field). Both can justify a MAJOR immediately — the equivalent of an
incident fix that doesn't wait for a release train.

## The scheduled core review

This is the default sweep — the one that runs even when nothing urgent
has happened, so drift doesn't happen by default. Pick a cadence and
commit to it somewhere visible (quarterly is a reasonable default, and
matches this repo's own).

1. Pull every log entry (`seam` and `faces`) dated since the last review.
2. Group by `domain`, `anti_pattern`, and `system`.
3. Apply the promotion test: recurs across **≥2 systems**, or recurred
   **≥2 times within one completed project's own arc** (a project
   retro's widened view supplies its own internal recurrence, even
   without a second system), or was **severe enough alone**.
4. For anything that clears the bar, decide MAJOR / MINOR / PATCH — see
   `CHANGELOG.md`'s versioning policy if you've adopted this repo's
   scheme, or your own equivalent.
5. Write the edit, write the changelog entry (cite the log entry `id`(s)
   that prompted it), bump the version, tag it.
6. If nothing clears the bar: say so, even in one line, somewhere
   durable. "Reviewed 2026-Q4, nothing promoted" is a recorded decision.
   Silence is indistinguishable from having skipped the review entirely,
   and only one of those is fine.

**Owner:** whoever maintains this copy of the guidelines. If that's you,
alone, the real failure mode to design against isn't a bad decision made
at review time — it's the review not happening at all. Calendar it or
set a reminder rather than trusting it'll come to mind. If more than one
person maintains this copy, name someone.

## What this doesn't touch

The log's own schema evolves by its own rule — the `other` escape-valve
logic in `templates/log-template.md`. This ritual consumes the log, it
doesn't version it. And most reviews, scheduled or triggered, should
promote nothing — that's the expected outcome, not a sign the ritual
isn't working.
