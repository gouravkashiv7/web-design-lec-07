# Project 1, Part 3: A Visual Design Pass

**Lecture 7 · Typography & Visual Design**
**Lab time:** 35 minutes in class · **Due:** before Lecture 8
**You need:** your Project 1 folder with `styles.css` from Lecture 6

---

## 1. What you are doing

Turn Project 1 into a site that looks **designed**, using a small set of deliberate choices called **tokens** instead of random numbers.

By the end:

- every font size, space and colour in `styles.css` comes from a token in `:root`
- every text colour passes **4.5 : 1** contrast
- a new page, `style-guide.html`, shows your whole system at a glance

**The rule for today:** no magic numbers. If you type `17px` or `#13253a` outside `:root`, it's a bug.

## 2. Where things are in this repo

```
project/
├── project-brief.md            ← this file
└── starter/
    ├── tokens-starter.css      ← paste at the TOP of your styles.css, then fill in
    ├── style-guide.html        ← copy into your Project 1 folder (homework)
    └── ai-critique-table.md    ← homework
exercises/
└── silent-bugs/                ← 3 bugs, no error messages
```

## 3. Lab tasks

| Time | Step | Done when | Checkpoint |
|---|---|---|---|
| 50–55 | **Find your magic numbers.** In `styles.css`, Ctrl + F for `px`, `rem` and `#`. Write every value on paper. | You have a list of every value you used | |
| 55–65 | **Define tokens.** Paste `tokens-starter.css` at the top of `styles.css`. Fill in 4–6 font sizes, 5–6 spacing steps, 4–6 colours. | `:root` has all three groups | ✋ Show your `:root` |
| 65–75 | **Replace.** Swap every value below `:root` for a `var(--token)`. Apply the type scale to `h1`, `h2`, `h3`, body and small text. | Ctrl + F `px` finds nothing below `:root` | |
| 75–80 | **Change one token.** Edit `--color-accent`. Refresh every page. | Every accent on every page changed at once | ✋ Show the change spreading |
| 80–85 | **Check contrast.** DevTools → Styles → click each text colour's swatch. Read the ratio. | Every text colour is 4.5 : 1 or better | ✋ Show your lowest ratio |

### Rules for your tokens

| Group | How many | Guideline |
|---|---|---|
| Font sizes | 4–6 | One size per heading level. Use `rem`, not `px`. |
| Spacing | 5–6 | Each step roughly doubles: 4, 8, 16, 24, 32, 48. |
| Colours | 4–6 | Ink (text), muted (secondary text), accent, line (borders), surface (backgrounds). |
| Line height | 1 | Body text at 1.5–1.7. |

Use one or two font families. Keep borders and shadows light: if everything is decorated, nothing stands out.

## 4. Debugging exercise: silent bugs

Open `exercises/silent-bugs/index.html` with Live Server. There are **3 bugs and none of them shows an error.**

Test for them deliberately:

1. **Squint test:** blur your eyes. What do you read first? Is that right?
2. **Contrast check:** colour picker on every text colour.
3. **Computed pane:** is the padding what `:root` says it should be?
4. **Search the token:** Ctrl + F each `var(--...)` name. Is it spelled the same in `:root`?

Fix one bug at a time and log each one: expected / actual / evidence / cause / fix.

## 5. Stuck? Do this before asking

- **A `var()` does nothing?** Computed pane shows the fallback, not your value. Check the token's spelling in `:root`, including the two dashes.
- **Every heading looks the same?** Another rule sets `font-size` on all headings. Find it in the Styles pane; it won't be crossed out.
- **Can't pick a colour?** Start from the starter values; they already pass contrast.
- **Page looks busy?** Remove borders and shadows first, then add back only the ones that group things.

## 6. Definition of done

- [ ] `:root` defines 4–6 font sizes, 5–6 spacing steps and 4–6 colours
- [ ] Below `:root`, every size, space and colour uses `var(--...)`
- [ ] `h1`, `h2`, `h3`, body and small text each use one size from the scale
- [ ] Body line height is between 1.5 and 1.7
- [ ] Every text colour passes 4.5 : 1 (3 : 1 for large headings)
- [ ] Squint test: the most important thing on each page stands out first
- [ ] `style-guide.html` shows type scale, colour swatches with ratios, spacing bars, a button and a card
- [ ] Every page still validates with zero errors

## 7. AI critique (homework)

Take a screenshot of your home page and ask:
*"Here is a screenshot of my page. Identify the visual hierarchy problems. Don't rewrite my CSS."*

Mark every suggestion **Adopt**, **Adapt** or **Reject** in `ai-critique-table.md`, with one line of reasoning. Use your own tests (squint, contrast, tokens) as the reason.

## 8. What to submit

1. Your Project 1 folder, zipped, with tokens in `styles.css`
2. `style-guide.html` inside it, linked from nowhere (open it directly)
3. `ai-critique-table.md`, filled in
4. Your silent-bugs bug log

## 9. How it is marked (15 marks)

| Area | Marks | Full marks means |
|---|---|---|
| Tokens defined | 3 | Font, spacing and colour groups in `:root`, sensible counts |
| No magic numbers | 3 | Every value below `:root` uses a token |
| Type scale and hierarchy | 3 | One size per level; passes the squint test |
| Contrast | 2 | Every text colour at 4.5 : 1 or better |
| Style guide page | 2 | All five parts present and using the real tokens |
| AI critique table | 2 | At least 4 suggestions, each with a decision and a tested reason |
