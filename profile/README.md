# Alkalurops

Open-source DJ library tooling — names, folders, playlists, stems, and the boring glue between Apple Music, Traktor, and Rekordbox.

**Git today** is the repo list below — the crate, the stems factory, migration helpers, and the scripts that keep a real library concise, robust and cross platform. **Alkalurops** is the name for the wider idea: live visuals that track the set while you play, built on the laptop next to the booth, with an **Apache** core in the open and product layers when they are ready. Deeper strategy stays in private notes; this page is the story at a glance.

[alkalurops.org](https://www.alkalurops.org)

## Marketplace

Most working acts already know how they want to look. **Resolume** carries loops and clips through a mature mixer. **Synesthesia** and **TouchDesigner** give you shader depth when you want to author pixels by hand. **Custom Unreal rigs** show up when the room is big enough to justify a real-time 3D pipeline. Those workflows earned their place; we borrow from them and plug into them where it makes sense.

What we are adding is another lane: **generative picture that follows the performance** as it happens. The picture is rendered in real time on the machine in the booth, so you are not uploading frames to someone else’s cloud and you are not waiting on an offline render farm between songs. The goal is a show that breathes with the mix — energy, tension, release — without turning the DJ booth into a render queue.

The same story extends to **IoT and ARKit**. We are interested in face and body cues from the performer on the mic, in audience participation through phones in the room, and in small stage devices that can speak the same local language as the decks. Fused with BPM, fader, and phrase data from **Rekordbox** or **Traktor**, that gives visuals something richer than a waveform alone: they can respond to the human holding the set, not only to the analyzer. We are evaluating those pieces incrementally, in private market notes, because each venue and each act wires the room differently. The first honest proofs run on **my own DJ setup** — same crates, same routing surprises, same late-night fixes — before we claim anything about festival scale.

## Platform

The platform story is a straight line from booth to picture. Audio and control data leave the decks on the **local network** (loopback-first, stage-safe). Visuals are composed in real-time **3D** so they can sit behind or beside the performer without fighting the room. **Inference stays local** on the Mac you already brought to the gig. The open repository stays **Apache** so the community can fork the bus without a locker in the cloud; a simpler app can sit on top for people who do not want to live in a terminal. Venues can grow into bigger installs later — more outputs, more machines — but the default is one artist, one laptop, one truth about what track is playing. The tools are there to support the performance. They are not the headliner.

## Roadmap

Sequencing matters because a visual bus is useless if the library lies. **Git ships the foundation first**: music library organization, stems, crates, and remix decks — the boring work that makes paths and names agree across **Apple Music**, **Traktor**, and **Rekordbox**. Only after that foundation holds do we push **OSC** forward into **Unreal**, **ComfyUI**, and other **DCC** delivery paths as proof of concept. What becomes a shrink-wrapped app, what stays a service, and what ships when — that ordering lives in private roadmap notes, not in a public promise date. What you see here is the crate today and the direction of travel tomorrow.

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

I DJ, I have a day job, and I have a family, and the library still grew on its own — wrong tags, duplicate rows, USB crates, three apps that disagree on the same path. The git stack exists because I needed something that separates **stems from tracks**, fixes **genres and playlists**, and runs **stem batches** once the names are true. That metadata is what will feed the visual bus later; you cannot scrub Niagara to the right record if Rekordbox and Traktor do not agree on what the record is. The code stays **Apache** so the crate stays yours, not a cloud locker someone else can switch off.

---

## How it works today

Everything that ships right now is **Python and shell on your Mac** — no installer, no account, no phone-home. You clone the repos you need, point them at your music tree, and run passes when the library drifts. That is intentional: the crate on disk is the source of truth, not a dashboard that might disagree with Rekordbox tomorrow.

**CRATER** is the daily hygiene pass — genres, playlists, capture folders, Traktor and Rekordbox alignment, and the quiet cleanup that keeps a growing library from turning into duplicate rows and broken paths. **BABYLON** is the heavier night run when you want hygiene plus an optional **STEMIT** budget (overnight stems) and a clean quit of the decks so the databases can sync without you clicking through save dialogs. Both write human-readable reports under `~/local_tools/crate/reports/` so you can see what moved, what was skipped, and what needs a reload in the app. Step-by-step commands and flags live in [ixamal/ix `docs/crate.md`](https://github.com/ixamal/ix/blob/main/docs/crate.md).

Parallel to the crate, visual work is already moving in **ix** — OSC from the decks, local runtime glue, and experiments that will eventually feed Unreal and the rest of the DCC path described above. None of that is a shrink-wrapped product yet; it is the same repo family, the same Apache ethic, and the same rule that control stays on **127.0.0.1** until you deliberately widen it.

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
