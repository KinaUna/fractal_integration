# Fractal Integration Guidelines (FIG)

Guidelines for building systems — software, products, teams, and beyond — where
quality lives in the *connections* between parts, not just the parts
themselves. Written for both humans and AI agents to read, adopt, and act on.

**The core idea:** most failures don't happen inside components — they happen
at the seams where components meet. Integration here means two things done
together: **differentiating** a system into distinct parts, and **linking**
those parts back into a coherent whole. Do only the first and you get
fragmentation. Do only the second and you get an undifferentiated blob. Doing
both, at every scale — a function, a team, an organization, a life — is why
this is *fractal*: the same pattern repeats regardless of how far you zoom in
or out.

## Where to start

- **New here?** Start at [`generic/START-HERE.md`](generic/START-HERE.md) —
  orientation for reading the rest.
- **Want the theory first?** [`generic/README.md`](generic/README.md) lays
  out the core premise and principles.
- **Bringing FIG into your own project?**
  [`generic/adopting-fig.md`](generic/adopting-fig.md) covers how to copy
  this in without your copy silently drifting from the source.

## Repository structure

- `fractal_integration/`
  - [`generic/`](generic/) — the domain-neutral core: FIG as it applies everywhere
    - [`README.md`](generic/README.md) — core concept and principles
    - [`START-HERE.md`](generic/START-HERE.md) — orientation, read this first
    - [`domains-of-integration.md`](generic/domains-of-integration.md) — the 21 kinds of linkage to look for
    - [`anti-patterns.md`](generic/anti-patterns.md) — named failure modes and their fixes
    - [`the-human-system.md`](generic/the-human-system.md)
    - [`in-code.md`](generic/in-code.md) — FIG applied to software
    - [`in-product.md`](generic/in-product.md) — FIG applied to product
    - [`product-as-integrator.md`](generic/product-as-integrator.md)
    - [`everyday-life.md`](generic/everyday-life.md)
    - [`adopting-fig.md`](generic/adopting-fig.md) — how to fork/differentiate this for your own use
    - [`further-reading.md`](generic/further-reading.md)
    - [`examples/`](generic/examples/README.md)
    - [`templates/`](generic/templates/design-doc.md) — design review, postmortem, retro templates
  - `<domain>/` — future: FIG differentiated for a specific field, profession, or situation (not yet added)

## How this repo grows

`generic/` is the reference version — differentiated as little as possible,
so it stays applicable anywhere. As specific domains need their own
adaptation (a profession, a team function, a kind of project), they get their
own top-level folder here, each one taking the generic core and
differentiating it further for that context — the same differentiate-and-link
pattern the guidelines themselves describe, applied recursively to the
guidelines. `generic/in-code.md` and `generic/in-product.md` are the existing
examples of this at the software/product layer; new domain folders would sit
at the same level as `generic/` and follow the same shape.

## For AI agents

These guidelines are meant to be read and applied directly by an AI agent,
not just a person — that's part of why this lives as a plain, structured
repo rather than a slide deck. See the adoption prompt in
[`generic/adopting-fig.md`](generic/adopting-fig.md) for a working example of
handing this repo to an agent and asking it to write a domain-specific guide.

## Examples of projects using Fractal Integration
- [Kumunita](https://github.com/KinaUna/kumunita)


## Status

This is a living, evolving document set — expect it to be revised as the
ideas get tested against real use.

Licensed under [CC BY 4.0](LICENSE) — you're free to copy, adapt, and reuse this,
including commercially, as long as you credit the source.
