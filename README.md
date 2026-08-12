# lazysteve-content

Memory / thread for the **LazySteve daily content strategist** — the scheduled
Routine that produces the TikTok build-reveal digest for @lazysteve_es.

Attach this repo to that Routine so every run reads the history and writes back,
instead of starting cold with the same briefs every time.

## Files (all under `content/`)

- **`digest-log.md`** — the agent appends one line per FULL digest. It reads this
  at the start of every run: if today's date is already logged → it runs in
  LIGHT mode; otherwise FULL mode, then appends today's line and commits.
- **`posted.md`** — **you** fill this after publishing a video. The agent reads
  it to (a) NOT repeat a build/hook already posted and (b) build on what worked.
- **`performance.md`** — **you** fill this from TikTok analytics. The agent reads
  it to double down on formats/topics that performed and drop what flopped.

The agent never invents data for these files. If a file is empty it says so and
runs on research only — so it's safe to leave `posted.md` / `performance.md`
blank at first; the value grows as you fill them.

## Wiring

1. Attach this repo to the content Routine (the "Seleccionar un repositorio"
   step) with **write** access.
2. That's it — the agent reads `content/*.md` at the start and commits the
   `digest-log.md` line at the end.
