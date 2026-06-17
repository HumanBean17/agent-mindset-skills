# Agent Mindset Skills

> 🇬🇧 English · 🇷🇺 [Русский](./README.ru.md)

A set of **working postures** — each one sets an agent's operating mode for a task. They answer questions like *How much autonomy? Speed or quality? Do it myself or delegate? Minimal change or bold bets?*

These are **invoked manually** (for example `/surgeon` or by naming the posture in your prompt). They do **not** auto-trigger — you pick the posture that matches the situation and switch when the situation changes. Each posture is intentionally opinionated: it optimizes for one thing and says out loud what it deliberately skips. That tradeoff is the point.

## Pick by situation

| Situation | Posture |
|---|---|
| You want analysis or a recommendation — no changes | `advisor` |
| Stress-test a plan or change before you commit | `skeptic` |
| Throwaway script or a hard time-box | `sprinter` |
| New module / prototype where structure is the bet | `trailblazer` |
| Hotfix or fragile legacy code — touch as little as possible | `surgeon` |
| Library code, public API, or shared dependency | `perfectionist` |
| Short, well-scoped task — just do it, no machinery | `solo-operator` |
| Trusted goal you can walk away from, end-to-end | `autonomous-executor` |
| Long session with parallelizable work — delegate | `orchestrator` |
| You want to stay in the loop, step by step | `pair-partner` |
| Long project — must hand off context cleanly | `archivist` |

## How they relate

**Autonomy** — who drives each step:
`pair-partner` (you drive each step) → `autonomous-executor` (agent drives, you leave)

**Speed ↔ Quality** — what you optimize for:
`sprinter` / `trailblazer` (ship fast, cut corners) ↔ `perfectionist` (exhaustive, polished)

**Delegation** — do vs. coordinate:
`solo-operator` (do it all directly) → `orchestrator` (delegate to subagents)

**Disposition** — constructive vs. adversarial:
`advisor` (reason and recommend) ↔ `skeptic` (attack and break)

Two postures are about *style* rather than a tradeoff axis, and they layer onto any of the above:

- `surgeon` — minimal footprint (how much to touch)
- `archivist` — documentation-first (what to leave behind)

`sprinter` and `trailblazer` sit on the same (fast, cut-corners) end of the speed axis but differ in intent: `sprinter` ships a **disposable** result against a clock with no design ambition; `trailblazer` makes **structural bets** on empty ground to establish a shape. Same shortcut, different goal.

## Combining and contradicting

Most postures are chosen one-per-task, but the style postures layer cleanly: run an `autonomous-executor` task with `surgeon` discipline, or keep `archivist` notes through a `trailblazer` spike — name both in your invocation.

Several pairs are near-opposites (`sprinter` ↔ `perfectionist`, `advisor` ↔ `skeptic`, `solo-operator` ↔ `orchestrator`). Invoking both is a contradiction; pick the one your situation calls for.
