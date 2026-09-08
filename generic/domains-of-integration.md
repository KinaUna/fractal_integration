# Domains of Integration — Product & Software

> **The line to remember:** the mind is a system of integration, and so is a
> product. Siegel named nine ways the mind integrates to produce awareness.
> Here are the same nine, re-mapped from the mind onto the systems we build.

## Where this comes from

Daniel Siegel's Interpersonal Neurobiology describes the mind in terms of
**domains of integration** — the linking of differentiated aspects of
consciousness (see Siegel, *Mindsight*). That is, in other words, the whole
philosophy of this repo: *differentiated parts whose integrated functioning
produces properties no part has on its own.*

(Want the source directly, rather than our re-mapping of it? See the
Siegel entry in [`further-reading.md`](further-reading.md).)

This doc makes the parallel explicit. Each domain that integrates a mind also
integrates a system, a team, and a product. Use it as a diagnostic: when a
system feels like a "bag of features" or a "god module," name the domain that
is failing. Most failures are not missing parts — they are a missing
integration in one of these nine.

This doc is one of the most concrete parts of the guidelines: the domains
are the *kinds* of linkage to look for when a system is failing — nine of
them the mind already knows, six native to software, six native to product.

## The nine, at a glance

| Domain (Siegel)    | In the mind it links                  | In what we build it links                            | Emergent (the whole)          | The smell (the failure)         |
|--------------------|---------------------------------------|------------------------------------------------------|-------------------------------|---------------------------------|
| **Consciousness**  | alertness ↔ background flow           | signal ↔ attention                                   | calm, coherent awareness      | alert fatigue / total blindness |
| **Bilateral**      | left ↔ right hemisphere               | the two sides of a seam (producer ↔ consumer)        | a seam that actually holds    | silent coupling                 |
| **Vertical**       | lower/emotional ↔ upper/cognitive     | the layers of the stack (runtime ↔ strategy)         | design true to reality        | "designing in the cloud"        |
| **Memory**         | past ↔ present, explicit ↔ implicit   | what we learned ↔ what we do (docs, ADRs, tests)     | organizational learning       | tribal knowledge / frozen legacy |
| **Narrative**      | events ↔ a coherent self-story        | features ↔ one story (the journey, the "why")        | coherence — it makes sense    | a bag of features               |
| **States**         | waking ↔ dreaming ↔ flow              | the system's modes (dev, prod, overload, failover)   | resilience — one truth, all states | works in dev, breaks in prod |
| **Interpersonal**  | mind ↔ mind                           | role ↔ role; product ↔ the user's world              | shared understanding          | silos, divergent mental models  |
| **Temporal (time)**| past ↔ present ↔ future               | history ↔ live state ↔ projection (order, consistency) | continuity, foresight        | amnesia / firefighting only     |
| **Transpirational**| across generations                    | across versions, teams, and generations              | a system that outlives its authors | re-discovers the same lesson each cycle |

---

## 1. Integration of consciousness — *see without blinding or flooding*

**In the mind:** consciousness isn't all-or-nothing. It's a range between
hyper-arousal and hypo-arousal, and health is living in the workable middle.

**In what we build:** a system has awareness. The integration is between
*signal* (logs, metrics, traces) and *attention* (who looks, who acts). Too
much signal → alert fatigue, nobody responds. Too little → blind. The
workable middle: enough signal to know what's true, each one routed to an
owner with a response. (See [`in-product.md`](./in-product.md): every loop
needs an actuator.)

**The smell:** dashboards nobody reads, or no visibility at all.
**Heuristic:** if a signal has no owner and no response, it isn't awareness —
it's noise.

## 2. Bilateral integration — *both sides of the seam must agree*

**In the mind:** the two hemispheres are specialized and must talk to each
other; awareness needs both halves linked.

**In what we build:** every seam has two sides — a producer and a consumer, a
writer and a reader, the left and the right. Value and failure both live in the
*agreement* between the sides. One side optimized against the other's silent
assumption is a seam that hasn't actually integrated.

**The smell:** [`accidental integration`](./anti-patterns.md) — it works
until one side changes its assumption.
**Heuristic:** name both sides of the seam and write down what each assumes the
other does. If you can't, the contract isn't real.

## 3. Vertical integration — *design that stays true to reality*

**In the mind:** the lower, older, emotional layers and the upper, newer,
cognitive layers must link. A mind that can't bind the two is either flooded
by feeling or untethered from it.

**In what we build:** link the *levels* of the system — the fast, low
(realities: latency, cost, failure modes) with the slow, high (the strategy,
the model, the intent). The high level's decisions must be constrained by the
low level's realities, and the low level's signals must shape the high level's
choices. Architecture that ignores its runtime is a mind untethered from its
body.

**The smell:** "designing in the cloud" — a model that is elegant on paper and
impossible or ruinously expensive at the layer below.
**Heuristic:** can the top-level design survive the constraints of the bottom
layer? Run it down the stack once before you call it done.

## 4. Integration of memory — *the past informs the present, without freezing it*

**In the mind:** past experience and present moment are linked; explicit
(declarative) and implicit (non-declarative) memory are linked — so the past
can guide the now without dominating it.

**In what we build:** link what we have *learned* to what we are *doing*.
Explicit memory = docs, ADRs, tests, specs. Implicit memory = the instinct of
how this codebase actually behaves. Integration: the past is retrievable and
actionable, and it informs the present without forbidding change.

**The smell:** [`accidental integration`](./anti-patterns.md) — the lesson
lives in one head and leaves when they do — or frozen legacy (the past
forbids all change).
**Heuristic:** for this decision, point at the artifact that records *why*. If
it doesn't exist, the memory is only implicit — it will be lost.

## 5. Integration of narrative — *one story, not a bag of parts*

**In the mind:** raw events are linked into a coherent self-story. Meaning is
the narrative that binds experience.

**In what we build:** link the parts into a story. Two stories matter: the
*user's* — onboarding → first value → growth → retention must read as one
continuous arc, not four disconnected features; and the *team's* — the "why" of
each piece must be retrievable. A product with parts but no story is the
[`bag of features`](./anti-patterns.md).

**The smell:** [`feature sprawl`](./anti-patterns.md) — every feature works,
and nobody can say what the product is *for*.
**Heuristic:** can you tell the user's story in one breath, and the reason each
part exists? If not, you have features, not a product. (See
[`product-as-integrator.md`](./product-as-integrator.md).)

## 6. Integration of states — *one truth across every mode*

**In the mind:** the different states of consciousness — waking, dreaming,
flow, meditation — are linked, so one state can inform and repair another.

**In what we build:** a system runs in many states — dev, staging, production,
degraded, overloaded, in failover. Integration is the *coherence across them*
and the *design of the transitions* (deploy, rollback, scale, shed load). A
system whose behavior is a different truth in each state hasn't integrated its
states.

**The smell:** [`green CI, red production`](./anti-patterns.md), and no
graceful path through failure — states are walls, not a continuum.
**Heuristic:** what does the system do when it can't do the happy path? If the
answer is "nothing designed," the degraded state is un-integrated.

## 7. Interpersonal integration — *the mind is not in one head*

**In the mind:** the mind isn't contained in the skull. It is made in the
linking of mind to mind — relating, empathy, attachment.

**In what we build:** the "system" is not contained in one service or one
person. Integration is the linking of *person to person* and *product to the
user's world*. Roles must share one end-to-end model — where our mental models
diverge, seams break silently (see [`in-product.md`](./in-product.md),
cross-role integration).

**The smell:** [`retros without actuation`](./anti-patterns.md) and
[`metrics without loops`](./anti-patterns.md) — each role has a different map
of the same system, and the gaps are where it fails.
**Heuristic:** if the engineer, the designer, and the PM each drew the
architecture "from memory," they drew three pictures. That divergence is the
bug.

## 8. Temporal integration — *the system spans time, not just a request*

**In the mind:** past, present, and future are held together; the past
informs the present, and the future shapes it. The sense of time as continuous
is itself an integration.

**In what we build:** link the *time axes* of the system. Past = history,
telemetry, data. Present = the live request, the current state. Future =
projections, planned capacity, deprecation. Integration: the system reads its
past to act in the present, and plans for the future — with *order and
consistency* held across all three (causality, sequencing, eventual
consistency). This is distinct from memory: memory is *what we know*;
temporal is *how the system behaves across time*.

**The smell:** amnesia (every request is day one, no history, no order) or
present-only firefighting (reactive to the now, never planning the next).
**Heuristic:** does this design hold its invariants over time — under retries,
out-of-order events, and a year of data? If it only holds for one request, it
isn't integrated temporally.

## 9. Transpirational integration — *the system outlives its authors*

**In the mind:** integration reaches across *generations* — patterns,
lessons, and even predispositions are transmitted to the minds that come next.
A mind is not a blank slate that ends at one lifespan. It is a link in a
lineage: it carries the integration of the minds before it, and hands some of
its own forward to the minds after it.

**In what we build:** link the *generations* of the system — past version →
current → next, and past team → current team → successor. Integration is the
*transmission* of intent, constraints, and hard-won knowledge to those who
follow: ADRs, contracts, tests, and docs written for the next reader, not the
current author. A codebase that only its creator understands has no
transpirational integration.

**The smell:** each cycle re-discovers the same lesson; a "throwaway" that was
never handed to a next generation; a team that can't tell you why the design is
the way it is.
**Heuristic:** hand this to a new hire next month. What do they inherit, and
what did we have to re-learn? The gap is the transmission we skipped.

---

## Six more, that exist only in software

Siegel's nine come from the mind. A working system needs them all — but
software has axes the mind has no counterpart for. These six are native to
the systems we build.

| Domain             | What it links                            | Emergent (the whole)        | The smell (the failure)         |
|--------------------|------------------------------------------|-----------------------------|---------------------------------|
| **Spatial**        | one node ↔ the distributed whole         | a system, not one machine   | "works on one server", split brain |
| **Data / meaning** | format ↔ semantics (types, invariants)   | data that can be reasoned about | magic numbers, `data` columns |
| **Cognition**      | the user's model ↔ the system's model    | the system feels legible    | error states nobody can read    |
| **Authority**      | identity ↔ permission ↔ audit            | trust you can show           | god accounts, "who allowed that?" |
| **Capacity**       | workload ↔ resources                     | steadiness under load       | unbounded queues, cost spikes   |
| **Artifact**       | intent ↔ artifact ↔ environment          | "works on my machine" is meaningless | environment drift     |

## 10. Spatial integration — *the whole is more than the node*

**The problem:** a mind is one place; a system is many. Replicas, regions,
shards, and caches are differentiated copies that must link back into one
consistent whole. Every copy is a new seam.

**In what we build:** the integration is between the *local truth* of a node
and the *global truth* of the system — replication, quorum, eventual
consistency, the rules that keep many machines agreeing without a single
bottleneck. A design that is correct on one node and undefined across five
hasn't integrated its space.

**The smell:** "works on one server"; split brain; behavior that depends on
which machine answered.
**Heuristic:** kill a node, partition the network, and read from a replica.
Does the whole still tell one consistent story? If the answer depends on
luck, the spatial integration is missing.

## 11. Integration of data — *form is not meaning*

**The problem:** data has two halves — its *form* (bytes, columns, wire
format) and its *meaning* (what the values stand for, what they may be, how
they relate). Form without meaning is storage; meaning without form is a
vague idea. Neither is a system.

**In what we build:** the integration is between *representation* and
*semantics*: types over raw columns, invariants over magic numbers,
identifiers you can dereference over opaque strings. Every place the meaning
lives only in a person's head — a `status = 7`, a `data` blob, an unnamed
enum — is a form/meaning seam we didn't integrate.

**The smell:** `data` columns, magic numbers, IDs that no one can explain or
join.
**Heuristic:** can a reader of the schema alone say what a row *means* and
what it may legally be? If the answer requires a person, the meaning isn't
in the system.

## 12. Integration of cognition — *the user's model must link to the system's*

**The problem:** a running system has its own model of the world, and the
person in front of it has a different one. Neither is wrong; they must
*link*. This is the bilateral integration we keep failing, across the
human/machine boundary — and it's the domain the mind itself can't map onto
itself.

**In what we build:** the integration is between *how the user expects the
system to behave* and *how it actually does* — terminology, affordances,
error messages that name the real state, recoveries that match the user's
mental model of what went wrong. Every time the system does something the
user can't narrate, the two models have de-linked.

**The smell:** error states nobody can read; jargon UIs; "the system did X"
where X is inexplicable to the person who just hit it.
**Heuristic:** after a failure, ask the user to describe what happened in
their words. Where their story diverges from the system's, that gap is the
un-integrated cognitive seam.

## 13. Integration of authority — *trust must be linkable*

**The problem:** three things that must agree: *who* (identity), *what they
may do* (permission), and *what actually happened* (audit). Each is a
different part. A system where they drift apart is a system whose trust is
not integrated — the parts exist, the linkage is missing.

**In what we build:** the integration is the chain from identity →
permission → action → record, held intact. An action that cannot be
attributed to an identity, or a permission with no audit trail, is a broken
link in that chain. Security here is not a feature you add; it is the
linkage between these three parts.

**The smell:** god accounts, unscoped tokens, "who allowed that?" with no
answer.
**Heuristic:** pick any sensitive action. Trace it forward to an audit record
that names the identity, and backward from that record to the permission that
allowed it. If either direction stops, the chain isn't integrated.

## 14. Integration of capacity — *the system must link load to resources*

**The problem:** workload is differentiated from resources. The former is
open-ended and external; the latter is finite and paid for. A system that
can't link the two is either drowning in load or burning capacity it doesn't
need — and it can't tell the difference, because it has no integration
between the halves.

**In what we build:** the integration is the *feedback between demand and
supply* — backpressure, rate limiting, scaling policies, load shedding,
cost-aware capacity planning. Each of these is a link that says *here is how
much load this much resource can bear*. Without them, load and resources
drift apart silently until one of them fails loudly.

**The smell:** unbounded queues, cost spikes nobody predicted, no path for
graceful degradation under load.
**Heuristic:** double the load. What does the system do? If the answer is
"it dies" or "the bill doubles," the load/resource link isn't designed.

## 15. Integration of the artifact — *intent must survive the build*

**The problem:** there are three artifacts in a chain — *intent* (the code
as written, the design as decided), *build* (the compiled, packaged,
configured thing), and *environment* (where it runs, on what, with what
secrets). Each is a different thing. If any link in that chain is lossy or
unreproducible, the system that ships is not the system that was designed.

**In what we build:** the integration is the *lossless, reproducible path*
from intent to running system: deterministic builds, configuration that is
data not tribal knowledge, environments that are declared not inherited,
dependency pinning that makes the build a function of the source alone.
Every place "works on my machine" is true is a link in this chain that
doesn't hold.

**The smell:** environment drift; secrets that live in one machine; builds
that are not reproducible; "it worked in CI" that doesn't transfer to prod.
**Heuristic:** on a clean machine with only the repo, can you reproduce the
production build exactly? If the answer requires someone's laptop or their
memory, the artifact chain is broken at that link.

---

## Six more, native to product

The mind gives us nine, and software six more. A product reaches into the
world — into money, trust, and the lives of many different people — and so it
has axes of its own. These are the ones that only exist once a system has to
earn its place in the market and in a user's life.

| Domain      | What it links                         | Emergent (the whole)         | The smell (the failure)        |
|-------------|---------------------------------------|------------------------------|--------------------------------|
| **Value**   | what's paid ↔ what's returned         | a real exchange              | vanity metrics                 |
| **Fit**     | capabilities ↔ the user it's for      | a product, not a toy         | "built for everyone"           |
| **Trust**   | the promise ↔ the delivery            | trust you can keep           | churn at activation            |
| **Lifecycle**| the relationship's phases ↔ each other| a relationship, not a moment | great onboarding, no return    |
| **Agency**  | guidance ↔ autonomy                   | the user stays in charge     | dark patterns / paralysis      |
| **Access**  | one design ↔ many users               | a product for the population | "it works for me"              |

## 16. Integration of value — *what's paid must link to what's returned*

**The problem:** a product is an exchange. The user pays something — money,
time, attention, data, trust — and expects something back. The parts (price,
the features, the support) are differentiated; the integration is whether the
*total paid* links to the *total returned*. This is not the internal value
chain (data → outcomes); it is the value that crosses the boundary to the
user.

**In product:** willingness to pay, ROI, the felt return. A feature that costs
the user attention and returns none is a leak, even when it's heavily "used."

**The smell:** vanity metrics; high churn right after the free tier; users who
say they like it and then cancel.
**Heuristic:** what does a typical user actually pay, in all currencies, and
what do they actually get back? If you can't state the exchange in one
sentence, the value isn't integrated — it's assumed.
(See [`product-as-integrator.md`](./product-as-integrator.md) for the internal
value chain this complements, and the seam principle for what "paid" and
"returned" mean across the boundary.)

## 17. Integration of fit — *the product must link to the user it's for*

**The problem:** a product's capabilities are differentiated from the needs of
the people it serves. They only become a product when the two link. Capabilities
without a fit are a toy; a fit without capabilities is a promise.

**In product:** positioning, the ideal customer, the specific problem for the
specific person. "Built for everyone" is the smell — it means built for no one.

**The smell:** feature parity as a strategy; "who is this for?" with no crisp
answer.
**Heuristic:** name the one person this is for and the one problem it kills
for them. If you can't, the capability and the user aren't linked.
(See [`product-as-integrator.md`](./product-as-integrator.md) — the product's
job is to link the user's world into a whole *they can act on*; fit is that
job stated as a boundary question. And [`anti-patterns.md`](./anti-patterns.md):
feature sprawl is fit failing quietly.)

## 18. Integration of trust — *the promise must link to the delivery*

**The problem:** a product makes a claim — the brand, the pricing, the
marketing, the onboarding promise — and then delivers an experience. These are
two parts. When they diverge, trust breaks; and trust is the emergent property
that no single feature can restore afterward.

**In product:** the gap between first impression and first value, and between
stated and actual behavior. Churn at activation is usually a promise/delivery
seam, not a feature gap.

**The smell:** "bait and switch" onboarding; high trial signups, low
activation; refunds that say "not what I expected."
**Heuristic:** write down the top three promises a user buys, and check each
against the actual first-week experience. Any promise the delivery can't keep
is a broken trust link.
(See [`in-product.md`](./in-product.md) — trust is the emergent property we
protect by watching the whole, and this domain is where it is won or lost.)

## 19. Integration of lifecycle — *the phases must link to each other*

**The problem:** a user's relationship with a product runs in phases —
acquisition, activation, retention, expansion, and (when things go wrong)
recovery. Each phase is a part with its own goals and its own team. The
integration is the *transitions* between them: where one phase's work hands off
to the next.

**In product:** the seams between growth and product, product and support,
success and re-activation. A product can excel in every phase and still fail
at the transitions.

**The smell:** great onboarding, no reason to come back; a strong product,
no growth; good support, no re-activation.
**Heuristic:** trace one user from first touch to their six-month self. Where
did a handoff drop them? The phase with a strong metric but a weak transition
is the un-integrated seam.
(See [`in-product.md`](./in-product.md) — "seams are where users meet the
whole" names these transition seams directly.)

## 20. Integration of agency — *guidance must link to autonomy*

**The problem:** a product both guides (defaults, recommendations, flows) and
leaves the user free to choose. These are two forces that must be *integrated*,
not stacked. Too much guidance overpowers the user (dark patterns); too little
abandons them (paralysis). Health is in the linkage: the product guides where
it should, and gets out of the way where the user's own judgment should lead.

**In product:** default choices, the balance of hand-holding and power, and
whether the product's nudges serve the user's goal or the product's metric.

**The smell:** dark patterns; "I don't know which one to pick"; power users
resenting the handrail while beginners drown without it.
**Heuristic:** for a key decision, ask who is choosing — the user or the
product? And is that the right one, for that person, at that moment? If the
product is choosing for its own metric where the user should choose for
themselves, the agency link is corrupted.
(See [`the-human-system.md`](./the-human-system.md) — the whole-person test:
a nudge that optimizes the product's metric at the cost of the person's
attention is exactly the local optimization that doc warns against.)

## 21. Integration of access — *one design must link to many users*

**The problem:** a product is one design; its users are many — different
abilities, literacies, devices, contexts, and constraints. The integration is
how one differentiated design links to a differentiated population without
excluding a slice of it.

**In product:** accessibility, localization, low-connectivity, and "who can
actually use this" as design inputs, not afterthoughts. The median user is a
part; the whole is the population.

**The smell:** "it works for me"; accessibility as a compliance checkbox; a
feature that quietly requires a capability the target user doesn't have.
**Heuristic:** who is the least-served person who still needs this? Run their
path end to end. Every place their path hits a wall is an access seam the
design didn't integrate.
(See [`the-human-system.md`](./the-human-system.md) — the user's world
includes their body, attention, and context; access is integrating with all
of it, not just the median one.)

---

## How to use this

- **In design reviews:** when a proposal feels wrong but nothing is "broken,"
  name the domain it's failing at. "This has parts but no narrative" is a
  specific, actionable critique.
- **In postmortems and retros:** don't just ask *what* broke — ask *which
  integration* was missing. The answer is the durable lesson, not the symptom.
- **As a self-check for the team:** the interpersonal and transpirational
  domains are the ones we most often neglect, because they aren't "code." They
  are exactly as real as the rest.
- **When a smell names an anti-pattern:** [`anti-patterns.md`](./anti-patterns.md)
  is the fix map — each domain's smell points at the row where the fix lives.

The list is not a checklist to tick. It's a lens: **the parts are cheap; the
linkage is what's rare** — and these are the kinds of linkage a working system
needs. Nine of them the mind already knows; six are native to software; six
belong to the product that reaches out into the world.
