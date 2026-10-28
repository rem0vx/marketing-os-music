# Music library: where each song starts and where to use it (Remo, 2026-10-28)

Remo, 2026-10-28: "make sure we are using all the correct songs/audios and using the same point of the track so it matches the reference reels", saved as a rule so new chats use them right.

Library: `tools/music/`. Full source, licence and verification notes: `tools/music/README.md`. Read this table first; open the README only for detail.

## Rules
- When a video uses a song from a reference reel, it starts at the reel's cue point below, not at 0:00 of the track and not at a random section.
- If a reel-matched cut exists, use it: `tools/music/reel-cuts/<track>__reel-<id>.m4a`. It already has the right start, edits (loops, jumps) and speed, and runs the full length of the reel. Trim the tail to the video length and fade out the end; do not re-cut the start.
- Do not normalise the cut to -14 LUFS on its own; set its level under the voice (walk-talks -12 LU, trial reels about -20 LU, see memory) and do the final -14 LUFS on the full mix.
- Every track here is NOT licensed: organic posts only, and preferably add the same sound from the Instagram sound library when posting. Never in paid ads.
- New track from a reference reel: Shazam the Demucs music stem every 2 s, calibrate Shazam offsets against the downloaded file, build a reel-matched cut, check it against the reel, then add a row here and in the README.
- Shazam offsets are not exact track times. MY EYES and Radiohead read 0.78 s early, Equilibriums 0.00 s. Repetitive beats can also return a repeat of the same bar, so confirm loops by matching the cut against the reel's sound (spectrum), not by Shazam alone.

## Cue sheet

| Track file | Reel-matched cut | Reference reel | Starts at | Edits / speed | Use for |
|---|---|---|---|---|---|
| my-eyes_travis-scott.m4a | my-eyes_travis-scott__reel-DbqkgAasReM.m4a | DbqkgAasReM | 15.72 s | Straight through, 0.86% faster and higher (sped up to 1.0086x). Proven for the first 28 s | Confident talking head; loud, keep low under voice |
| equilibriums-edge_remyyybeatz.m4a | equilibriums-edge_remyyybeatz__reel-DXAIaEsjFFA.m4a | DXAIaEsjFFA (DaDuAqHOAst overlaps it, not aligned) | 71.52 s | Loops the block 71.52 to 83.87 s (12.347 s) back to back | Steady beat under a talking head (used in 2026-10-28-c0184) |
| adagio-in-c-minor_nicholas-britell.m4a | adagio-in-c-minor_nicholas-britell__reel-DUyGajyjoPw.m4a | DUyGajyjoPw | 41.96 s | At 39.75 s into the video (track 81.71 s), hard jump to 5.27 s of the track, then straight on | Serious story, wealth/power, history |
| everything-in-its-right-place_radiohead.m4a | everything-in-its-right-place_radiohead__reel-DZIZXL5s4kv.m4a | DZIZXL5s4kv | 1.08 s (±0.5 s, one proven window) | Straight through (only the first 15 s are proven) | Reflective talking-head bed |
| she-will-instrumental-slowed_932sounds.m4a | none | "remo sf" reference | 0.79 s | Straight through | Walk-talk night bed |
| me-and-the-devil-instrumental-slowed_luke-muzzic.m4a | none | DemxjfaiiiX | 46.7 s | Straight through | Dark/serious |
| resonance_home.m4a | none | De6H1jpPoOM | about 2.4 s | Straight through | Reflective story, night/city |
| spring-ii-largo_vivaldi-michelle-ross.m4a | none | Dcxwjz0qcEM | about 3 s | Quiet track (-23 LUFS), gain up | Old-master paintings, history |
| what-to-do-me-remix_guy-gerber.m4a | none | DdD_3gkq9YS, Dc-2R25qEjV | Walk-talks: **35 s** (Remo approved, C0070 v2, -12 LU). About 150 s only when matching those reference reels (not calibrated) | Straight through | Default walk-talk bed |
| stay-interstellar-slowed-reverb_starsounds.m4a | none | DRR9jtFjGj7 | about 1.1 s | Straight through | Calm talking head / screen walkthrough |
| leanin-slowed_cormill.m4a | none | DfA4UbZAQYf | not measured | Not measured | Talking-head bed |
| 4x4_travis-scott.m4a | none | DbQAuzHs0cy | not measured | Not measured | Not for walk-talks (Remo, 2026-10-26) |

Older rows (no cut) come from the README's Shazam notes and are less precise ("about"). Build a reel-matched cut the first time one is used.
