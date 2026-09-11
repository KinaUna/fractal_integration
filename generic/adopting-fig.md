# Adopting FIG in Your Own Project

> This doc is for when these guidelines stop being something you read and
> start being something you copy — into a repo, a wiki, a team handbook, or
> a prompt you hand an AI agent. It answers: how do you make them yours
> without losing the link back to here?

## Adopting this is itself an integration problem

The moment you copy any of this into your own project, you've done exactly
what principle 2 describes: you differentiated a part on purpose (your
local copy) out of a whole (this repo). That copy now needs to be
integrated — with your project's language, and, over time, with whatever
this source repo becomes next. Skip that second half and you've made
**exactly the anti-pattern this repo warns about**: a copy that drifts from
its source with nobody tracking why, which is [`accidental
integration`](./anti-patterns.md) — or, worse, [`silent
coupling`](./anti-patterns.md) — your team relying on a version of FIG that
no longer matches the one anyone else is reading.

There are two easy ways to get this wrong, and one steady way to get it
right.

**Wrong: copy-paste and forget.** You paste [`START-HERE.md`](./START-HERE.md) into your
wiki once. It's useful for a month, then this source repo moves on —
a principle gets sharpened, a new domain guide ships, an anti-pattern gets
renamed — and your copy quietly becomes a fork nobody meant to create.
Six months later someone asks "wait, is this still current?" and no one
can answer. This is [`integration decays`](./README.md) (principle 6),
applied to the guidelines about integration decaying.

**Also wrong: blind overwrite.** You script a pull that replaces your
local docs with source verbatim on every sync. This destroys the thing you
actually wanted — the domain-specific guide you wrote for *your* field,
which this repo explicitly expects you to add (see ["Applying it to your
domain"](./START-HERE.md#applying-it-to-your-domain) in [`START-HERE.md`](./START-HERE.md)) and which the source repo has no way to know
about.

**Right: a designed seam.** Treat your local copy the way [`in-code.md`](./in-code.md)
tells you to treat any boundary — a contract, not an accident:

1. **Keep the core, differentiate around it.** Pull the domain-neutral
   core ([`README.md`](./README.md), [`START-HERE.md`](./START-HERE.md), [`anti-patterns.md`](./anti-patterns.md),
   [`domains-of-integration.md`](./domains-of-integration.md), [`the-human-system.md`](./the-human-system.md), [`everyday-life.md`](./everyday-life.md),
   [`templates/`](templates/)) close to verbatim. Write your own domain guide — HR,
   accounting, your specific codebase's conventions, whatever your field
   is — as a new file alongside them, in the shape of [`in-code.md`](./in-code.md) or
   [`product-as-integrator.md`](./product-as-integrator.md). That split is the seam: the core is what
   you sync, the domain guide is what you own.
2. **Record what you pulled and when.** At the top of your local copy
   (a comment, a short `SOURCE.md`, or a line in your README), note the
   source repo, the commit or tag you're synced to, and the date. This is
   the "memory" domain applied to your own adoption — an explicit artifact
   that says *why* your docs look the way they do, instead of leaving that
   only in someone's head.
3. **Note your deliberate deviations.** If you trim a section or reword
   something for your team, say so in one line next to it (`<!-- local:
   trimmed the templates section, we use Linear's own retro doc -->`).
   That turns an overwrite risk into a diff you can read at a glance.
4. **Re-sync on a cadence, not never.** This repo's own docs are reviewed
   quarterly (see the closing line of [`README.md`](./README.md)). Put your adoption on
   the same rhythm: once a quarter, diff your local core docs against this
   source, pull in what changed, and re-check your deviations still make
   sense. A sync loop with no cadence is [`reflection without
   actuation`](./anti-patterns.md) waiting to happen.

## Doing this with an AI agent

This is designed to be adopted by an agent, not just a person — that's part
of why it lives in a plain, public, well-structured repo instead of a
slide deck. A reasonable prompt:

> Read `README.md` and `START-HERE.md` from
> `https://github.com/KinaUna/fractal_integration`. Add a domain guide for
> [your field/project] in the same shape as `in-code.md`: the six
> principles turned into our practices. Copy the core docs in as-is, note
> the commit you synced from, and leave our project-specific conventions
> out of the core files — they belong in the new domain guide.

For a codebase, the mechanical version of "keep the core, differentiate
around it" is whatever your tooling already gives you for tracking an
external source at a point in time — a git submodule or subtree pointed at
this repo, or simply a pinned commit hash recorded in the file the agent
creates. None of that is required; a dated note is enough to start. The
point isn't the tooling, it's that the link back to source is a designed,
visible thing — not an assumption.

## Adoption checklist

- [ ] Core docs copied in, close to verbatim.
- [ ] A domain guide written for your specific field or project.
- [ ] Source commit/tag and date recorded somewhere visible.
- [ ] Any deliberate local deviations noted inline.
- [ ] A re-sync cadence set (quarterly, matching this repo's own review
      cycle, is a reasonable default).

That's the whole pattern: differentiate deliberately, link back
explicitly, and revisit on a schedule. It's principles 1, 2, and 6 of
[`README.md`](./README.md), pointed at the guidelines themselves.