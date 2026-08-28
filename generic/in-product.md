# Integration in Product

> The conceptual foundation for everything in this doc is
> [`product-as-integrator.md`](./product-as-integrator.md). Read it first —
> it answers *what the product is for*. This doc is *how we do it*.

## The product is a system
Parts: features, onboarding, billing, docs, support, third-party
integrations, the team, the market. The product's behavior — trust,
retention, "goodness" — is emergent. It can't be assigned to a feature,
so we protect it by watching the whole.

## Seams are where users meet the whole
Users don't experience features. They experience the seams between them:
onboarding, first value, checkout, migration, export, "does it work with
the tool I already use." We invest in seams at least as heavily as in
features.

## Every loop needs an actuator
- **Fast (minutes–hours):** product metrics, error rates, deploy signals.
- **Medium (days–weeks):** support tickets, sales feedback, usage patterns.
- **Slow (weeks–quarters):** user interviews, cohort analysis, competitive
  shifts.

A loop without a scheduled response action is decoration. Every loop has
an owner, a cadence, and a defined response. A loop that closes but nothing
changes is [`retros without actuation`](./anti-patterns.md).

## Watch local optimization
Optimizing one metric (clicks, velocity, revenue/session) while the whole
(retention, trust, platform health) decays is the classic systems failure.
Before committing to a goal, ask: *which part are we optimizing, and what
is the cost to the system?*

## Cross-role integration
Engineering, design, product, and data must share one end-to-end model of
the system. Where our mental models diverge, seams break silently.
Design reviews, shared metrics, and cross-role pairing are our integration
harnesses as a team. A feature that works technically but not in the user's
context failed at a seam we didn't see.

## Releases are integration events
The deploy pipeline, feature flags, and canaries are integration harnesses
that let us link parts with controlled risk. The rollout and rollback plan
is part of the design, not an afterthought.

The rituals that keep this whole doc alive — design reviews, postmortems,
retrospectives — live in `templates/`.
