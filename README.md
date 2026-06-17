# Agent Mindset Skills

> 🇬🇧 English · 🇷🇺 [Русский](./README.ru.md)

A set of **working postures** — each one sets an agent's operating mode for a task. They answer questions like *How much autonomy? Speed or quality? Do it myself or delegate? Minimal change or bold bets?*

These are **invoked manually** (for example `/surgeon` or by naming the posture in your prompt) — you pick the posture that matches the situation and switch when it changes. They're written so they *can* also surface automatically when a task clearly matches one, but the intended use is a deliberate choice. If more than one surfaces for a task, pick the single best match — only one posture should bind at a time (you can still layer a style posture like `surgeon` or `archivist` onto it). Each posture is intentionally opinionated: it optimizes for one thing and says out loud what it deliberately skips. That tradeoff is the point.

## Usage

Install each `<posture>/` directory into your agent's skills location, then invoke by name.

- **Claude Code:** copy the posture directories into `~/.claude/skills/` (or a project `.claude/skills/`), then run `/surgeon` (or name the posture in your prompt).
- **Codex:** place under `~/.agents/skills/`.
- **Other agents:** these are plain `SKILL.md` files with standard `name` / `description` frontmatter — drop them wherever your agent discovers skills.

Invoke one per task, or layer a style posture onto a doing one (see [Combining and contradicting](#combining-and-contradicting)).

## Pick by situation

| Situation | Posture |
|---|---|
| You want analysis or a recommendation — no changes | `advisor` |
| Stress-test a plan or change before you commit | `skeptic` |
| Throwaway script or a hard time-box | `sprinter` |
| Library code, public API, or shared dependency | `perfectionist` |
| New module / prototype where structure is the bet | `trailblazer` |
| Hotfix or fragile legacy code — touch as little as possible | `surgeon` |
| Existing code needs restructuring without changing behavior | `refactorer` |
| Short, well-scoped task — just do it, no machinery | `solo-operator` |
| Long session with parallelizable work — delegate | `orchestrator` |
| Trusted goal you can walk away from, end-to-end | `autonomous-executor` |
| Task is ambiguous — resolve intent before acting | `clarifier` |
| You want to stay in the loop, step by step | `pair-partner` |
| Long project — must hand off context cleanly | `archivist` |

## How they relate

**Autonomy** — who drives each step:
`pair-partner` / `clarifier` (you drive, or resolve ambiguity first) → `autonomous-executor` (agent drives, you leave)

**Speed ↔ Quality** — what you optimize for:
`sprinter` (fast, disposable) ↔ `perfectionist` (exhaustive, polished)

**Delegation** — do vs. coordinate:
`solo-operator` (do it all directly) → `orchestrator` (delegate to subagents)

**Disposition** — constructive vs. adversarial:
`advisor` (reason and recommend) ↔ `skeptic` (attack and break)

**Footprint** — how much you change, on what ground:

|                | existing code   | empty ground   |
|----------------|-----------------|----------------|
| **touch little**  | `surgeon`       | `sprinter` ¹   |
| **restructure**   | `refactorer`    | `trailblazer`  |

¹ `sprinter`'s home axis is speed — it appears here because disposable code is structurally minimal, not because the task is small.

`archivist` is a *style* layer — documentation-first — that layers onto any of the above.

## Combining and contradicting

Most postures are chosen one-per-task, but the style postures layer cleanly: run an `autonomous-executor` task with `surgeon` discipline, or keep `archivist` notes through a `trailblazer` spike — name both in your invocation.

Several pairs are near-opposites (`sprinter` ↔ `perfectionist`, `advisor` ↔ `skeptic`, `solo-operator` ↔ `orchestrator`, `surgeon` ↔ `refactorer`, `clarifier` ↔ `autonomous-executor`). Invoking both is a contradiction; pick the one your situation calls for.
