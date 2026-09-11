# Anti-patterns

The eight failures below are **domain-general** — any differentiated system
can suffer them, from a workflow to a codebase to a department. Each domain
guide (e.g. [`in-code.md`](in-code.md)) adds its own concrete examples on top of these.

| Name | What it looks like | The fix |
|---|---|---|
| **Part sprawl** | Parts accumulate with no linkage; the whole is a bag of parts (features, tasks, roles, rules) nobody can navigate. | Every new part states which seam it integrates. Prune parts that don't connect. |
| **The god part** | Under-differentiation: one part everyone depends on — a person, a process, a component — nothing can be tested or changed in isolation. | Find the stable contract; split on it. Give the part a boundary and an owner. |
| **Distributed fragmentation** | Over-differentiation: many parts, no integration; every change touches five of them (services, teams, forms, steps). | Re-differentiate on real seams; merge what always changes together. |
| **Parts work, seams don't** | Every part passes its own checks, but the handoff between parts fails (in code: green CI, red production). | Test and observe the seams, not just the parts; instrument the boundaries. |
| **Signals without loops** | Dashboards, reports, or reviews nobody acts on; the signal goes nowhere. | Every signal gets an owner, a threshold, a response action. |
| **Accidental integration** | It works, but nobody knows why; the linkage lives in tribal knowledge. | Make the linkage explicit: contracts, tests, ADRs, documented procedures. |
| **Silent coupling** | Undocumented assumptions between parts or teams; one side changes and the other breaks, or silently degrades. | Explicit, versioned agreements; migrate dependents deliberately. |
| **Reflection without actuation** | Retros, reviews, postmortems with no follow-through; the loop has no actuator. | Every action gets an owner and a deadline; the next review starts by verifying the last ones closed. |

## Reading the table in your domain

The same eight names appear in every field, wearing different clothes:
in code they are *green CI, red production* and the *god module*; in an
HR process they might be *the one manager who knows everything* or *the
intake form that loses the applicant between stages*. Name the failure
with the general name first, then the local one — the general name is
what keeps the diagnosis portable.

## Domain catalogs

Each domain guide carries its own anti-pattern catalog, built on these:
same eight skeletons, field-specific symptoms and fixes. When a failure
keeps recurring in one domain, record it there — that's principle 6
working: the loop closes where the work happens.
