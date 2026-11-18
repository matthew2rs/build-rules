# Build rules for AI-assisted builds

Seven rules to follow before you ship anything real people will use: a web app, an internal tool, a store page, a feature. They work with Claude Code or any AI coding agent. They do not apply to one-line fixes or copy tweaks.

Rules 1 to 4 are adapted from Greg Isenberg's agent workflow post, cut down to what you can do with no new paid tools. Rules 5 to 7 are adapted from [ponytail](https://github.com/DietrichGebert/ponytail) by Dietrich Gebert (MIT), rewritten and trimmed for non-technical owners.

## 1. Grill the idea before you build

Before any code, answer these in writing (in your notes or handoff file):

- Who uses it, in which moment, on which device?
- What does it replace, and what breaks if it goes wrong?
- What is the smallest version that proves it works?
- What already exists that does part of this?

Only ask the person who owns the project what your answers can't settle, in one message. Decide everything else yourself.

## 2. New screen? Mock up 3-4 versions first

For a new screen or a major redesign, make 3-4 genuinely different versions as quick HTML or images. Look at them side by side. Pick one, or take pieces from two, then build the merged version. Small changes to an existing screen skip this step.

## 3. Persona-test before you ship

Have a cheap AI agent click the 2-3 key flows on the preview, once as each person:

- **Impatient:** skips the instructions and clicks the first thing.
- **Confused:** a new person who doesn't know your words.
- **On a phone:** mobile width, checked in your browser's device mode, never by dragging the window smaller.

Fix what they trip on, then ship. Write the result in one line on the task or handoff.

## 4. Scored skeptic

A separate, independent reviewer (not the one who built it) scores the build out of 10 and gives reasons. **Under 8 goes back** for fixes and a fresh re-check. Show the score when you ask for sign-off.

## 5. Smallest complete change

Solve the whole problem with the least new code. Take the first option that fully works:

1. Does it need to exist? Skip features, options and flexibility nobody asked for, and name what you skipped in one line.
2. Is it already in the codebase (a helper, component, pattern)? Use it the way the surrounding code does.
3. Does the standard library or the platform do it? Use that, unless the project has its own.
4. Is it in a dependency you already have? Use it. Never add a dependency for a few lines.
5. Otherwise write the minimum that works.

Be lazy about the solution, never about the change itself: finish every part the task touches, including the callers, tests and fixtures it breaks. Before fixing a bug, find every caller of the function you are about to change, then fix the root cause once in the shared code.

**Never cut:** checks on input from outside, error handling that prevents data loss, security, accessibility, and anything the person asked for.

A shortcut with a known limit gets a comment in this form, so it can be found and revisited: `shortcut: <the limit>, <when to upgrade>`. A shortcut with no upgrade trigger quietly becomes permanent.

## 6. Check what you wrote

New logic that matters (a branch, a loop, a parser, money, security, data writes, a whole new script) gets one small test or a self-check beside it. Trivial changes need none. For a bug fix, prove the test is real: it passes with the fix, fails with the fix reverted, then passes again once restored.

## 7. Say what you skipped

Every report ends with one line: what you did not check or left out, and any risk the reader must know. Never claim "works" or "done" without having run the check in the same session. Evidence first, then the claim.

When you review someone's change, number the findings so they can answer "fix 2 and 5". Each finding gets: what it is, the concrete case where it goes wrong (no concrete case, no finding), the smallest fix, and what happens if you skip it. Group them as must fix, should fix and nice to have, and finish with a one-line verdict.

## Using it with Claude Code

Copy `CLAUDE-snippet.md` into your project's `CLAUDE.md` so every session sees the rules.

## Not included, on purpose

Automatic error-to-fix pull requests, farms of headless browsers and other paid add-ons. They cost money without a proven gain at small scale.

## Licence

MIT. See `LICENSE`.
