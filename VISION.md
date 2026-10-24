# PENSIEVE: Vision

> A wizarding home on your phone, holding everything you learn, remember and do.

PENSIEVE is a personal, offline-first Flutter app that I build and keep growing for as long as I like. Each feature is a **room in the castle**. The home screen is the castle, and you open a room to use its feature. New rooms can be added at any time.

It is also my learning project. Each room is chosen to use something from college: DBMS, DSA, networks, OS, security, software engineering and AI/ML.

---

## The Castle (home screen)

The home screen is a map of the castle that you can tap around. Each room is a tile or door with live info on it: today's streak, unread owls, the next sealed letter and so on.

A **Sorting Hat** quiz on first launch puts you in a house, which sets the theme colours: Gryffindor, Slytherin, Ravenclaw or Hufflepuff.

---

## Rooms (features)

### Remembering
| Room | What it is for |
|---|---|
| **The Pensieve** | The heart of the app. Capture "memories" (notes, snippets, links, photos, voice), tag them and link them with `[[other memory]]`. Includes a full **History**: a timeline of every memory and every edit to it. |
| **Remembrall** | Daily review that resurfaces old memories with spaced repetition (SM-2), plus streaks. |
| **Time-Turner** | "On this day": what you captured 1 week, 1 month or 1 year ago. |
| **Owl Post** | Letters to your future self, sealed until a date you choose. |

### Learning
| Room | What it is for |
|---|---|
| **Library** | Subjects and courses, syllabus progress, and a code vault with syntax highlighting. |
| **Classroom** | Study sessions with a Pomodoro timer and a GitHub-style activity heatmap. |
| **Chocolate Frog Cards** | Flashcards made from `Q:: ... A:: ...` lines inside memories, collected like cards. |

### Life
| Room | What it is for |
|---|---|
| **Common Room** | Journal with daily entries, mood and a life timeline. |
| **Gringotts** | Expense and savings tracker. |
| **Potions Class** | Habit tracker, with each habit as an ingredient you add daily. |
| **Divination** | Goals and plans, and the Dream Board for ideas and future projects. |
| **Quidditch Pitch** | Fitness and activity log. |

### Magic layer
| Feature | What it is for |
|---|---|
| **Owlery** (notifications) | All app updates arrive as owls: reminders, review due, a capsule unsealed, streak at risk. Also an in-app inbox. |
| **Daily Prophet** | Morning digest: today's review, an "on this day" memory, habits and goals. |
| **Spellbook** | Cast spells by **voice** or by **drawing a wand gesture** on screen. See below. |
| **House Points** | Gamification: XP for capturing, reviewing and keeping habits, with achievements. |
| **Marauder's Map** | Interactive graph of linked memories. A later version can also map memories to the places they happened. |
| **Room of Requirement** | Universal search, and later "Ask the Pensieve", an AI chat over your own notes. |
| **Gringotts Vault Lock** | Biometric or PIN lock, plus private encrypted memories. |

---

## Spellbook (first set)

| Spell | Action |
|---|---|
| *Lumos* / *Nox* | Torch on / off |
| *Accio* `<thing>` | Search and open a memory |
| *Scribbly* | Quick-capture a new memory |
| *Revelio* | Show hidden or private memories (after unlock) |
| *Alohomora* | Unlock the vault |
| *Colloportus* | Lock the app immediately |
| *Obliviate* | Delete a memory (it goes to trash, so it can be restored) |
| *Reparo* | Undo the last action, or restore from trash |
| *Silencio* | Turn on Do Not Disturb |
| *Tempus* | Show the time and today's summary |
| *Expecto Patronum* | Open your "happy memories" collection |

Spells work **inside the app**, from a **home-screen widget** and from a **quick-settings tile**. Android does not let apps listen for gestures across the whole phone, so spells can't be cast from other apps.

Wand gestures are recognised with the **$1 Unistroke Recognizer**, a small geometry and DSA algorithm I implement myself. Voice spells use on-device speech-to-text.

---

## Tech stack
- **App:** Flutter (Dart), targeting Android first, then Windows desktop and web.
- **Local DB:** SQLite through Drift, with full-text search (FTS5) and migrations.
- **Sync:** offline-first. The backend is not decided yet: either my own (API plus PostgreSQL) or Supabase.
- **Later:** end-to-end encryption, on-device embeddings for semantic search.

## College subjects → where they show up
| Subject | In PENSIEVE |
|---|---|
| DBMS | Schema design, indexes, FTS, migrations, edit history tables |
| DSA | Link graph, search ranking, SM-2, $1 gesture recognizer |
| Computer Networks | Sync API, retries, offline queue |
| Distributed Systems | Conflict resolution (last-write-wins, then CRDTs) |
| OS | Background jobs, notifications, file storage, permissions |
| Security | Auth, biometric lock, encryption |
| Software Engineering | Architecture, tests, CI, releases |
| AI/ML | Speech recognition, semantic search, Ask the Pensieve |

---

## Roadmap
Each version is small enough to finish. Rooms not listed yet come later, in any order.

- **v0.1, The Castle opens:** project setup, the castle home screen, the Sorting Hat theme, and **The Pensieve** (create, edit, delete, tag and search memories in SQLite).
- **v0.2, History & Common Room:** memory edit history and timeline, and the journal with mood.
- **v0.3, Spellbook I:** voice and wand-gesture spells (Lumos, Nox, Accio, Scribbly, Obliviate, Reparo).
- **v0.4, Remembrall & Owlery:** spaced-repetition review, streaks, notifications and the inbox.
- **v0.5, Owl Post & Time-Turner:** sealed letters and "on this day".
- **v0.6, Sync:** choose the backend, add accounts and offline-first sync.
- **v0.7+, more rooms:** Library, Classroom, Gringotts, Potions, Divination, Quidditch, Marauder's Map, House Points, Vault Lock, Ask the Pensieve…
