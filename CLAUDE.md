# Spacefast demos

Each top-level folder is one demo site, deployed to its own Space on the **Ryan - DevRel** Spacefast team.

Every demo has to be three things: **clear in its purpose**, **functional**, and **fun to look at and use**. `blocks-7-1/` is the reference for fun and personality. `wp-kses-tester/` is the reference for clear instructions and feedback. Before building a new demo, open both.

## Clear in its purpose

- **The headline is the question the demo answers**, phrased the way the visitor would ask it: "Will my block break?", "Does the new wp_kses() change your HTML?". No product names or feature labels as the headline.
- **A small eyebrow above it sets the context** (the WordPress version or feature), and **one short paragraph below it** says what the tool does and why it matters right now.
- **Say what to do.** Either numbered steps or one obvious primary action. Someone landing cold should know their first move within a few seconds.
- **Let people see it work before they bring their own input.** Offer a "Load broken example" button or example chips.
- **Show where results will appear before there are any.** Use an empty state like "Your before and after will show up here."
- **Results are in plain language first.** Give a verdict ("No change", "Changed", "Totally borked"), then the detail, then a short hint about why it happened.
- **Be honest about limits.** If the demo reads patterns instead of running code, or can't promise a result, say so where people will see it (see the caution-tape note in `blocks-7-1/`).

## Functional

- **It does the real thing, or says exactly what it does instead.** `wp-kses-tester/` runs WordPress nightly in the browser with Playground rather than faking output. Example outputs on the page must be verified, not copied from a post.
- **Every action gets visible feedback:**
  - A loading state, with the reason a button is disabled.
  - A busy state while it works.
  - A result that's clearly new, such as an animation or a timestamp.
  - A notice when the input changed since the last run.
- **Nothing runs automatically in a way that makes the main button look broken.** If clicking the primary button produces an identical screen, people think it did nothing.
- **Always include a Reset or Clear.**
- **Accessible:**
  - Real labels.
  - `aria-live` on results.
  - Visually hidden text when a heading is split into animated letters.
  - Decorative art is `aria-hidden`.
  - A keyboard shortcut for the main action is a nice extra.
- **Works on a phone:** a 16px side gutter, no horizontal scroll, and stacked layouts under ~760px.
- **One self-contained `index.html` with no build step.** External code only from pinned CDN URLs, fonts only from Google Fonts.
- **Test it in a real browser before publishing:** every example, every button, empty input, light and dark themes.

## Fun

- **Give it a personality that comes from the topic.** A character or a metaphor, not stock decoration. In `blocks-7-1/` that's a block mascot that cracks and sweats, a Bork-o-Meter gauge, and headline letters that fall when code breaks.
- **Match the fun to what the demo shows.**
  - **When the result can go either way** (pass/fail, safe/broken), a mascot or meter that reacts is great. Drive it from state (`data-state`, `data-distress` on `<body>`): confetti when things are fixed, debris and a wobbling frame when they break.
  - **When the result is always a difference to look at** (like `wp-kses-tester/`, where the output always changes and the point is how it changes), skip the score and the reacting character. Put the fun into how the difference is presented: the look, the highlighting, the labels.
  - Either way, the fun is part of the answer, not wallpaper.
- **A bold, warm look, not generic SaaS:**
  - A warm off-white background with dark ink text.
  - WordPress blue plus two or three bright accents (pink, yellow, green).
  - Chunky ink borders and hard offset shadows (`box-shadow: 6px 6px 0`).
  - An expressive display font (Bricolage Grotesque) paired with a mono (JetBrains Mono).
- **Playful copy in Ryan's voice for labels and reactions** ("Bork-o-Meter", "Seriously. Do it.", "Higher number, more borked."). Instructions and warnings stay plain and literal.
- **Light and dark themes,** both defined as CSS custom properties.
- **Respect `prefers-reduced-motion`** by turning animations and transitions off.
- **Fun never gets in the way of function.** Animations are decorative, don't block input, and never hide the result.

## Every demo page ends with "Built on Spacefast"

Put it in the footer, linking to https://spacefast.com:

```html
<p>Built on <a href="https://spacefast.com">Spacefast</a>.</p>
```

If the footer already has a short credits line, append `Built on <a href="https://spacefast.com">Spacefast</a>.` to it instead of adding a new paragraph.
