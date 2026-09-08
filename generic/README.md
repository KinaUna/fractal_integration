# Fractal Integration — Our Philosophy

We define a system as differentiated parts whose integrated functioning
produces properties no part has on its own. Integration is the linkage
of those differentiated parts. Because that linkage repeats at every scale
— from a function to a service to a product to a team to a life — we call
the philosophy **Fractal Integration**, and the docs and templates in this
folder that operationalize it the **Fractal Integration Guidelines (FIG)**.

👉 **Start here:** [`START-HERE.md`](START-HERE.md) — one argument, one hour.

## How we think

We apply this to any differentiated system: a piece of work, code (modules,
services, APIs), a product (features, onboarding, users, market), a team,
an organization — and to the lives the work touches. Any profession can
apply it the same way; `START-HERE.md` has a recipe for writing a domain
guide for a field like HR or accounting.
We hold:

1. **Quality is the quality of the linkage.** A system's competence is
   not the sum of its parts; it's the quality of the wiring between them.
   Most failures are integration failures, not component failures.

2. **Differentiation is deliberate, integration is the work.** We split
   modules, services, and roles on purpose. But parts without linkage are
   fragmentation. Every boundary we create is a place where integration
   must now be designed, tested, and maintained.

3. **Bugs and value both live at the seams.** The highest-risk and
   highest-value behavior happens where parts meet, not inside parts.
   We test, observe, and invest there first.

4. **Feedback loops are a feature.** A system that can't signal when it's
   wrong can't learn. We build the shortest honest path from change to
   signal — in code (tests, CI, observability) and in product (metrics,
   support, research). Every loop needs an owner and a response action.

5. **Emergent properties can't be delegated.** Trust, retention,
   performance, reliability, "goodness" exist only in the integrated
   whole. They are not assignable to a single feature, service, or person.
   We judge the system, not the part.

6. **Integration decays.** Without maintenance, linkage rots: contracts
   drift, tests go stale, assumptions become tribal knowledge, skills
   atrophy. Refactoring, review, postmortems, and retrospectives are
   how we close that decay.

## Where each doc fits

**The core (domain-neutral)**

- **Onboarding:** read `START-HERE.md` top to bottom — that *is* the
  onboarding.
- **In plain language:** `everyday-life.md` — the same idea told
  with everyday examples, for readers who don't live in the codebase.
  For more to choose from, matched to different backgrounds, see
  `examples/`.
- **How it fails:** `anti-patterns.md` — the catalog of integration failures,
  and what to do instead.
- **The human system:** `the-human-system.md` is the outermost scale. It
  applies to how we work and to the lives the work touches.
- **A lens for diagnosing failures:** `domains-of-integration.md` maps nine
  ways the mind integrates (from Siegel's Interpersonal Neurobiology) onto the
  systems we build. When a design feels wrong but nothing is "broken," name the
  domain it's failing at.

**Applying it to a domain** — the same principles turned into a field's
practices. Code and product are the first two guides; a profession (HR,
accounting, operations…) can add its own in the same shape:

- **Product work:** start with `product-as-integrator.md`. It's the reason
  the product exists, in our terms.
- **How we build code:** `in-code.md` — the principles turned into
  practice.

**Using it in the work**

- **Every review and retro:** the three tests — closed-loop? handoff?
  part-vs-whole? — plus a FACES score, the five faces of a healthy system
  (details in `START-HERE.md`).
- **Design reviews:** use `templates/design-doc.md`. The "Seams & contracts"
  section is mandatory.
- **PRs:** the integration checkbox in the PR template (in each product
  repo) is not optional.
- **Incidents:** use `templates/postmortem.md`.
- **Retrospectives:** use `templates/retrospective.md`.

This doc is itself a living system. We review it quarterly: what does our
practice show to be true, false, or missing?