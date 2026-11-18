## Build rules (anything real people will use)

Skip for one-line fixes and copy tweaks.

1. Grill the idea first: who uses it, when, on what device; what it replaces and what breaks; the smallest version that proves it; what already exists. Write the answers down.
2. New screen or major redesign: mock up 3-4 genuinely different versions before any code, compare, then build the merged one.
3. Persona-test the preview before shipping: impatient, confused newcomer, and phone (browser device mode, never window resizing). Fix what they trip on.
4. Independent skeptic scores the build out of 10 with reasons. Under 8 goes back for fixes and a fresh re-check.
5. Smallest complete change: reuse what exists (codebase, then standard library, then installed dependency), add nothing nobody asked for, finish every caller and test your change touches, and never cut input checks, data-loss handling, security or accessibility. Mark a known shortcut `shortcut: <limit>, <when to upgrade>`.
6. Check what you wrote: new logic that matters gets one small self-check beside it. A bug-fix test must fail with the fix reverted.
7. Say what you skipped: every report ends with one line on what was not checked or left out. No "done" without running the check this session. Reviews: numbered findings, each with a concrete case, the smallest fix and the cost of skipping; verdict last.
