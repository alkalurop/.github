# Alkalurops

**For DJs:** one open-source stack to keep a huge library *playable* — same song in Apple Music, Traktor, and Rekordbox; stems beside the mix when you want four-deck sets; playlists and genres that stay sorted while life stays full.

[alkalurops.org](https://www.alkalurops.org) · Monthly mirror of [ixamal](https://github.com/ixamal) — day-to-day commits land on **ixamal**; this org is the **public snapshot** (refreshed around the **15th** each month via `alkalurop-bridge` on the Mac).

---

## What this can do for you

| You want… | Start here |
| --- | --- |
| Names and folders that match what you actually play | [ix](https://github.com/alkalurop/ix) — crate toolkit, **CRATER** / **BABYLON**, Music.app hygiene |
| Vocal + instrumental + Traktor `.stem.m4a` on your machine, not in the cloud | [stems](https://github.com/alkalurop/stems) — local STEM factory |
| Decks still find tracks after you moved drives or folders | [music_migration](https://github.com/alkalurop/music_migration) — NML + rekordbox xml remaps |
| Maschine + Traktor + Rekordbox on one Mac without routing roulette | [blackhole](https://github.com/alkalurop/blackhole) — rig runbook |
| Explore and plan sets before anything writes your DB | [ix_bangers](https://github.com/alkalurop/ix_bangers) — Bangers catalog (dry-run first) |
| Beatgrids on a whole playlist, written back to rekordbox / Traktor | [grid](https://github.com/alkalurop/grid) — GPL beatgrid tools |
| Visual / stage assets beside the booth | [stage](https://github.com/alkalurop/stage) — Blender tools (GPL) |

Nothing here ships your audio. Git holds **scripts, docs, and tooling** — your library stays on your SSD.

---

## Why this exists

I collect like a vinyl brain and DJ like the crate has to survive a Saturday night. Somewhere between a day job, family, and actually sleeping, tens of thousands of files turned into **Track 01**, **EDM, House**, USB crates that vanish when you unplug, and three apps that disagree on the path.

I built Alkalurops to **organize like a madman on a schedule**: separate **stems** from **tracks**, file by **artist / album / title**, sync **genres and playlists** across Apple Music, Traktor, and Rekordbox, and batch **STEM** work when the names are finally true — without renting someone else’s cloud locker. The goal is something **cool and reusable**: open docs and code other DJs and builders can fork, not a black-box SaaS.

**ixamal** is where the work happens. **Alkalurop** is the org-facing mirror so the story and the repos stay readable in one place.

---

## How to use it (technical)

**Today** the stack is built for **local, loopback-only** operation: Python CLIs, shell macros (`BABYLON`, `CRATER`, STEMIT budgets), Cursor as orchestrator, optional Tk progress HUD, mail on long runs. Typical flow:

1. **Identity & hygiene** — `ix` `crate/` (`music-repair`, `music-genre`, `music-organize`, …).
2. **Optional stems** — `stems` `py.exec.separate` or `ix` `stemit-chain` with a genre budget.
3. **Decks honest** — quit Rekordbox/Traktor when xml/NML writes; reload rekordbox xml (`<>`).
4. **Daily pass** — **CRATER** / **BABYLON** (MiK playlists, GENRES, samples, remix crates).

Clone from this org or from [ixamal](https://github.com/ixamal) (same names). Mac path in docs: `~/github/ixamal/…`. Read each repo’s README — first paragraph is DJ-facing; below that is operator detail.

**Licenses:** most DJ crate tooling is **[Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0)** (`ix`, `stems`, `blackhole`, `music_migration`, `ix_bangers`). **grid** and **stage** stay **GPL-3.0-or-later** so GPL beatgrid/Blender lineage never infects the Apache tree.

---

## Where it’s going

**Now:** agent-assisted and CLI — fast iteration, verbose logs, reports under `~/local_tools/crate/reports/`, RunLogger JSON under `stems/log/`. That’s the factory floor.

**Next:** the same pipelines as **proper open-source DJ organization products** — clearer GUIs, safer defaults, plugin-shaped boundaries (crate / stems / migration / rig), and docs a non-coder can follow without living in a terminal. Agentic AI stays a **bootstrap**, not the destination: the artifacts are **your library, your paths, your decks**, in formats you can audit and extend.

Floor visuals (Unreal / OSC) and performance routing stay wired through **ix** and **blackhole**; stem generation stays in **stems**; path surgery stays in **music_migration**. One crate, many repos, Apache-first core.

---

## Bridged repos (ixamal → alkalurop)

| Org copy | Source | Role |
| --- | --- | --- |
| [ix](https://github.com/alkalurop/ix) | [ixamal/ix](https://github.com/ixamal/ix) | Control plane — crate, CRATER, BABYLON, OSC / UE path |
| [stems](https://github.com/alkalurop/stems) | [ixamal/stems](https://github.com/ixamal/stems) | Local STEM factory |
| [music_migration](https://github.com/alkalurop/music_migration) | [ixamal/music_migration](https://github.com/ixamal/music_migration) | Post-move NML / xml remaps |
| [blackhole](https://github.com/alkalurop/blackhole) | [ixamal/blackhole](https://github.com/ixamal/blackhole) | Performance routing |
| [ix_bangers](https://github.com/alkalurop/ix_bangers) | [ixamal/ix_bangers](https://github.com/ixamal/ix_bangers) | Bangers MCP catalog |
| [grid](https://github.com/alkalurop/grid) | [ixamal/grid](https://github.com/ixamal/grid) | Playlist beatgrids (GPL) |
| [stage](https://github.com/alkalurop/stage) | [ixamal/stage](https://github.com/ixamal/stage) | Blender stage (GPL) |

**Last full mirror:** 2026-10-15 — see [ixamal/ix `docs/notes.md`](https://github.com/ixamal/ix/blob/main/docs/notes.md) (*Alkalurop org bridge*) for tip SHAs. Issues and milestones live on **ixamal** only; this org is **git mirror + profile**.
