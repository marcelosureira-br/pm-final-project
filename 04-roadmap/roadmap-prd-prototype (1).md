# Roadmap, PRD & Prototype (Module 4)

## Your strategic anchors
- **Persona (M2), who are you solving for?:** A high-frequency, long-tenured subscriber who opens the app by default, not by decision., wants to Be watching something worthwhile within minutes — without the search becoming the evening., blocked by Scrolls 15,000 titles for 20 minutes, closes the app, and reaches for a DVD instead..
- **Primary success metric (M3), your leading indicator:** If it works, that should show up as improved browse-to-play conversion and a smaller Mo. 0→1 retention drop
- **Moment of misery (M2), the specific friction blocking the goal:** She scrolls for twenty minutes across a 15,000-title catalog, closes the app without playing anything, and watches a DVD instead. The technical substrate under that moment is documented: descriptive search does not function (BUG-1080), leaving browse as the only path; the browse surface is degraded by placeholder thumbnails and a Continue Watching row occupied by finished titles (BUG-1104, BUG-1121); and on older hardware an 11-second cold start is charged before the twenty minutes even begins (BUG-1110). Her churn signal is silent. She has not complained, downgraded, or filed a ticket. Her tenure makes her look healthy in retention data right up until she leaves.
- **Guardrail metric (M3), what must not drop or break:** Catalog-wide browse diversity and amount of onboarding users.

## Scan the backlog & set a human baseline
- **My instinctive “quick wins” before touching the AI (2 to 3 feature IDs + why):** A1, since it touches the biggest reported problem and it doesn't require very engineering effort.
A2, because it facilitates easily the choice of users
A7, following the same idea of A1. Recommendations based on some authority.

## Audit, override & decide
- **Where did you override the AI? (feature + old vs. new score + why):** A7 - Curator Profiles. Old Score was 2-3 Time Sinker. I believe it could be a 4-2. It brings values adding new recommendations based on curators authority with low effort from tech team (basically playlists)
- **Did the AI over-value a Sales/Eng request your M2 interviews don’t support?:** No. AI considered the Sales requests comparing with moment of misery and considered them as time sinker. For instance, A8, A10.
- **Did it underweight something your M3 cohort/funnel data strongly supports?:** Yes. I believe A7

## Generate your interactive roadmap
- **My “Now” lane (this sprint), the 2 to 3 quick wins I’ll build first:** A1 Spotlight Curated Rail, A7Curator Profiles
- **What I cut, and the “no” I’m protecting the scope from:** A2, A4, A8, A9, A10. Cutting things not related to the moment of misery and metrics
- **Prototype/roadmap screenshot link (paste into your deliverables):** https://github.com/marcelosureira-br/pm-final-project/blob/main/04-roadmap/roadmap.png
