# sim-from-standard

**Give your AI agent a curriculum standard. Get back a simulation that fights the misconception.**

`sim-from-standard` is an agent skill. Name a standard (`CCSS 5.NF.B.5`, `NGSS MS-LS4-6`, or a plain objective) and the agent builds a single-file interactive HTML simulation in which the concept *is* the physics of the toy. No slides, no quiz with a picture, no build step, no accounts.

> Built by a learning scientist. Every simulation targets one documented misconception and follows a strict predict → play → explain → check loop.

## Gallery

| Standard | Misconception it attacks | Simulation |
|---|---|---|
| CCSS 5.NF.B.5 | “Multiplying always makes things bigger.” | [Scale Machine](examples/scale-machine.html) |
| CCSS 7.SP.A.1 | “A small sample mirrors the population.” | [Jar of Beads](examples/jar-of-beads.html) |
| NGSS MS-LS4-6 | “Organisms change because they need to.” | [Moth Forest](examples/moth-forest.html) |

Open [`examples/index.html`](examples/index.html) in any browser. Everything works offline.

## Quick start

Install the skill for Claude Code:

```bash
mkdir -p ~/.claude/skills && cp -R skills/sim-from-standard ~/.claude/skills/
```

Then ask:

```text
Use sim-from-standard for CCSS 6.RP.A.3, ratios and unit rates.
```

For other agents that read `SKILL.md` files, copy the same folder into that agent’s skills directory.

## What makes it different

- **The concept is the mechanism.** If a student holding the misconception wouldn’t be surprised, the design fails.
- **Predict first.** Controls unlock only after the learner commits to an answer, and the sim reveals it next to the outcome.
- **One source of truth.** Readouts, drawing and feedback come from the same state, never hard-coded.
- **Teacher-ready.** Each page carries a collapsed note: standard, misconception, questions to ask, extensions, and the model’s honest limits.
- **Accessible by contract.** Keyboard operation, live-region readouts, reduced-motion support, light/dark contrast.

The full rules are in [`skills/sim-from-standard/references/lesson-contract.md`](skills/sim-from-standard/references/lesson-contract.md).

## How it works

1. Parse the standard and grade band.
2. Name one research-documented misconception, or say it isn’t sure.
3. Invent a manipulable model that makes the misconception visibly fail.
4. Write one HTML file in the shared visual family.
5. Verify in a browser: no console errors, keyboard works, mobile width, the surprise actually happens.

## Limits

- Misconceptions come from the model’s knowledge of the literature. Verify against sources before publishing claims about prevalence.
- Simulations are teaching aids, not assessments.
- Models are deliberately simple; each page states what it does not show.

## Roadmap

- Standards index with a misconception catalogue per grade band
- Per-sim prediction export (CSV) for classroom discussion
- Translation of in-page text
- Community gallery: submit a sim for a standard we lack

## Contributing

Add an example under `examples/` that satisfies the lesson contract, and add it to the gallery table and `examples/index.html`.

## License

MIT
