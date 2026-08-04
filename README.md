# skill-fx class board

A published snapshot of the status board for reconstructing Ragnarok Online skill
visual effects against the original client, class by class.

**Read it here: https://rul3ik9.github.io/skill-fx-board/**

Each row is one skill. For every effect id the client's own dispatch table fires
for that skill, the board carries the verdict (covered / missing / stand-in /
n/a), how it was established, and the stamps that record it — `@decoded` with the
handler address it was read from, `@covers` for a channel that ships, `@verified`
with the measured numbers and a hash that expires itself when the row is retuned.

## What this repo is

One generated `index.html`, nothing else. The page is self-contained: all data is
inlined, no server, no network, no build step. It is produced by
`publish_class_board.py` in the private tracker tree and pushed here.

**It is a frozen snapshot, not a live view.** The timestamp in the top-right is
the moment it was generated; it moves when a work batch republishes it.

Source code is deliberately not included — the board's own reading window onto the
port's implementation is stripped before publishing, so what is here is status,
verdicts and reverse-engineering notes about the original client.

History is intentionally flat. Every regeneration rewrites the whole file, so the
push amends rather than stacking commits; keeping them would grow this repo by the
file's full size on every batch.
