# Marketing OS music toolbox

Private audio library for Marketing OS video work (nuBeam Partners / Seqnced). Exported from `tools/music/` in Marketing OS by `scripts/export-music.sh`.

**Nothing here is licensed.** These are copyrighted songs kept for internal editing reference. Organic posts only, preferably by adding the same sound from the Instagram sound library when posting. Never use them in paid ads, and never make this repo public.

## Layout

| Path | What |
|---|---|
| `tools/music/*.m4a` | Full tracks (Shazam-verified unless the README says otherwise) |
| `tools/music/reel-cuts/<track>__reel-<id>.m4a` | Reel-matched cuts: the same start point, loops, jumps and speed as the reference reel, full reel length, music only |
| `tools/music/README.md` | Source, licence and verification notes per track |
| `.claude/rules/music-cues.md` | Cue sheet: where each song starts and where to use it. Read this first |

Not included: `tools/music/_sources/` (reel downloads and Demucs stems). They can be rebuilt from the reel links in the README.

## Using it in a Marketing OS checkout

Copy `tools/music/` into the same path in Marketing OS (the rules and skills expect `tools/music/`). Then follow `.claude/rules/music-cues.md`: start each song at the reel's cue point, use the reel-matched cut when one exists, trim and fade only the end.
