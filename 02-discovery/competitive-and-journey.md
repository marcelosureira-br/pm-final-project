# Competitive Analysis & Journey Map (Module 2)

## Responses
- **Role, who are you solving for? (the specific user segment or profile):** A high-frequency, long-retention subscriber whose relationship with the platform is habitual — she opens the app by default rather than by decision.
- **Goal, what is this user ultimately trying to achieve?:** To open the app and be watching something worthwhile within a few minutes, without the selection itself becoming the evening's activity.
- **Friction, the main barrier (moment of misery) stopping them from succeeding:** She scrolls for twenty minutes across a 15,000-title catalog, closes the app without playing anything, and watches a DVD instead. The technical substrate under that moment is documented: descriptive search does not function (BUG-1080), leaving browse as the only path; the browse surface is degraded by placeholder thumbnails and a Continue Watching row occupied by finished titles (BUG-1104, BUG-1121); and on older hardware an 11-second cold start is charged before the twenty minutes even begins (BUG-1110). The focus-group aggregate confirms this is not idiosyncratic — half of participants described catalog scale as producing anxiety and a desire to be told what to watch. Her churn signal is silent. She has not complained, downgraded, or filed a ticket. Her tenure makes her look healthy in retention data right up until she leaves.
- **External tools, the outside platforms or tools the user is forced to use:** she ends up going back to a DVD after twenty minutes of scrolling.
- **The process, the 3 to 5 manual steps the user takes to get the job done:** Step 1 — Exhaust the in-app path. She opens the app, scrolls for roughly twenty minutes, and closes it without watching anything.

Step 2 — Abandon the platform entirely. She does not switch to a competitor's app or open YouTube (the pattern Raj describes in UXR-08). She goes back to a DVD

Step 3 — Watch something already vetted. A DVD in her possession is, by definition, something she already selected once and presumably liked enough to own. The "workaround" is not really solving tonight's discovery problem — it's opting out of discovery and re-consuming a known quantity.
- **Core frustration, the exact moment the process feels most “broken”:** The moment is when she closes the app without a rejection ever occurring
- **The evidence, a specific quote or behavior from the research that proves this:** UXR-01 · Priya, 34, heavy viewer (14 yrs)"I open the app, scroll for like twenty minutes, and close it without watching anything. There's 15,000 titles but nothing I actually want. I ended up going back to a DVD."
- **Your journey map, a shareable link, or the map file you committed (e.g. journey-map.html):** https://github.com/marcelosureira-br/pm-final-project/blob/main/02-discovery/Journey-map.png
