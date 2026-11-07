# PENSIEVE: Progress Tracker

Every step of building PENSIEVE, from an empty folder to the full vision in [VISION.md](VISION.md).

**Done:** ✅ done · 👉 doing now · ⬜ not started
**Learned:** ✅ I can explain it in my own words · ⬜ not yet

Only tick **Learned** when you could teach that step to a friend without looking.

---

## Stage 0: Setup · done 17/17 · learned 0/17

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ✅ | ⬜ | 0.1 | Idea & vision | Decided what PENSIEVE is: a Hogwarts castle home screen where every feature is a room. Written down in VISION.md so the plan survives. |
| ✅ | ⬜ | 0.2 | Choose Flutter | Cross-platform: one Dart codebase gives Android and iOS. Chosen over native Kotlin so the app isn't locked to one platform. |
| ✅ | ⬜ | 0.3 | GitHub repo + clone | The repo on GitHub is the online copy; `git clone` made the local copy in `E:\PENSIEVE`. Git tracks every change so nothing is ever lost. |
| ✅ | ⬜ | 0.4 | Install Flutter SDK | Downloaded and extracted the SDK to `E:\APK-STUFF\flutter`. The SDK has the Dart compiler, the Flutter framework and the `flutter` command. |
| ✅ | ⬜ | 0.5 | Add Flutter to PATH | PATH is the list of folders Windows searches for commands. Adding `flutter\bin` lets you type `flutter` in any terminal. |
| ✅ | ⬜ | 0.6 | `flutter doctor` + licenses | `doctor` checks every tool Flutter needs and shows ✓/✗. `--android-licenses` accepts the Android SDK licenses, which builds require. |
| ✅ | ⬜ | 0.7 | Fix the admin-lock hang | Running Flutter from an Administrator terminal made cache lock files admin-owned, so normal runs hung. Fixed the permissions. Lesson: never run Flutter as Administrator. |
| ✅ | ⬜ | 0.8 | Limit platforms | `flutter config` turned off web and Windows, so only Android + iOS are built and checked. |
| ✅ | ⬜ | 0.9 | `flutter create` | Generated the project. `--org com.redrighthand` + `--project-name pensieve` give the package ID `com.redrighthand.pensieve`, which is hard to change later. |
| ✅ | ⬜ | 0.10 | Project structure | `lib/` = your Dart code, `pubspec.yaml` = name, version and packages, `android/` & `ios/` = platform shells, `test/` = tests, `build/` = generated output (never edit). |
| ✅ | ⬜ | 0.11 | Android Studio setup | Installed the Flutter and Dart plugins and set the Flutter SDK path, so the IDE can run, debug and hot reload. |
| ✅ | ⬜ | 0.12 | NDK + CMake | The NDK builds native (C/C++) code that Flutter's engine and some packages need. Installed NDK 30 + CMake and set `ndkVersion` in `android/app/build.gradle.kts`. |
| ✅ | ⬜ | 0.13 | Phone over USB (ADB) | Turned on Developer options and USB debugging. ADB (Android Debug Bridge) is how the PC talks to the phone. Fixed "offline" by restarting ADB and re-authorizing USB. |
| ✅ | ⬜ | 0.14 | First run on the phone | The first build compiles everything with Gradle, so it is slow; later builds are fast. The counter demo app ran on the Samsung. |
| ✅ | ⬜ | 0.15 | Hot reload | Changed `seedColor` and the app updated in about a second without losing its state. This is Flutter's fastest feedback loop. |
| ✅ | ⬜ | 0.16 | First commit + push | `git add` stages changes, `git commit` saves a snapshot with a message, `git push` uploads it to GitHub. |
| ✅ | ⬜ | 0.17 | Progress tracker | This file: shows what is built and what you have actually learned. |

## Stage 1: Dart and Flutter basics · done 4/19 · learned 0/19

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ✅ | ⬜ | 1.1 | `main()` and `runApp()` | Every Dart program starts at `main()`. `runApp()` takes the root widget and draws it on screen. |
| ✅ | ⬜ | 1.2 | Widgets and the widget tree | In Flutter everything on screen is a widget, nested inside other widgets like a tree. `MyApp` is the root. |
| ✅ | ⬜ | 1.3 | `StatelessWidget`, `build()`, constructors | A stateless widget never changes by itself. `build()` returns what it looks like. Named parameters (`title: ...`), `required`, `const` and `super.key`. Exercise: title set to "Hogwarts". |
| ✅ | ⬜ | 1.4 | `MaterialApp` and `ThemeData` | `MaterialApp` sets up the app (title, theme, home screen). `ColorScheme.fromSeed` builds a whole colour palette from one colour. |
| 👉 | ⬜ | 1.5 | `StatefulWidget` and `State` | A widget that can change. The widget holds settings; its separate `State` object holds data that changes, like `_counter`. |
| ⬜ | ⬜ | 1.6 | `setState()` | Tells Flutter "data changed, run `build()` again". Without it the data changes but the screen does not. Exercise 2: House Points (+10 per tap, then remove `setState` and watch the screen freeze). |
| ⬜ | ⬜ | 1.7 | Hot reload vs hot restart | Reload injects new code and keeps state. Restart re-runs `main()` and resets state (House Points back to 0). |
| ⬜ | ⬜ | 1.8 | `Scaffold` and `AppBar` | `Scaffold` is the page skeleton: app bar, body, floating button, drawer, bottom bar. |
| ⬜ | ⬜ | 1.9 | Layout widgets | `Column` (vertical), `Row` (horizontal), `Center`, `Padding`, `SizedBox`, `Expanded`, `Stack`. How main/cross axis alignment works. |
| ⬜ | ⬜ | 1.10 | `Text`, `Icon`, `Image`, styling | Showing content and styling it with `TextStyle`, colours from the theme, and images from assets. |
| ⬜ | ⬜ | 1.11 | Buttons and taps | `ElevatedButton`, `IconButton`, `FloatingActionButton`, `InkWell`/`GestureDetector`. Callbacks: passing a function to run on tap. |
| ⬜ | ⬜ | 1.12 | Dart language basics | Variables, types, `var`/`final`/`const`, null safety (`?`, `!`, `??`), functions, lists, maps, loops, classes, enums. |
| ⬜ | ⬜ | 1.13 | Lists and grids | `ListView.builder` and `GridView.builder` build only the items on screen, so long lists stay fast. |
| ⬜ | ⬜ | 1.14 | Files, folders and imports | Split code out of `main.dart` into `lib/screens/`, `lib/widgets/` and so on, and `import` between them. |
| ⬜ | ⬜ | 1.15 | Navigation | Moving between screens with `Navigator.push` / `pop` and passing data to the next screen. |
| ⬜ | ⬜ | 1.16 | Packages and `pubspec.yaml` | `flutter pub add <name>` adds a package from pub.dev. `pubspec.lock` pins the exact versions. |
| ⬜ | ⬜ | 1.17 | Async: `Future`, `async`/`await`, `Stream` | How to wait for slow work (database, network) without freezing the UI. A `Stream` is a flow of values over time. |
| ⬜ | ⬜ | 1.18 | Debugging | Reading red error screens and stack traces, `debugPrint`, breakpoints, and Flutter DevTools. |
| ⬜ | ⬜ | 1.19 | Lints and formatting | `analysis_options.yaml` sets code rules; `dart format` keeps style consistent; `flutter analyze` finds problems. |

## Stage 2: v0.1 The Castle opens · done 0/25 · learned 0/25

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ⬜ | ⬜ | 2.1 | Folder architecture | Decide where code lives (e.g. `core/`, `data/`, `features/<room>/`) so the app can grow for years without becoming a mess. |
| ⬜ | ⬜ | 2.2 | App name, icon, splash | Show "PENSIEVE" under the icon, a custom launcher icon, and a splash screen. |
| ⬜ | ⬜ | 2.3 | `Room` model class | A Dart class describing a room (name, icon, screen). The castle is built from a list of these. |
| ⬜ | ⬜ | 2.4 | Castle home screen | A grid of room tiles, replacing the counter demo. Your first real screen. |
| ⬜ | ⬜ | 2.5 | Open a room | Tap a tile → navigate to that room. Unbuilt rooms show a "coming soon" placeholder. |
| ⬜ | ⬜ | 2.6 | Wizarding theme and fonts | Custom fonts and colours so it feels like Hogwarts. Assets declared in `pubspec.yaml`. |
| ⬜ | ⬜ | 2.7 | Sorting Hat quiz UI | Question screens with answer choices, one after another. |
| ⬜ | ⬜ | 2.8 | Sorting logic | Each answer adds points to houses; the highest total wins. A small scoring algorithm. |
| ⬜ | ⬜ | 2.9 | House themes | Four colour schemes (Gryffindor, Slytherin, Ravenclaw, Hufflepuff); the app theme switches to your house. |
| ⬜ | ⬜ | 2.10 | Remember the house | Save the house on the phone (`shared_preferences`) so the quiz only appears on first launch. |
| ⬜ | ⬜ | 2.11 | State management | Share app-wide data (house, theme) across screens with a state-management package (Provider or Riverpod) instead of passing it everywhere. |
| ⬜ | ⬜ | 2.12 | SQLite + Drift setup | SQLite is a database inside the app. Drift gives typed Dart access to it. `build_runner` generates code from your table definitions. |
| ⬜ | ⬜ | 2.13 | `memories` table | Schema design: `id`, `title`, `body`, `createdAt`, `updatedAt`. Primary keys, column types, NOT NULL. (DBMS) |
| ⬜ | ⬜ | 2.14 | Migrations | `schemaVersion` + migration steps, so changing tables later doesn't wipe users' data. |
| ⬜ | ⬜ | 2.15 | Data layer (DAO / repository) | One place for all memory queries (insert, update, delete, select). Screens never write SQL directly. |
| ⬜ | ⬜ | 2.16 | Pensieve list screen | Shows all memories, newest first. Uses a `Stream` so the list updates by itself when data changes. |
| ⬜ | ⬜ | 2.17 | Create a memory | A form with `TextField`s, `TextEditingController`s and validation (title can't be empty). |
| ⬜ | ⬜ | 2.18 | Edit a memory | Open a memory, change it, save; `updatedAt` changes. |
| ⬜ | ⬜ | 2.19 | Delete with undo | Confirm dialog, then a `SnackBar` with "Undo". |
| ⬜ | ⬜ | 2.20 | Tags tables | `tags` + `memory_tags` join table: a many-to-many relationship. (DBMS) |
| ⬜ | ⬜ | 2.21 | Tag chips + filter | Add tags to a memory as chips; tap a tag to see only those memories. |
| ⬜ | ⬜ | 2.22 | Full-text search (FTS5) | A special SQLite index for searching words inside text quickly, with ranking. |
| ⬜ | ⬜ | 2.23 | Search screen | Type to search, results update as you type (debouncing). The first version of the Room of Requirement. |
| ⬜ | ⬜ | 2.24 | Tests | Unit tests for logic (sorting, queries) and widget tests for screens. `flutter test`. |
| ⬜ | ⬜ | 2.25 | Release v0.1 | Bump `version` in `pubspec.yaml`, build a release APK, install it on the phone, `git tag v0.1`. |

## Stage 3: v0.2 History & Common Room · done 0/9 · learned 0/9

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ⬜ | ⬜ | 3.1 | `memory_versions` table | Every save also stores the old version, so nothing is ever truly overwritten. |
| ⬜ | ⬜ | 3.2 | Pensieve History timeline | A timeline of all memories and edits, newest first. |
| ⬜ | ⬜ | 3.3 | Compare and restore | See what changed between versions and restore an older one. |
| ⬜ | ⬜ | 3.4 | Links between memories | Typing `[[Other memory]]` creates a link. Parsing text with regular expressions. |
| ⬜ | ⬜ | 3.5 | Backlinks | Each memory shows which memories link to it. A graph stored in a `links` table. (DSA) |
| ⬜ | ⬜ | 3.6 | Journal table | `journal_entries`: date, mood, text. One entry per day. |
| ⬜ | ⬜ | 3.7 | Common Room screen | Write today's entry and pick a mood. |
| ⬜ | ⬜ | 3.8 | Life timeline / calendar | Browse past entries by date, coloured by mood. |
| ⬜ | ⬜ | 3.9 | Release v0.2 | Version bump, tests pass, release build, tag. |

## Stage 4: v0.3 Spellbook I · done 0/13 · learned 0/13

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ⬜ | ⬜ | 4.1 | Android permissions | Asking for the microphone and other permissions at runtime and handling "denied". (OS) |
| ⬜ | ⬜ | 4.2 | Voice input | On-device speech-to-text turns what you say into text. |
| ⬜ | ⬜ | 4.3 | Spell dispatcher | Maps spell words to actions ("lumos" → torch on). One place to register every spell. |
| ⬜ | ⬜ | 4.4 | Wand canvas | `CustomPaint` + gesture detection: draw with your finger and record the points. |
| ⬜ | ⬜ | 4.5 | $1 Unistroke Recognizer | Your own algorithm: resample the points, rotate, scale and move them, then compare against templates. (DSA, geometry) |
| ⬜ | ⬜ | 4.6 | Gesture templates | Record a shape for each spell and save it as a template. |
| ⬜ | ⬜ | 4.7 | *Lumos* / *Nox* | Torch on and off through a torch package. |
| ⬜ | ⬜ | 4.8 | *Accio* | Search for a memory and open it. |
| ⬜ | ⬜ | 4.9 | *Scribbly* | Quick-capture a new memory. |
| ⬜ | ⬜ | 4.10 | *Obliviate* / *Reparo* | Soft delete (move to trash, using a `deletedAt` column) and undo/restore. |
| ⬜ | ⬜ | 4.11 | More spells | *Revelio*, *Alohomora*, *Colloportus*, *Silencio* (Do Not Disturb needs a special permission), *Tempus*, *Expecto Patronum*. |
| ⬜ | ⬜ | 4.12 | Home-screen widget + quick-settings tile | Cast spells from outside the app. Needs a little native Kotlin and a platform channel between Dart and Kotlin. |
| ⬜ | ⬜ | 4.13 | Release v0.3 | Version bump, tests, release build, tag. |

## Stage 5: v0.4 Remembrall & Owlery · done 0/9 · learned 0/9

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ⬜ | ⬜ | 5.1 | Review fields | Add `ease`, `interval` and `dueDate` to memories (a migration). |
| ⬜ | ⬜ | 5.2 | SM-2 algorithm | Calculates when to show a memory next based on how well you remembered it. Unit-tested. (DSA) |
| ⬜ | ⬜ | 5.3 | Remembrall screen | Show due memories one by one; rate Again / Hard / Good / Easy. |
| ⬜ | ⬜ | 5.4 | Streaks | Count consecutive days of review. Date maths and time zones. |
| ⬜ | ⬜ | 5.5 | Local notifications | Schedule notifications on the phone; the Android 13+ notification permission. |
| ⬜ | ⬜ | 5.6 | Background work | Run tasks while the app is closed (e.g. check what's due). (OS) |
| ⬜ | ⬜ | 5.7 | Owlery inbox | A table + screen of all owls (updates), with read/unread. |
| ⬜ | ⬜ | 5.8 | Daily Prophet | Morning digest: due reviews, "on this day", habits and goals. |
| ⬜ | ⬜ | 5.9 | Release v0.4 | Version bump, tests, release build, tag. |

## Stage 6: v0.5 Owl Post & Time-Turner · done 0/5 · learned 0/5

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ⬜ | ⬜ | 6.1 | Letters table | Letters to your future self with an `unlockDate`. |
| ⬜ | ⬜ | 6.2 | Sealed letters | Locked until the date; an owl notification arrives when one unseals. |
| ⬜ | ⬜ | 6.3 | Time-Turner queries | Find memories from exactly 1 week, 1 month and 1 year ago. Date range queries. |
| ⬜ | ⬜ | 6.4 | Time-Turner screen | Shows those memories and lets you jump to them. |
| ⬜ | ⬜ | 6.5 | Release v0.5 | Version bump, tests, release build, tag. |

## Stage 7: v0.6 Sync · done 0/10 · learned 0/10

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ⬜ | ⬜ | 7.1 | Networking basics | HTTP, REST, JSON, status codes; calling an API from Dart. (CN) |
| ⬜ | ⬜ | 7.2 | Choose the backend | Your own API + PostgreSQL (more learning) or Supabase (faster). Decide here. |
| ⬜ | ⬜ | 7.3 | Server database + API | PostgreSQL schema mirroring the app's tables; endpoints to push and pull changes. |
| ⬜ | ⬜ | 7.4 | Accounts | Sign up and sign in; tokens kept in secure storage on the phone. (Security) |
| ⬜ | ⬜ | 7.5 | Sync-ready data | UUIDs instead of 1, 2, 3 ids, `updatedAt` everywhere, soft deletes. So two devices never clash on ids. |
| ⬜ | ⬜ | 7.6 | Offline queue | Changes made offline wait in a queue and are sent when the internet returns, with retries. |
| ⬜ | ⬜ | 7.7 | Pull changes | Fetch everything changed since the last sync and merge it into SQLite. |
| ⬜ | ⬜ | 7.8 | Conflict resolution | Same memory edited on two devices: last-write-wins first, CRDTs later. (Distributed systems) |
| ⬜ | ⬜ | 7.9 | Sync status UI | Online/offline indicator, "last synced", errors shown nicely. |
| ⬜ | ⬜ | 7.10 | Release v0.6 | Version bump, tests, release build, tag. |

## Stage 8: v0.7+ More rooms (any order) · done 0/14 · learned 0/14

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ⬜ | ⬜ | 8.1 | Media in memories | Attach photos and voice notes; files stored on the phone, paths in the database. |
| ⬜ | ⬜ | 8.2 | Library | Subjects, syllabus progress, and a code vault with syntax highlighting. |
| ⬜ | ⬜ | 8.3 | Classroom | Pomodoro timer and a GitHub-style activity heatmap. |
| ⬜ | ⬜ | 8.4 | Chocolate Frog Cards | `Q:: ... A:: ...` lines in memories become flashcards, collected like cards, reviewed with SM-2. |
| ⬜ | ⬜ | 8.5 | Gringotts | Expenses and savings tracker with monthly totals. |
| ⬜ | ⬜ | 8.6 | Potions Class | Habit tracker: each habit is an ingredient you add daily. |
| ⬜ | ⬜ | 8.7 | Divination | Goals, plans and the Dream Board. |
| ⬜ | ⬜ | 8.8 | Quidditch Pitch | Fitness and activity log. |
| ⬜ | ⬜ | 8.9 | Marauder's Map | Interactive graph of linked memories (graph layout algorithm); later, memories on a map by place. |
| ⬜ | ⬜ | 8.10 | House Points | XP for capturing, reviewing and habits; achievements. |
| ⬜ | ⬜ | 8.11 | Vault Lock | Biometric/PIN lock and private memories encrypted on the device. (Security) |
| ⬜ | ⬜ | 8.12 | End-to-end encryption | Synced data encrypted so even the server can't read it. (Crypto) |
| ⬜ | ⬜ | 8.13 | Export and backup | Export everything (JSON/Markdown) so the data is truly yours. |
| ⬜ | ⬜ | 8.14 | Ask the Pensieve | On-device embeddings for semantic search, then an AI chat over your own notes (RAG). (AI/ML) |

## Stage 9: Shipping & polish · done 0/6 · learned 0/6

| Done | Learned | # | Step | Explanation |
|:-:|:-:|---|---|---|
| ⬜ | ⬜ | 9.1 | CI with GitHub Actions | Every push runs `flutter analyze` and `flutter test` automatically. |
| ⬜ | ⬜ | 9.2 | App signing | A release keystore so Android trusts updates come from you. Keep it backed up and out of Git. |
| ⬜ | ⬜ | 9.3 | Play Store release | Store listing, screenshots, privacy policy, internal testing track. |
| ⬜ | ⬜ | 9.4 | iOS build | Needs a Mac (or a cloud Mac) and an Apple developer account. |
| ⬜ | ⬜ | 9.5 | Accessibility | Screen-reader labels, text scaling, colour contrast. |
| ⬜ | ⬜ | 9.6 | Performance | Profile with DevTools; fix slow builds of widgets and slow queries. |

---

## Lessons & fixes

| Problem | Fix / lesson |
|---|---|
| Flutter hung on every command | Lock files in `flutter\bin\cache` became admin-owned. Never run Flutter from an Administrator terminal. |
| ADB showed the phone as "offline" | Close phone mirroring, `adb kill-server`, revoke USB debugging authorizations, replug. |
| Android Studio broke after "Link Gradle project" | Never link the `android/` Gradle project in a Flutter project. Fixed by deleting `.idea` and reopening `E:\PENSIEVE`. |
| NDK 28 not offered | Installed NDK 30 and set `ndkVersion` in `android/app/build.gradle.kts`. |
