# When to Review — matching the ritual to the scope

> Principle 6 says integration decays without review. It doesn't say every
> review is the same size. Running a full retro on a single closed task is
> ceremony nobody sustains; treating a finished project like just another
> sprint is the opposite mistake — you skip the one question only a
> finished project can answer.

## The template already flexes — the trigger is what's been missing

[`templates/retrospective.md`](templates/retrospective.md) is titled
"Retro — **[cycle]**" on purpose. It never defines what a cycle is,
because it isn't one size — a cycle can be a sprint, a shipped feature, or
a whole project, and the template holds at every size. What's actually
been missing isn't a bigger toolbox, it's a rule for which trigger gets
which response, so the smallest, most frequent triggers don't drown in
ceremony and the largest, rarest ones don't get short-changed by it.

## The triggers

**A task closes.** Too small and too frequent for a retro. There's no
template for this — just ask, in passing, whether a seam surprised you
while doing it. If yes, log it wherever you keep track of seams. If no,
that's the expected outcome for most tasks; a system that logs every
closed task has stopped distinguishing signal from noise.

**A milestone is reached** — a sprint ends, a feature ships, whatever you
already treat as a natural checkpoint. This is exactly what
`retrospective.md`'s "[cycle]" means. Run it as written: seam failures,
FACES score, one integration move.

**A project is completed.** Same template, widened to the project's whole
arc instead of one cycle of it — plus one question the smaller sizes don't
need: hand this to a successor next month. What do they inherit, and what
would they have to re-learn? That's transpirational integration (domain
9 in [`domains-of-integration.md`](domains-of-integration.md)), and a
finished project is the one moment it's actually answerable — mid-project,
there's no "next generation" yet to hand anything to.

**Something breaks.** [`templates/postmortem.md`](templates/postmortem.md),
unchanged — this is exactly what it's for.

**Circumstances change, but nothing broke** — a constraint shifts, new
information arrives, a dependency changes underneath you. This isn't a
retro or a postmortem; it's a reason to reopen the relevant
[`templates/design-doc.md`](templates/design-doc.md) and re-run it against
the new ground, not to review what already happened.

**You're applying this somewhere new for the first time** — a new
project, a new domain, a new team. Also closer to `design-doc.md` in
spirit than to a retro: forward-looking, checking fit before problems
accumulate, rather than looking back at problems that already did.

## What this doesn't cover

Whether a particular review's findings warrant a change to *these
guidelines themselves* — not just to the project they came from — is a
separate question from when to hold the review. See
[`review-ritual.md`](review-ritual.md) for that: the promotion tiers,
the scheduled core review, and the criteria for when a logged lesson
earns an edit here rather than staying a private note.