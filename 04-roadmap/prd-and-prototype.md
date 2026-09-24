# Spotlight Curated Rail - Hand-picked homepage rail that bypasses the algorithm, Simplified PRD (StreamLine)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** A high-frequency, long-tenured subscriber who opens the app by default, not by decision., wants to Be watching something worthwhile within minutes — without the search becoming the evening., blocked by Scrolls 15,000 titles for 20 minutes, closes the app, and reaches for a DVD instead..

## 1. The Big Picture
- **Vision:** Give the long-tenured subscriber who opens StreamLine by default a short, hand-picked shortlist at the top of the homepage, so she is watching something worthwhile within minutes and never reaches for a DVD.
- **Press release:** Today StreamLine introduces Spotlight, a rail of ten titles chosen by our editors and placed at the top of your homepage, before anything else. Every title has real artwork, none is something you have already finished, and each is one tap from playing. It is a short answer to a 15,000-title catalog.

For subscribers who have been with us for years and open the app without deciding what to watch, the evening used to be a 20-minute scroll that often ended with the app closed. Spotlight replaces that scroll with a shortlist that fits on one screen. If the shortlist can't meet that standard, it doesn't appear at all.
- **Success metric:** Browse-to-play conversion, rail group vs. 10% holdout
- **Guardrail:** Catalog-wide browse diversity: distinct titles played per active user per week

## 2. The Details
### User stories
- As a long-tenured subscriber who opens the app by default, I want a short hand-picked shortlist at the top of home, so that I'm watching something within minutes instead of scrolling 15,000 titles.
- As a subscriber who has finished titles, I want the rail never to offer something I've already watched, so that it doesn't feel like another Continue Watching row full of finished titles (BUG-1104).
- As the Spotlight editor, I want to change the 10 titles without a code release, and as PM I want plays tagged by cohort and long-tail status, so that I can prove the lift and catch concentration early.
### Screens to build
- Screen 1: Home (entry point)
- Top nav and the Spotlight rail in position 1 (header "Spotlight" plus a one-line subtitle)
- 10 cards, each with 16:9 artwork, title and runtime, in a horizontal scroll
- Below the rail: a Continue Watching row and two generic catalog rows (static, to show the rail sits above the 15,000-title sprawl)
- Prototype-only strip: holdout toggle, cohort toggle (tenured / new) and a "mark 6 titles watched" scenario button
- Screen 2: Title sheet (feature core)
- Large artwork, title, year, runtime, genre and an editor-written one-line synopsis
- Primary Play button, plus a back control to the rail
- Previous / next arrows that step through the 10 rail titles, so she can compare without returning to the scroll
- Screen 3: Now playing (success)
- Player placeholder with the title and a "Playing now" confirmation
- Time to play (home load to play start), shown on screen
- Back to home
- Collapsible session log showing the events fired and the long-tail share of plays
### Functional requirements
- The rail renders in position 1 or 2 and is fully visible without scrolling at 1280×720 and 390×844.
- The rail shows exactly 10 titles, read from one config array of 12 candidates (a hard cap of 10).
- A title with missing or placeholder artwork is excluded before render, so the rail shows 0 placeholder thumbnails (BUG-1121 guard).
- A title with watched=true is excluded before render, and if fewer than 5 eligible titles remain the rail is not rendered (BUG-1104 guard).
- Home load to playback takes at most 2 interactions: select a card, then press Play.
- The rail renders in the same pass as home, with 0 additional requests and 0 loading spinners, so it adds 0 ms to cold start (BUG-1110 guard).
- A flag with a holdout bucket controls the rail. Holdout users see no rail, and events fire for both groups.
- rail_impression, rail_click and play_start fire once each per action, tagged with cohort, long_tail and bucket. play_start also carries time_to_play.
### Smart behaviors (Situation → Outcome)
- Situation - Outcome
- Home loads with 5 or more eligible titles - Rail renders in position 1 with up to 10 cards
- Title has watched=true - Excluded before render
- Title has no artwork	 - Excluded before render and logged
- Fewer than 5 eligible titles - Rail is not rendered and home renders normally, with no empty state
- User in holdout bucket - No rail, standard rows only, events still logged with bucket=holdout
- Card selected - Title sheet opens and rail_click fires
- Play pressed - Screen 3 opens, play_start fires with long_tail, cohort and time_to_play
- Play pressed twice quickly - One play_start event only
- Title unavailable at play time - Inline "This title isn't available right now", returns to the rail, and the title is removed for the session
### Technical constraints
- No external APIs. Data is a hard-coded JSON constant with 12 seed titles: 1 watched, 1 with no artwork, and 1 long-tail-heavy mix so the gates are visible.
- No login and no real user accounts. Cohort and holdout are toggles.
- State uses useState only, with one screen state switching the 3 screens. No router, context, reducer or localStorage.
- No simulated 11-second cold start and no AI-generated text.

## 3. The Logistics
### Features out
- Personalization and algorithmic ranking (A5)
- "Why you'll love this" labels (A2) and mood filters (A4)
- Hidden Gem badges on the rail (A3)
- Search or filter changes (BUG-1080, A9)
- Root-cause fixes for BUG-1104, BUG-1121 and BUG-1110. They are dependencies, and the rail only guards against them.
- A new-user variant of the rail
- Watch Party, Offline Download and digest-email tie-ins
### Edge cases & safety guard
- Malformed, empty or duplicate config. The rail doesn't render, with no user-facing error, and home is unaffected. Duplicate IDs are deduped, keeping the first.
- All artwork missing. This is treated as fewer than 5 eligible titles, so the rail is hidden.
- New user with little history. The user sees the same rail, tagged cohort=new, so the onboarding guardrail can be read separately.
- Back from playback. Starting playback does not count as finished, so the title is not suppressed on return.
- Safety and hallucination guard. This feature generates nothing. Every rendered string, including synopses, is an editor-supplied config field. If a synopsis is missing, nothing is shown instead of generated text. The session log computes only from real events and shows no invented stats.
### Decision log
- Fixed 10 titles, no personalization. A5 has to beat A1 as its control. Adding any per-user ranking now would contaminate the baseline and hide whether personalization earns its cost.
- Guard against BUG-1104, BUG-1121 and BUG-1110 rather than fix them here. Fixing them inside this feature would push a 3-week sprint into a platform project. The rail hides itself instead of showing a degraded state.
### Evals
- Gate accuracy: 100%. Across 20 config permutations (watched, no artwork, duplicates, fewer than 5 eligible), 0 finished titles and 0 placeholder thumbnails render, and the rail hides in every under-5 case.
- Time-on-task. With 5 testers on a tenured profile, median home load to play start is ≤ 60 seconds (against her 20-minute scroll), and ≥ 90% of sessions need 2 or fewer interactions.
- Integrity and safety triggers. 0 rendered strings that don't trace to a config field, and 100% of events carry cohort, long_tail and bucket. Any miss blocks the pilot.

## MoSCoW scope
- **Must:** - Rail sits in position 1 or 2 on the homepage, visible without scrolling on every platform.; - Fixed list of about 10 hand-picked titles, set by editors and ranked by no algorithm.; - List is config-driven, so editors can change it without an app release; - Hard artwork gate: a title with a placeholder thumbnail (BUG-1121) cannot enter the rail.; - Suppress titles she has already finished, and hide the rail if fewer than 5 eligible titles remain; - One-action path to play from each card: play directly, or open a title page with Play as the primary button; - Rail loads with the home payload and adds no blocking call; - A named editor and a first list of about 10 titles ready by day 5
- **Should:** - Scheduled rotation with start and end dates per list.; - Auto-remove titles that become unavailable; - Editorial diversity floor; - Fallback to the last valid list if the config fails to load.
- **Could:** - Editable rail title and one-line subtitle; - Per-region or per-locale lists; - Preview or trailer on focus (must not touch cold start); - Curator attribution on the rail. This overlaps with A7, which is also in NOW, so coordinate the two.; - Simple editor UI in place of the config file; - Tenure-cohort list variants. This is a natural bridge into A5.
- **Won't (now):** Any personalization or algorithmic ranking. Per-user order belongs to A5.; "Why you'll love this" labels or mood filters. Both were cut (A2, A4), and both add a decision she doesn't want to make.; Hidden Gem badges on the rail. A3 is in LATER, and it adds one more thing to evaluate.; Search or filter changes. BUG-1080 and A9 are a separate workstream.; Root-cause fixes for BUG-1104, BUG-1121 and BUG-1110 inside this feature's scope. Track them as dependencies. The rail only guards against them, as the Must Haves above specify.; A new-user variant of the rail. Watch onboarding as a guardrail metric first, and build a separate variant only if the data says you need one.; Watch Party, Offline Download or digest email tie-ins. These are cut or parked.

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.
