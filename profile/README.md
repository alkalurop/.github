# Alkalurops

Open-source DJ library tooling — names, folders, playlists, stems, and the boring glue between Apple Music, Traktor, and Rekordbox.

[alkalurops.org](https://www.alkalurops.org)

**Two GitHub homes, same repos:**

- **[ixamal](https://github.com/ixamal)** — where I commit. Issues and milestones live here.
- **alkalurop (this org)** — a public copy, refreshed around the **15th** each month so the story stays in one place without making you dig through my working org.

No audio in git. Ever. Just scripts, docs, and the paper trail of how a real crate got fixed.

---

## Pick what you need

| If you… | Open |
| --- | --- |
| Want files named like songs, not `Track 01`, and decks that agree on the path | [ix](https://github.com/alkalurop/ix) |
| Want stems on your Mac overnight (vocal / instrumental + Traktor stem file) | [stems](https://github.com/alkalurop/stems) |
| Moved the library and Traktor/Rekordbox lost the plot | [music_migration](https://github.com/alkalurop/music_migration) |
| Run Maschine + Traktor + Rekordbox on one machine and hate routing surprises | [blackhole](https://github.com/alkalurop/blackhole) |
| Want to browse and plan set ideas before touching a database | [ix_bangers](https://github.com/alkalurop/ix_bangers) |
| Want beatgrids on a whole playlist without clicking every track | [grid](https://github.com/alkalurop/grid) (GPL) |
| Want Blender stage stuff beside the booth | [stage](https://github.com/alkalurop/stage) (GPL) |

---

## Why I built this

I DJ. I also have a day job and a family. The library kept growing anyway — mix CDs tagged wrong, Beatport genres pasted as `EDM, House`, the same file twice because iTunes got creative, a USB drive that *was* the crate until you unplugged it.

I needed to **sort stems from full tracks**, file things **artist / album / title**, fix **genres and playlists** without living in three apps, and run **stem batches** when the names were finally true. All on nights and weekends. The point is to leave something **useful on GitHub** — Apache-licensed core, readable docs — not a locked cloud crate.

---

## How it works today

Mostly **Python and shell on your Mac**. Long jobs like **CRATER** and **BABYLON** tie hygiene, optional stem budgets, and deck sync together. Cursor helps me move fast; you do not need Cursor to use the CLIs.

Rough order: fix names and genres → optional stem factory → quit Rekordbox/Traktor when xml/NML writes → daily crate pass → reload rekordbox xml with `<>` (not “import collection”).

Reports land under `~/local_tools/crate/reports/`. Stem runs log under `stems/log/`. Dry-run is the default almost everywhere. Read each repo’s README — the good stuff is in `docs/crate.md` on **ix**.

**Licenses:** **Apache-2.0** for ix, stems, blackhole, music_migration, ix_bangers. **GPL** for grid and stage so GPL grid/Blender code never lands inside the Apache tree.

---

## Where it’s headed

Right now it’s terminal-heavy and agent-friendly because that’s how I ship while employed elsewhere. The direction is normal **open-source DJ organization tools** — clearer UI, safer defaults, docs your mate can follow — with the same rule: **your files, your paths, your decks**.

AI is a shortcut for building it, not the product. The product is a library that still works on Saturday.

---

## Mirrored repos

| Here | Source on ixamal |
| --- | --- |
| [ix](https://github.com/alkalurop/ix) | [ixamal/ix](https://github.com/ixamal/ix) |
| [stems](https://github.com/alkalurop/stems) | [ixamal/stems](https://github.com/ixamal/stems) |
| [music_migration](https://github.com/alkalurop/music_migration) | [ixamal/music_migration](https://github.com/ixamal/music_migration) |
| [blackhole](https://github.com/alkalurop/blackhole) | [ixamal/blackhole](https://github.com/ixamal/blackhole) |
| [ix_bangers](https://github.com/alkalurop/ix_bangers) | [ixamal/ix_bangers](https://github.com/ixamal/ix_bangers) |
| [grid](https://github.com/alkalurop/grid) | [ixamal/grid](https://github.com/ixamal/grid) |
| [stage](https://github.com/alkalurop/stage) | [ixamal/stage](https://github.com/ixamal/stage) |

Last full mirror: **2026-10-15**. SHAs: [ixamal/ix `docs/notes.md`](https://github.com/ixamal/ix/blob/main/docs/notes.md) (Alkalurop bridge section).
