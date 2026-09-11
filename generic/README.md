# Fractal Integration, how I think about it

It has come to my attention that most of what goes wrong in systems, be it code, products, teams, my own life, goes wrong at the seams, not inside the parts. So let me try to write down what I mean by that.

A system, as I'm using the word here, is just differentiated parts whose combined functioning does something no single part can do alone. Integration is the linkage between those parts. That pattern, split things up, then wire them back together, seems to repeat at every scale, from a function to a service to a product to a team, even to life itself. That's why I've started calling this Fractal Integration, and the docs and templates in this folder that try to turn it into something usable, the Fractal Integration Guidelines (FIG).

For a quick introduction, **Start here:** [`START-HERE.md`](START-HERE.md)

## How I think about it

I think this applies to more or less any differentiated system I can point to: a piece of work, code (modules, services, APIs), a product (features, onboarding, users, market), a team, an organization, and the lives all of that touches. I don't see why any profession couldn't apply the same thinking and `START-HERE.md` has a rough recipe for writing a domain guide, if you work in HR or accounting or something else entirely.

Here's roughly where my head is at now:

Quality, as far as I can tell, is mostly the quality of the linkage. A system isn't the sum of its parts, it's the wiring between them, and most of the failures I've actually dealt with turned out to be integration failures I mistook for component-failures.

Improving differentiation requires awareness and deliberate choices, and integration is the effort and work that follows from those choices. Splitting things into modules and services and roles on purpose is fairly easy. But parts sitting next to each other without linkage is just fragmentation with extra steps. Every boundary I draw is a place where I now owe the system some integration: designed, tested, maintained.

Bugs and value seem to live in the same place: the seams. The riskiest and most valuable behavior of the things I've worked on and built happens where parts meet, not inside them. So that's where I try to improve the most, to test and observe and invest first.

Feedback loops aren't a nice-to-have, they're what lets a system learn it's wrong. I try to build the shortest honest path from a change to a signal about that change: tests, CI, observability in code; metrics, support, research in product. A loop nobody owns and nobody acts on isn't really a loop.

Emergent properties can't be delegated to a part. Trust, retention, performance, reliability, whatever "goodness" means for the thing I'm building, only exist in the whole, integrated system. I can't assign them to one feature or one person and expect that to work effectively, so I will try not to.

Entropy is inevitable, so integration decays if I don't maintain it. Contracts drift, tests go stale, assumptions turn into tribal knowledge nobody wrote down, skills atrophy. Refactoring, review, postmortems, retrospectives — that's how I will try to keep up with the decay, not eliminate it, because I don't think it can be eliminated.

## Where each doc fits

**The core (domain-neutral)**

- **Onboarding:** read [`START-HERE.md`](START-HERE.md) top to bottom — that *is* the
  onboarding.
- **In plain language:** [`everyday-life.md`](everyday-life.md) — the same ideas told
  with everyday examples, for readers who don't live in the codebase.
  For more to choose from, matched to different backgrounds, see
  [`examples/`](examples/README.md).
- **How it fails:** [`anti-patterns.md`](anti-patterns.md) — my running catalog of integration
  failures, and what I try to do instead.
- **The human system:** [`the-human-system.md`](the-human-system.md) is the outermost scale I've
  thought about. It applies to how I work and to the lives that work touches.
- **A lens for diagnosing failures:** [`domains-of-integration.md`](domains-of-integration.md) maps nine
  ways the mind integrates (from Siegel's Interpersonal Neurobiology) onto
  the systems I build. When something feels wrong but nothing is technically
  "broken," this is how I try to name what's failing.

**Applying it to a domain** — the same principles turned into a field's
practices. Code and product are the two I've actually written up; a
profession (HR, accounting, operations…) could add its own in the same shape:

- **Product work:** start with [`product-as-integrator.md`](product-as-integrator.md). It's where I try
  to justify why the product exists at all, in these terms.
- **How I build code:** [`in-code.md`](in-code.md) — the principles turned into practice.

**Using it in the work**

- **Every review and retro:** three questions I ask myself — is the loop
  closed, is the handoff clean, am I looking at the part or the whole —
  plus a FACES score, the five faces of a healthy system (details in
  [`START-HERE.md`](START-HERE.md)).
- **Design reviews:** I use [`templates/design-doc.md`](templates/design-doc.md). The "Seams &
  contracts" section isn't optional for me.
- **PRs:** the integration checkbox in the PR template (in each product
  repo) isn't optional either.
- **Incidents:** [`templates/postmortem.md`](templates/postmortem.md).
- **Retrospectives:** [`templates/retrospective.md`](templates/retrospective.md).

This document is itself a system I haven't finished integrating. I try to
come back to it now and then and ask what my actual practice has shown to
be true, false, or just missing.
