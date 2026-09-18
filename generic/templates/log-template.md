# The Log — Entry Template

This is the artifact [`retrospective.md`](retrospective.md) and
[`postmortem.md`](postmortem.md) already point at ("log each in the seam
log"; "score each 1–5, this cycle vs. last cycle") — the destination those
two references have been missing. Validated by
[`log-schema.json`](log-schema.json).

Where the actual entries live is yours to decide, and it's a real decision:
unlike this schema, entries usually aren't domain-neutral. The moment
they start covering more than one project — or anything outside work at
all — most people want them somewhere private, not sitting in whatever
repo holds their public guidelines. A plain JSONL file, one per year, in
a private repo or a local-only `git init` folder, works fine and needs
nothing more than what's below.

One line of the log = one JSON object. Two entry *types* share one
envelope, so both can be queried together later (e.g. "every open item
across every system") even though they capture different things.

## The envelope (every entry has these)

| Field | Required | Notes |
|---|---|---|
| `id` | yes | ULID or any time-sortable unique ID |
| `date` | yes | ISO 8601, e.g. `2026-09-11` |
| `system` | yes | Open vocabulary — yours to grow. One value per project or area of life you're logging. Keep it short and stable so you can filter by it later. |
| `source` | yes | `retro` \| `postmortem` \| `design-doc` \| `ad-hoc` \| `other` (+ `source_other` if `other`) |
| `type` | yes | `seam` or `faces` — picks which fields below apply |
| `notes` | no | Free text, always welcome |

## Type: `seam` — a linkage that broke

Maps to `retrospective.md`'s "seam failures" and `postmortem.md`'s "which
seam broke."

| Field | Required | Notes |
|---|---|---|
| `domain` | yes | One of the 21 domains in [`../domains-of-integration.md`](../domains-of-integration.md), or `other` |
| `domain_other` | if `domain: other` | Free text. If you keep reaching for `other` on the same kind of seam, that's a signal a 22nd domain wants naming — principle 2 (deliberate differentiation), applied to this schema itself. |
| `anti_pattern` | no | One of the 8 in [`../anti-patterns.md`](../anti-patterns.md), or `other`. Optional — a seam can break without matching a named anti-pattern. |
| `anti_pattern_other` | if `anti_pattern: other` | Free text |
| `seam` | yes | Name the *boundary*, not the component. `"mobile client <-> API token refresh"`, not `"the API"`. |
| `what_broke` | yes | What actually happened at that boundary |
| `action` | no | What closes the loop. Fill in when you have it, even if that's later than the entry itself. |
| `owner` | no | Matters once this spans more than one person |
| `status` | yes | `open` \| `closed` |
| `closed_date` | no | Set when `status` flips to `closed` |

**The 21 domain slugs**: `consciousness`, `bilateral`, `vertical`,
`memory`, `narrative`, `states`, `interpersonal`, `temporal`,
`transpirational`, `spatial`, `data`, `cognition`, `authority`,
`capacity`, `artifact`, `value`, `fit`, `trust`, `lifecycle`, `agency`,
`access`.

**The 8 anti-pattern slugs**: `part_sprawl`, `god_part`,
`distributed_fragmentation`, `parts_work_seams_dont`,
`signals_without_loops`, `accidental_integration`, `silent_coupling`,
`reflection_without_actuation`.

### Example

```json
{"id":"01J8ZC3R8K9Q2X4Y5Z6W7V8U9T","date":"2026-09-11","system":"my-app","source":"design-doc","type":"seam","domain":"bilateral","anti_pattern":"silent_coupling","seam":"mobile client <-> API token refresh","what_broke":"client assumed silent refresh; API started requiring re-auth after the last deploy and nobody told the client team","action":"version the refresh contract, add a changelog note for breaking auth changes","owner":"you","status":"open"}
```

## Type: `faces` — a per-cycle score

Maps to `retrospective.md`'s FACES score and "one integration move." Works
the same whether the cycle is a sprint or a personal week.

| Field | Required | Notes |
|---|---|---|
| `cycle` | yes | An identifier for the cycle, e.g. `2026-W37` or `sprint 24`. Keep one convention per `system` so cycles sort/compare cleanly. |
| `scores` | yes | Object with `flexible`, `adaptive`, `coherent`, `energizing`, `stable`, each `1`–`5` |
| `lowest_face` | yes | Which of the five is weakest this cycle |
| `integration_move` | no | The one committed action for next cycle |
| `move_status` | no | `open` \| `closed` — lets the *next* cycle's loop-check be a lookup instead of a memory exercise |

### Example

```json
{"id":"01J8ZC3R8K9Q2X4Y5Z6W7V8U9U","date":"2026-09-11","system":"personal","source":"retro","type":"faces","cycle":"2026-W37","scores":{"flexible":3,"adaptive":4,"coherent":3,"energizing":2,"stable":4},"lowest_face":"energizing","integration_move":"protect one no-meeting evening","move_status":"open"}
```

## The "other" escape valve

`domain`, `anti_pattern`, and `source` are strict enums — typos fail
loudly, which is the point of an enum. But a strict enum with no way out
is exactly the kind of rigid-without-flexible failure FACES warns about,
so each one has an `other` value plus a matching `_other` free-text
field, required only when `other` is chosen. Loosening a strict enum
later is easy; tightening a loose one after months of freeform values is
not — so start strict, escape through `other` when something genuinely
doesn't fit, and treat a pattern in your `other`s as a proposal to
extend the enum, not a reason to abandon it.

## When to reach for something heavier

JSONL is the right starting format: greppable and diffable by hand, and
an append-only writer (you, or a tool) can't easily corrupt it. Move to
SQLite once you want real queries — trend charts, cross-system rollups —
rather than "grep and eyeball it." Import is a one-liner
(`jsonlines` → `sqlite-utils insert`); JSONL can stay the source of truth
or get retired from there. Don't build that layer before you have data
to query.
