---
name: sim-from-standard
description: Turn a curriculum standard or learning objective (CCSS, NGSS, state or national standards, or a plain-language objective) into a single-file interactive simulation that confronts a specific student misconception. Use when the user wants an interactive explorable, simulation, or "play with it" lesson object for a concept, or mentions a standard code like 5.NF.B.5 or MS-LS4-6.
---

# sim-from-standard

Build one self-contained HTML file in which the **concept is the physics of the toy**. The learner changes something, the model responds, and the response contradicts the misconception. No slides, no quiz-with-a-picture.

## Workflow

1. **Parse the standard.** Extract grade band, the exact verb ("interpret", "construct", "compare"), and the underlying concept. If the input is a code, state the standard's text back in one line.
2. **Name one misconception.** Pick the single most common, research-documented wrong idea for this concept. Write it as the student would say it ("multiplying always makes things bigger"). If you are not confident it is documented, say so rather than invent one.
3. **Invent the mechanism.** Choose a manipulable model where the correct idea is the only way the model can behave. The misconception must produce a visible surprise. Read `references/lesson-contract.md` for the rules this step must satisfy.
4. **Use the four-beat structure**, always in this order:
   - **Predict**: learner commits to an answer before touching anything.
   - **Play**: direct manipulation with live readouts driven by the same model that draws the picture.
   - **Explain**: the sim names the pattern after the learner has seen it, not before.
   - **Check**: one transfer question in a new context, with feedback that addresses the misconception by name.
5. **Write the file.** Single `.html`, no build step, no network requests, vanilla JS plus SVG or canvas. Copy the visual language and layout of `examples/` so output looks like one family.
6. **Add the teacher note** inside the page (collapsed `<details>`): standard code, target misconception, what to ask students, two extension prompts.
7. **Verify before delivering** (see Verification). Do not report done until each item has been checked.

## Verification

- Open the file in a headless or real browser; take a screenshot at desktop and 390px width.
- Console has zero errors and zero warnings.
- Every control works by keyboard; focus is visible; dynamic readouts live in an `aria-live="polite"` region.
- Text contrast is at least 4.5:1 in light and dark mode; motion respects `prefers-reduced-motion`.
- The misconception actually triggers: manually run the prediction the misconception would make and confirm the model contradicts it.
- The numbers on screen are computed from the model, never hard-coded.

## Output

Deliver the HTML file plus a one-paragraph summary: standard, misconception, mechanism, and what the learner will see that surprises them. State plainly anything you could not verify.

## Do not

- Explain the concept in text before the learner has predicted.
- Use a quiz where a manipulable model would work.
- Fabricate research citations or misconception prevalence figures.
- Add accounts, tracking, analytics, or external assets.
