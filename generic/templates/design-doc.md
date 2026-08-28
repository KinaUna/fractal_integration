# [Title]

## Context
## Goals / Non-goals

## Human cost
Does this give the user's time and attention back, or take them? Does it
optimize a part (engagement, output) at the cost of the whole (their life)?
For our team: can this pace hold, and does it respect the boundary?

## Parts affected
Which modules, services, roles, and external systems does this touch?

## Seams & contracts (mandatory)
Which interfaces does this create, change, or depend on?
What is the new contract? Who depends on it? What's the migration path?

## Feedback loops
How will we know it works? Tests at which seams? Which metrics,
which thresholds, who watches them?

## Emergent impact
Performance, reliability, security, UX, cost — for the system, not the part.

## Local-optimization check
Which part is this optimizing? What does the system pay for it?

## Rollout & rollback
Flags, canary, rollback criteria.

## Risks
Where is the integration most likely to break?

## Integration step served
Which arrow does this move? (data→info, info→knowledge, knowledge→solution,
solution→task, task→outcome). If "none," say what value this actually adds.

## World seams
Which integrations, exports, or handoffs does this create or depend on?
Does every output it produces flow to a next action, or does it die here?
