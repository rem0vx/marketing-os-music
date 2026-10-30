# Music library: where each song starts and where to use it (Remo, 2026-10-28)

Remo, 2026-10-28: "make sure we are using all the correct songs/audios and using the same point of the track so it matches the reference reels", saved as a rule so new chats use them right.

Library: `tools/music/`. Overview of what to pick (go-to, try, avoid, usage counts): `tools/music/LIBRARY.md`. Full source, licence and verification notes: `tools/music/README.md`. Read this table first; open the README only for detail.

## Rules
- When a video uses a song from a reference reel, it starts at the reel's cue point below, not at 0:00 of the track and not at a random section.
- If a reel-matched cut exists, use it: `tools/music/reel-cuts/<track>__reel-<id>.m4a`. It already has the right start, edits (loops, jumps) and speed, and runs the full length of the reel. Trim the tail to the video length and fade out the end; do not re-cut the start.
- Do not normalise the cut to -14 LUFS on its own; set its level under the voice (walk-talks -12 LU, trial reels about -20 LU, see memory) and do the final -14 LUFS on the full mix.
- Every track here is NOT licensed: organic posts only, and preferably add the same sound from the Instagram sound library when posting. Never in paid ads.
- New track from a reference reel: Shazam the Demucs music stem every 2 s, calibrate Shazam offsets against the downloaded file, build a reel-matched cut, check it against the reel, then add a row here and in the README.
- A Shazam match only proves the melody. Before building from the official track, compare the reel's music to it (frequency balance, bass, speed). If they differ (an Instagram edit, remix or bass-boosted version), use the reel's own music: Demucs the voice out, check the stem has 0 words with `tools/transcribe-long.sh`, save it as `reel-cuts/<song>-ig-edit__reel-<id>__extracted.m4a`. Or ask Remo for the sound name shown on the reel in the Instagram app.
- Shazam offsets are not exact track times. MY EYES and Radiohead read 0.78 s early, Equilibriums 0.00 s. Repetitive beats can also return a repeat of the same bar, so confirm loops by matching the cut against the reel's sound (spectrum), not by Shazam alone.

- Finding where reels start a library song (2026-10-30, cheapest way): treg `tikhub.x.instagram-v2-search-music` (keyword, $0.002) gives the IG sound id, then `tikhub.x.instagram-v1-fetch-music-posts` (music_id, $0.001, run calls one at a time) lists reels with `clips_metadata.music_info.music_consumption_info.audio_asset_start_time_in_ms`: Instagram's own record of the part each reel uses. The most common value is usually IG's highlight (`highlight_start_times_in_ms`). Then align IG's sound file (`fast_start_progressive_download_url`) against our file and check 1 to 2 reels by audio: the IG file plays about 0.13 s late (encoder padding), and our file can have its own offset. Write the cue in OUR file's time.

## Cue sheet

| Track file | Reel-matched cut | Reference reel | Starts at | Edits / speed | Use for |
|---|---|---|---|---|---|
| none (use the extracted reel music) | **my-eyes-ig-edit__reel-DbqkgAasReM__extracted.m4a** | DbqkgAasReM | 0 s of the extracted file | The reel uses an Instagram EDIT of MY EYES (bass-boosted, sped up, re-cut), not the official track. Remo, 2026-10-28, on a version built from the official track: "thats not the same sound from the IG reel I sent you at all". The extracted file is the reel's own music with the voice removed (Demucs; 0 words heard in it), 89 s. In the reel it sits about 8 LU under the voice | Confident talking head. **Remo approved 2026-10-28** under the C0180 walk-talk v4, from 0 s at -15 LU |
| my-eyes_travis-scott.m4a | my-eyes_travis-scott__reel-DbqkgAasReM.m4a (does NOT sound like the reel) | none | 15.72 s | Official track. Only the melody matches the reel; do not use it to match DbqkgAasReM | Only when Remo asks for the official MY EYES |
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
| outside-my-feelings-outro_arriez-king-dif.m4a | outside-my-feelings-outro_arriez-king-dif__yt-V8ddup1hPj0.m4a | YouTube V8ddup1hPj0 (Mr Nik Setting, "My $600k/mo appointment setting system") | 56.21 s | Straight to 98.23 s, then loops the block 88.21 to 98.23 s (10.02 s), 20 ms crossfades; cut is about 600 s. Matched to the ref's Demucs music stem: corr 0.81 to 0.98, within 0.12 s over 80 s. Ref sits about 11 LU under the voice | Second-channel BTS / YouTube talking heads (used in 2026-10-29-yt-mentee-walk at -12 LU) |
| seraphic_txmy.m4a | none | IG sound 587213663720245 (5.8K reels); verified De0P-qPJAEz, Dd8FAGbiKUJ | **1.63 s** (IG start 1.5 s, 8 of 12 top reels, IG's own highlight). Also 0.13 s (IG 0 s) | Straight through (IG music sticker, no edits) | Short-form bed |
| ray-mysterio-instrumental_the-alchemist.m4a | none | IG sound 486670981854169 (79K reels); verified DeW7zAUu1Cd (1.7M plays), DeoMDRgMpHV | **0.13 s** (IG start 0 s, 6 of 12). Also 1.63 s (IG 1.5 s, 4 of 12) | Straight through | Short-form bed |
| new-computers-instrumental_girlfriends.m4a | none | IG sound 1361450332645281 "New Computers" (15K reels); Dd-r47SO_5k, DeskknWyel7 match the IG sound at its stated start | **1.98 s** (IG start 1.5 s, 9 of 12). Mapped via the IG sound: ours = IG + 0.35 s, steady over the whole track | Our file is a much quieter, different master (-24.9 vs IG -14 LUFS, weak spectral match). For the exact IG sound use `_sources/frameio-short-form-musics/ig/ig_asset/girlfriends.mp4` from 1.63 s | **Talking-head bed** (30 of 36 checked reels have speech, Jev 2026-10-30) |
| every-living-breathing-moment_gabriel-piano.m4a | none | IG sound 1213929170639164 (23K reels); verified Dd_lIlztbEu, Dd8zXlOTWV7 | **5.29 s** (IG start 4.5 s, 7 of 12, IG highlight) | Straight through. Ours runs 0.66 s behind IG's sound and has 10 s more tail | **Talking-head bed** (29 of 37 checked reels have speech, Jev 2026-10-30) |
| echo-sax-end_caleb-arredondo.m4a | none | IG sound 1073574610962815 (324K reels); verified DZUrwODR8UN (747K plays), DeHuMWUO5bM | **0.84 s** (IG start 0 s, 6 of 12). Also 2.34 s (IG 1.5 s, 3 of 12) | Straight through. Ours runs 0.70 s behind IG's sound. The two remixes are not in IG's music library | Short-form bed |
| echo-sax-end-drill-remix_caleb-arredondo.m4a | none | none: not in IG's music library (searched 2026-10-30) | not measured | Straight through | Short-form bed |
| echo-sax-end-remix-mike-mvsk_caleb-arredondo.m4a | none | none: not in IG's music library (searched 2026-10-30) | not measured | Loud (-8.2 LUFS) | Short-form bed |
| do-i-clench-my-fists_ridgeclub.m4a | none | IG sound 28060501890200050 (302K reels); verified DeED1FvgX8Q (2.3M plays) | **1.48 s** (IG start 1.5 s, 7 of 12, IG highlight) | Straight through | Short-form bed |
| acido-iii-over-slowed_udiennx.m4a | none | IG sound 778863298353997 (652K reels); verified DeCIKp_peXp, DeJqpvIyURP | **9.00 s** (IG start 9 s, 5 of 12, IG highlight). Top reel DeJqpvIyURP (503K plays) uses 0.14 s (IG 0 s) | Straight through. Loud (-7.5 LUFS) | Music-only edits, not under voice (1 of 27 reels talk) |

Older rows (no cut) come from the README's Shazam notes and are less precise ("about"). Build a reel-matched cut the first time one is used.
