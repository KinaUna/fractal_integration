# Anti-patterns

| Name | What it looks like | The fix |
|---|---|---|
| **Feature sprawl** | Parts accumulate with no linkage; the product is a bag of features. | Every initiative states which seams it integrates. |
| **God module** | Under-differentiation: one part everyone depends on, nothing testable in isolation. | Find the stable contract; split on it. |
| **Distributed monolith** | Over-differentiation: many parts, no integration; every change touches five services. | Re-differentiate on real seams; merge what always changes together. |
| **Green CI, red production** | We tested parts, not seams. | Seam tests + boundary observability. |
| **Metrics without loops** | Dashboards nobody acts on. | Every metric gets an owner, a threshold, a response action. |
| **Accidental integration** | It works, but nobody knows why; the knowledge is tribal. | Contracts, tests, ADRs. Make the linkage explicit. |
| **Silent coupling** | Undocumented assumptions between services or teams. | Explicit, versioned contracts; migrate dependents deliberately. |
| **Retros without actuation** | Reflection loop with no actuator. | Every action has an owner and deadline; next retro starts by verifying loops closed. |
