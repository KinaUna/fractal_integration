# START HERE — Fractal Integration, in one hour

> **The line to remember:** the parts are cheap; the linkage is what's rare.
> Integration — the linking of differentiated parts — is the whole game, at
> every scale, from a function to a life.

## What "integration" means here

A system is differentiated parts whose integrated functioning produces
properties no part has alone. Integration is the linking of those parts.
Quality is the quality of the linkage — not the sum of the parts.

That is the entire philosophy. The rest of this folder is the same idea
applied at each scale.

Because the same pattern repeats at every scale we work at, we call the
whole philosophy **Fractal Integration**, and this folder — the docs and
the templates that operationalize them — the **Fractal Integration
Guidelines (FIG)**.

## The same idea, at every scale

| Scale    | Parts (the cheap)                    | Linkage (the rare)                        | Emergent property                    | Local-optimization smell |
|----------|--------------------------------------|-------------------------------------------|--------------------------------------|--------------------------|
| **Code**   | functions, modules, services         | contracts, tests, feedback loops           | reliability, performance, maintainability | "my function is fast" |
| **Product**| features, data, screens              | value chains, world seams, integrations       | insight, flow, trust             | "a bag of features"      |
| **Team**   | roles, tools, people                 | rituals, reviews, shared models, boundaries | judgment, velocity-with-quality  | silos, heroics           |
| **Human**  | body, mind, attention, relationships | boundaries, rest, meaning, recovery        | health, well-being, sustainability   | burnout, "grinding"      |
| **World**  | product, competitors, the user's life| adoption, feedback loops, positioning        | category leadership, user trust  | feature parity        |

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

- **Closed-loop:** can the user take a problem in and get an outcome out,
  without leaving? Every exit is a seam we didn't integrate.
- **Copy-paste:** every manual handoff is an un-integrated seam and a value
  leak — including the user copying between our tool and another.
- **Whole-person:** does this optimize a part (output, engagement) at the cost
  of the whole (the person's health, life, meaning)?

Run these in every design review and retro — and whenever a decision
feels cheap.

## Read it in this order (60 minutes)

| # | Doc                          | Time  | What it answers          |
|---|------------------------------|-------|--------------------------|
| 0 | `START-HERE.md` (this page)  | 5 min | the one argument         |
| 1 | `README.md`                  | 5 min | the six principles, in full |
| 2 | `product-as-integrator.md`   | 10 min| what the product is *for* |
| 3 | `in-code.md`                 | 10 min| how we build code        |
| 4 | `in-product.md`              | 5 min | how we run product & team |
| 5 | `the-human-system.md`        | 10 min| the outermost scale: the person |
| 6 | `domains-of-integration.md`  | 5 min | the lenses of linkage, in three sets |
| 7 | `anti-patterns.md`           | 5 min | how integration fails    |
| 8 | `templates/` (skim)          | 5 min | the tools for the rituals |

**Short on time?** Read the six principles, run the three tests on something
you touched today, and stop. Come back to the full pass when you have the
hour — and to `anti-patterns.md` the next time something goes wrong.

**Enter where you stand:**

- New to the team → read top to bottom; that *is* the onboarding.
- About to design something → `product-as-integrator.md`, then `templates/design-doc.md`.
- Running a team or reviewing work → the six principles, then `templates/retrospective.md`.

The order is deliberate: idea → what the product is for → how we build → how
we run it → the life it all lives in → the lenses that connect it all →
how it fails → the tools.

## Do this first (20 minutes, so it sticks)

Don't just read it. Pick one thing you touched this week:

1. List its **parts** (functions, data, screens, people).
2. Draw the **seams** — where the parts meet, and where the output flows.
3. Ask the three tests: closed-loop? copy-paste? whole-person?
4. Find **one un-integrated seam.** That is your first integration task.

You've now run the philosophy once, on a real system. Write it up — even
five lines in `templates/design-doc.md` is enough. That's the loop closing.

## Where the tools live

- Designing a change → `templates/design-doc.md`
- Something broke → `templates/postmortem.md`
- End of a cycle → `templates/retrospective.md`

## The line to leave with

> We will not trade a person's whole for a part's output.

This page is reviewed with the rest of the guidelines, quarterly. Disagree
with something here? That's principle 4 — the loop wants your signal.
