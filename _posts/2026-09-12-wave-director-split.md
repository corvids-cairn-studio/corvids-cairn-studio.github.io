---
title: "Splitting the wave director from the wave generator"
categories: [SpaceSects, process]
---

One autoload deciding both "when" and "what" was quietly making every new enemy pattern harder to add than the last one.

Here's the problem I kept running into: the same script decided *when* a wave should spawn and *what* should be in it. Every time I wanted a new enemy behavior, I ended up touching timing logic I didn't mean to change.

The fix was splitting it into two pieces:

- **WaveDirector** — owns pacing. When does a wave start, how long between spawns, when does the level escalate.
- **WaveGenerator** — owns content. Given "spawn a wave now," what enemies actually come out, based on the current difficulty curve.

Now adding a new enemy type is purely a WaveGenerator change, and tuning pacing is purely a WaveDirector change. Neither one has to understand the other's internals.

More on this as it settles in — next up is seeing how it holds together once I add the first mini-boss wave.
