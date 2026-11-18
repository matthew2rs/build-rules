# Build rules for AI-assisted builds

Four rules to follow before you ship anything real people will use: a web app, an internal tool, a store page, a feature. They work with Claude Code or any AI coding agent. They do not apply to one-line fixes or copy tweaks.

The ideas are adapted from Greg Isenberg's agent workflow post, cut down to what you can do with no new paid tools.

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

## Using it with Claude Code

Copy `CLAUDE-snippet.md` into your project's `CLAUDE.md` so every session sees the rules.

## Not included, on purpose

Automatic error-to-fix pull requests, farms of headless browsers and other paid add-ons. They cost money without a proven gain at small scale.

## Licence

MIT. See `LICENSE`.
