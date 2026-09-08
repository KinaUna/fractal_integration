# START HERE — Fractal Integration, in one hour

> **The gist** the parts are cheap; effective linkage is rare, but fundamental to great systems.
> Integration, the linking of differentiated parts, is essential for complex systems, at
> every scale, from simple functions, to life and entire ecosystems.

## Why this is worth an hour

This isn't a new idea. Systems theory, cybernetics, the study of
institutions, even the leading theory of consciousness all converge on the
same claim: differentiated parts, linked well, produce something no part
has alone — and most failure is a failure of the linkage, not the parts.
What these guidelines add isn't a new truth. It's a shared, practical
vocabulary for a pattern you already live inside every day, kept in one
place, kept alive, and easy to bring into whatever you're building.

Once you see it, you see it at every size:

- **The smallest scale.** A relay team drops the baton — four excellent
  runners lose to a slower team that practiced the handoff. A dish fails
  not because an ingredient was bad, but because nothing was given its
  moment.
- **Your work.** CI is green, the deploy ships, and production still
  breaks. The parts were fine; the seam between them was never tested.
- **Your life.** Burnout isn't one broken part — not enough sleep, too
  much work. It's the coordination between sleep, work, rest, and meaning
  breaking down. The diagnosis for a struggling system and a struggling
  person is the same one: the parts are fine, the linkage is failing.
- **The biggest scale.** The 2008 financial crisis was mortgage risk
  deliberately sliced and resold to sever the link between who originated a
  loan and who bore its consequence — a bilateral-integration failure with
  a trillion-dollar price tag. Climate change is a planet-sized feedback
  loop with no owner: the cost of carbon is differentiated from whoever
  emits it, so nothing corrects. Political polarization and the erosion of
  institutional trust read as a narrative and interpersonal integration
  failure at the scale of a whole society — different groups with no
  shared story and no functioning feedback between them.

None of these are "like" an integration failure, as a figure of speech.
They *are* one — the same failure your team has, wearing a bigger coat.
That's the actual claim behind "fractal": not that the world is mystically
made of fractals, but that this one failure mode — parts without adequate
linkage — repeats, recognizably, at every scale we've looked. Learning to
see it in a standup makes it visible in a headline; the reverse is also
true, and either direction is a reason to keep reading.

**Use this like a travel guide, not a lexicon.** These pages aren't a
canon to memorize or a tutorial with a right answer at the end. They're a
way of noticing something that's already there, so you can name it and act
on it in whatever terrain you're actually in — a PR, a diagnosis, a
household, a policy. Take what's useful and leave the rest; the map isn't
the point, finding your way is.

That's also why this lives in a public, evolving repository instead of a
document you'd print once: the guidelines are meant to keep fractally
integrating — with your domain, your team's language, and other ideas as
you find them — rather than staying fixed. See
[`adopting-fig.md`](adopting-fig.md) for how to bring this into your own
project and keep it linked to this source as both evolve.

## What "integration" means here

A system is differentiated parts whose integrated functioning produces
properties no part has alone. Integration is the linking of those parts.
Quality is the quality of the linkage — not the sum of the parts.

That is the entire philosophy. It applies to any differentiated system —
a process, a product, an organization, a team, a person. The rest of this
folder is the same idea applied at each scale.

Because the same pattern repeats everywhere, we call the whole philosophy
**Fractal Integration**, and this folder — the docs and the templates that
operationalize it — the **Fractal Integration Guidelines (FIG)**.

The core docs in this folder are domain-neutral. The code and product docs
are its first two applications; guides for other professions — HR, accounting,
and so on — can be added on the same pattern (see
[Applying it to your domain](#applying-it-to-your-domain)).

## The same idea, in everyday life

Before the work scales, the idea in things you can touch:

| Everyday    | Parts (the cheap)         | Linkage (the rare)                              | Emergent property            | The smell                              |
|-------------|---------------------------|--------------------------------------------------|------------------------------|----------------------------------------|
| A meal      | ingredients               | the cooking — heat, order, balance               | a dish; satisfaction         | a buffet where nothing goes together   |
| A bicycle   | frame, gears, chain       | tension, alignment, the drivetrain working together | speed — crossing a town   | a shop full of parts that get you nowhere |
| A relay race| runners                   | the baton handoff — timing, trust, rehearsal     | a team time no runner has alone | dropped batons — the seam fails    |

The next table is the same shape, at work scales. Plain-language version,
with the cooking example written out in full:
[`everyday-life.md`](everyday-life.md). Want more examples to pick from —
matched to your own background rather than ours? See
[`examples/`](examples/README.md).

## The same idea, at every scale

| Scale    | Parts (the cheap)                    | Linkage (the rare)                        | Emergent property                    | Local-optimization smell |
|----------|--------------------------------------|-------------------------------------------|--------------------------------------|--------------------------|
| **A piece of work**  | tasks, tools, data                  | handoffs, reviews, feedback               | quality, trust in the outcome | "my part is done"   |
| **Code**             | functions, modules, services        | contracts, tests, feedback loops          | reliability, maintainability  | "my function is fast" |
| **Product**          | features, data, screens             | value chains, integrations                | insight, flow, trust          | "a bag of features"  |
| **Team**             | roles, tools, people                | rituals, reviews, shared models, boundaries | judgment, velocity-with-quality | silos, heroics  |
| **Person**           | body, mind, attention, relationships| boundaries, rest, meaning, recovery       | health, well-being, sustainability | burnout, "grinding" |
| **World**            | product, competitors, the user's life| adoption, feedback, positioning           | trust, category leadership    | feature parity       |

Read that table once and you've read the whole repo. Every doc below is one
row, expanded.

## The six principles (short version)

1. Quality is the quality of the linkage.
2. Differentiation is deliberate; integration is the work.
3. Bugs and value both live at the seams.
4. Feedback loops are a feature — every loop needs an owner and a response.
5. Emergent properties can't be delegated — judge the whole, not the part.
6. Integration decays — review, reflection, and maintenance close the loop.

(Full version: `README.md`.)

## The three tests

- **Closed-loop:** can someone take a problem in and get an outcome out,
  without leaving? Every exit — every point where the work must leave the
  system — is a seam we didn't integrate.
- **Handoff:** every manual transfer between parts, systems, or people is an
  un-integrated seam and a value leak.
- **Part-vs-whole:** does this optimize a part (an output, a metric, a
  quarter) at the cost of the whole (the person, the team, the life, the
  trust it all stands on)?

Run these in every review and retro — and whenever a decision feels cheap.

## The five faces of a healthy system — FACES

Daniel Siegel, working in Interpersonal Neurobiology, names what a healthy
*relationship* looks like with five words: **F**lexible, **A**daptive,
**C**oherent, **E**nergizing, **S**table. We use the same shape to ask the
same question of a system, a team, or a product:

| Face       | A healthy system is…                                                        | Where it lives                                 |
|------------|-----------------------------------------------------------------------------|------------------------------------------------|
| **F**lexible   | parts can change without the whole breaking; degradation is graceful, not catastrophic | principle 6 (decay) + states (`domains-of-integration.md`) |
| **A**daptive   | feedback reaches a decision and changes it                                  | principle 4 — a loop needs an owner *and* a response |
| **C**oherent   | parts link into one story a newcomer can read and a user can narrate        | narrative + cognition (`domains-of-integration.md`) |
| **E**nergizing | working with it is sustainable — for the team and for the user              | `the-human-system.md` — the letter that keeps us honest about people |
| **S**table     | the whole holds under load and over time; trust survives the handoff        | capacity + transpirational (`domains-of-integration.md`) |

Run FACES alongside the three tests: the tests ask where the system
*fails*; FACES asks where it is *healthy*. The templates carry a FACES
score, so a cycle can move one of the five faces on purpose — and a
design can name what it trades away before it's built.

## Read it in this order (60 minutes)

| # | Doc                          | Time  | What it answers          |
|---|------------------------------|-------|--------------------------|
| − | `everyday-life.md`           | 10 min| the same idea in plain language — start here if jargon isn't your language |
| 0 | `START-HERE.md` (this page)  | 5 min | the one argument         |
| 1 | `README.md`                  | 5 min | the six principles, in full |
| 2 | `product-as-integrator.md`   | 10 min| application: what the product is *for* |
| 3 | `in-code.md`                 | 10 min| application: how we build code        |
| 4 | `in-product.md`              | 5 min | application: how we run product & team |
| 5 | `the-human-system.md`        | 10 min| the outermost scale: the person |
| 6 | `domains-of-integration.md`  | 5 min | the lenses of linkage, in three sets |
| 7 | `anti-patterns.md`           | 5 min | how integration fails    |
| 8 | `templates/` (skim)          | 5 min | the tools for the rituals |
| 9 | `adopting-fig.md`            | 5 min | bringing this into your own project, and keeping it linked to source |

Steps 2–4 are the first applications of the pattern to specific domains.
Other professions can slot their own guide in the same position — same
shape, same length.

**Short on time?** Read the six principles, run the three tests on something
you touched today, and stop. Come back to the full pass when you have the
hour — and to `anti-patterns.md` the next time something goes wrong.

**Enter where you stand:**

- Not a technical reader → `everyday-life.md` — the same idea in
  plain language, no jargon. If none of its examples fit you, `examples/`
  has more to pick from.
- New to the team → read top to bottom; that *is* the onboarding.
- About to design something → the domain guide for your field (code:
  `in-code.md`, product: `product-as-integrator.md`), then `templates/design-doc.md`.
- Running a team or reviewing work → the six principles, then `templates/retrospective.md`.
- In another profession → start with the core (steps 0–1, 5–8), then find
  the guide for your domain — or write one (below).

The order is deliberate: idea → what the product is for → how we build → how
we run it → the life it all lives in → the lenses that connect it all →
how it fails → the tools.

## Applying it to your domain

Any profession can run this pattern on itself. Pick a domain — HR,
accounting, operations, a craft — and fill in one row of the table above:

- **Parts** — what it is made of.
- **Linkage** — what connects the parts (policies, reviews, handoffs,
  reconciliations).
- **Emergent property** — what only the integrated whole delivers.
- **Local-optimization smell** — what optimizing a part sounds like when
  the whole degrades.

Then write a guide for the domain, in the shape of `in-code.md`: the six
principles turned into its practices. The row becomes the guide's table of
contents; the rest is filling it in.

Doing this with an AI agent, or pulling these guidelines into a project
that isn't this repo? See [`adopting-fig.md`](adopting-fig.md) — it covers
how to differentiate a local copy without losing the link back to this
source as it keeps evolving.

## Do this first (20 minutes, so it sticks)

Don't just read it. Pick one thing you touched this week — a process, a
project, a piece of work:

1. List its **parts** (tasks, tools, data, people).
2. Draw the **seams** — where the parts meet, and where the output flows.
3. Ask the three tests: closed-loop? handoff? part-vs-whole?
4. Find **one un-integrated seam.** That is your first integration task.

You've now run the philosophy once, on a real system. Write it up — even
five lines in `templates/design-doc.md` is enough. That's the loop closing.

## Where the tools live

- Designing a change → `templates/design-doc.md`
- Something broke → `templates/postmortem.md`
- End of a cycle → `templates/retrospective.md`

## The line to leave with

> We will not trade the whole — whether the whole is a system, a team, or a
> person — for a part's output.

This page is reviewed with the rest of the guidelines, quarterly. Disagree
with something here? That's principle 4 — the loop wants your signal.