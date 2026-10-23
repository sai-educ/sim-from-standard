# Lesson contract

A simulation passes only if every rule holds.

## The mechanism

1. **The concept is the model.** The only way to make the model behave is to obey the concept. Decoration that doesn't respond to the learner's input fails.
2. **One surprise.** The misconception predicts X; the model shows Y. If a learner holding the misconception would not be surprised, redesign the mechanism.
3. **Same source of truth.** Readouts, drawing and feedback derive from one state object. No hard-coded numbers.
4. **Cheap to retry.** Reset is one control. Every manipulation gives feedback in under 100 ms.

## The four beats

| Beat | Rule |
|---|---|
| Predict | Forced-choice or numeric commit before controls unlock. Record it; reveal it later next to the outcome. |
| Play | At most three controls. Readouts update live. No hidden state. |
| Explain | Appears only after the surprise has happened. One or two sentences naming the pattern. |
| Check | One transfer item in a different context. Wrong-answer feedback names the misconception and points back to the model. |

## Accessibility and robustness

- Keyboard-operable, visible focus, labels on every control.
- `aria-live="polite"` for readouts; do not announce every animation frame.
- `prefers-reduced-motion`: stop auto-animation, keep step buttons.
- Colour is never the only signal.
- Works offline from a `file://` URL.

## Teacher note (inside the page, collapsed)

Standard code and text, target misconception, three questions to ask students, two extensions, and one honest limit of the model ("this simulation does not show...").

## Style family

Match `examples/`: system font stack, a single accent colour, rounded cards, light and dark via `prefers-color-scheme`, max width 880px, 16px gutters.
