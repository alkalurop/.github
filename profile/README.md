# Alkalurops

Open-source DJ library tooling — names, folders, playlists, stems, and the boring glue between Apple Music, Traktor, and Rekordbox.

**Git today** is the repo list below. **Alkalurops** is also live visuals that track the set — laptop-local, Apache core in the open, product layers when they are ready. Strategy detail stays private; this page stays overview only.

[alkalurops.org](https://www.alkalurops.org)

## Marketplace

There are current workflows in performance with Resolume, Synesthesia, TouchDesigner, and custom Unreal rigs which each solve real problems. 

We are building another lane with **generative picture that follows the performance**. Rendered in realtime on the machine in the booth, without sending frames to the cloud or rendering offline. Market notes also cover **IoT and ARKit** — face and body cues from the performer and audience participation through smartphone devices, small stage devices, fused with deck data are all incrementally being evaluated to deliver next generation live performances. So visuals can react to the artist performing, not only to a waveform. First proofs run on **my own DJ setup** before we claim venue scale.

## Platform

Audio and control data leave the decks on the local network. Visuals stay stage-safe in 3D. Inference stays local. The open repo is Apache. A simpler app can sit on top for people who do not want a terminal. Venues can go bigger later. The tools supports the performance and are not the headliner.

## Roadmap

Git ships music library organization, stems, crates, and remix decks first. Paths and names have to be true before OSC moves forward with Unreal, ComfyUI, and other DCC delivery mechanisms as proof of concept.

## Two GitHub homes

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

I DJ. I have a day job and a family. The library grew anyway.

Wrong tags. Duplicate rows. USB crates. Three apps that disagree on the path.

The git stack separates **stems from tracks**, fixes **genres and playlists**, and runs **stem batches** when the names are right. That metadata feeds the visual bus later. The code stays **Apache** so the crate stays yours, not a cloud locker.

---

## How it works today

**Python and shell on your Mac.** **CRATER** and **BABYLON** handle hygiene, optional stem budgets, and deck sync.

Reports: `~/local_tools/crate/reports/`. How-to: [ixamal/ix `docs/crate.md`](https://github.com/ixamal/ix/blob/main/docs/crate.md).

Visual work is active in **ix**. It is not a shrink-wrapped app yet.

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
