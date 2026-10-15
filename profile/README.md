# Alkalurops

Open-source DJ library tooling — names, folders, playlists, stems, and the boring glue between Apple Music, Traktor, and Rekordbox.

That is what you see in **git today** (the repos below). The wider company is **live visuals that follow the set** — built on the laptop next to the booth, open **Apache** core in git, product layers later. Details stay in private strategy notes for now; public copy stays high level.

[alkalurops.org](https://www.alkalurops.org)

### Where we’re headed (public summary)

**Market & competition (internal analysis).** Most working DJs still live in a narrow band: loop libraries and clip mixers, shader toys that cap out fast, or pro tools that need a VJ salary. Festival-grade 3D rigs exist, but not for a solo act on one machine. The bet is generative picture that listens to the performance — without shipping pixels to the cloud.

**Platform story (internal narrative).** One pipeline from booth audio data to stage-safe visuals: local inference, real-time 3D compositing, loopback-only control. Open source for the community; simpler packaged tools for people who will not live in a terminal; optional venue-scale offerings later. The machine assists; it does not headline.

**Business & sequencing (internal roadmap).** What ships free in git, what becomes an app, what stays services — and in what order — lives in a separate working doc. GitHub shows the crate foundation first because a visual bus is useless if the library lies about paths and names.

**Two GitHub homes, same code repos:**

- **[ixamal](https://github.com/ixamal)** — where I commit. Issues and milestones live here.
- **alkalurop (this org)** — public mirror, refreshed around the **15th** each month.

No audio in git. Scripts, docs, and how a real crate got fixed.

---

## Pick what you need (shipping now)

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

## Why the crate repos exist

I DJ. Day job. Family. The library still grew — wrong tags, duplicate rows, USB crates, three apps arguing about paths. The git stack sorts **stems vs tracks**, fixes **genres and playlists**, and runs **stem batches** when names are true. It feeds the visual platform (clean metadata → OSC → stage) and stays **Apache** so others can use it without a locker in the cloud.

---

## How it works today

**Python + shell on your Mac.** **CRATER** / **BABYLON** for hygiene, optional stem budgets, deck sync. Reports: `~/local_tools/crate/reports/`. Details: [ixamal/ix `docs/crate.md`](https://github.com/ixamal/ix/blob/main/docs/crate.md).

The visual stack is in motion in **ix**; not a shrink-wrapped product yet.

**Licenses:** **Apache-2.0** — ix, stems, blackhole, music_migration, ix_bangers. **GPL** — grid, stage.

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

Last mirror: **2026-10-15** — SHAs in [ixamal/ix `docs/notes.md`](https://github.com/ixamal/ix/blob/main/docs/notes.md).
