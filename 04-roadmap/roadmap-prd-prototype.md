# Feature Roadmap, Module 4 · StreamLine Spotlight

**Team:** 2 engineers + 1 designer

## Strategic anchors
- **Persona:** A high-frequency, long-tenured subscriber who opens the app by default, not by decision., wants to Be watching something worthwhile within minutes — without the search becoming the evening., blocked by Scrolls 15,000 titles for 20 minutes, closes the app, and reaches for a DVD instead..
- **Primary metric:** If it works, that should show up as improved browse-to-play conversion and a smaller Mo. 0→1 retention drop
- **Moment of misery:** She scrolls for twenty minutes across a 15,000-title catalog, closes the app without playing anything, and watches a DVD instead. The technical substrate under that moment is documented: descriptive search does not function (BUG-1080), leaving browse as the only path; the browse surface is degraded by placeholder thumbnails and a Continue Watching row occupied by finished titles (BUG-1104, BUG-1121); and on older hardware an 11-second cold start is charged before the twenty minutes even begins (BUG-1110). Her churn signal is silent. She has not complained, downgraded, or filed a ticket. Her tenure makes her look healthy in retention data right up until she leaves.
- **Guardrail:** Catalog-wide browse diversity and amount of onboarding users.

## Scoring
| Feature | Value | Effort | Quadrant | Decision | Rationale |
|---|---|---|---|---|---|
| A1 Spotlight Curated Rail | 4 | 1 | Quick Win | Now | It hands her a finished shortlist at the top of the screen, which attacks the 20-minute scroll directly and needs no algorithm work, though it is one-size-fits-all and could concentrate plays, so watch the diversity guardrail. |
| A2 'Why You'll Love This' Label | 3 | 3 | Time Sinker | Cut | It reduces doubt about a title she has already stopped on, but her friction is never reaching a candidate, and hover-based UI barely exists on TV and mobile. |
| A3 Hidden Gem Badge | 2 | 1 | Fill-In | Later | It's cheap and helps the diversity guardrail, but low viewcount says nothing about her taste, so it adds one more thing to evaluate while she scrolls. |
| A4 Mood-Based Entry Point | 2 | 3 | Time Sinker | Cut | She opens the app by default, not by decision, so a forced mood pick adds a step before play, and tagging 15,000 titles by mood is a heavy metadata job. |
| A5 Personalized Spotlight Queue | 5 | 4 | Major Project | Next | Years of tenure give the richest taste signal in the base, and a per-person shortlist is the most direct lever on browse-to-play and the Mo 0→1 drop; it must ship with a diversity floor. |
| A6 Spotlight Digest Email | 2 | 2 | Fill-In | Later | It acts outside the moment of misery, since she is already in the app when she fails, and it does nothing for browse-to-play. |
| A7 Curator Profiles | 4 | 2 | Quick Win | Now |  It brings values adding new recommendations based on curators authority with low effort from tech team (basically playlists) |
| A8 Watch Party (Spotlight) | 1 | 5 | Time Sinker | Cut | It is a Sales request that solves group viewing, not her solo 20-minute search, at the highest engineering cost on the list. |
| A9 Advanced Filter Engine | 3 | 3 | Time Sinker | Cut | Runtime and decade filters offer a partial workaround for the broken descriptive search (BUG-1080), but they still make her do the searching, so fixing search itself is the better spend. |
| A10 Offline Download (Spotlight) | 1 | 5 | Time Sinker | Cut | It is a Sales request that does nothing about finding something to watch, which is her actual problem. |

## Roadmap
### NOW, 3-week sprint
- **A1 Spotlight Curated Rail**, It hands her a finished shortlist at the top of the screen, which attacks the 20-minute scroll directly and needs no algorithm work, though it is one-size-fits-all and could concentrate plays, so watch the diversity guardrail.
- **A7 Curator Profiles**, It brings values adding new recommendations based on curators authority with low effort from tech team (basically playlists)

### NEXT, following 1-2 sprints
- **A5 Personalized Spotlight Queue**, Years of tenure give the richest taste signal in the base, and a per-person shortlist is the most direct lever on browse-to-play and the Mo 0→1 drop; it must ship with a diversity floor.

### LATER, backlog
- **A3 Hidden Gem Badge**, It's cheap and helps the diversity guardrail, but low viewcount says nothing about her taste, so it adds one more thing to evaluate while she scrolls.
- **A6 Spotlight Digest Email**, It acts outside the moment of misery, since she is already in the app when she fails, and it does nothing for browse-to-play.

### ✂ Cut List
- **A2 'Why You'll Love This' Label**, It reduces doubt about a title she has already stopped on, but her friction is never reaching a candidate, and hover-based UI barely exists on TV and mobile.
- **A4 Mood-Based Entry Point**, She opens the app by default, not by decision, so a forced mood pick adds a step before play, and tagging 15,000 titles by mood is a heavy metadata job.
- **A8 Watch Party (Spotlight)**, It is a Sales request that solves group viewing, not her solo 20-minute search, at the highest engineering cost on the list.
- **A9 Advanced Filter Engine**, Runtime and decade filters offer a partial workaround for the broken descriptive search (BUG-1080), but they still make her do the searching, so fixing search itself is the better spend.
- **A10 Offline Download (Spotlight)**, It is a Sales request that does nothing about finding something to watch, which is her actual problem.
