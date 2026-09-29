# A/B Experiment Brief, StreamLine (B2C)

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | Spotlight Curated Rail - Hand-picked homepage rail that bypasses the algorithm |
| Persona | A high-frequency, long-tenured subscriber who opens the app by default, not by decision., wants to Be watching something worthwhile within minutes — without the search becoming the evening., blocked by Scrolls 15,000 titles for 20 minutes, closes the app, and reaches for a DVD instead.. |
| Expected outcome | We expect curated, mood-based discovery to shorten the path from app-open to play-start for this segment. |
| Primary success metric | If it works, that should show up as improved browse-to-play conversion and a smaller Mo. 0→1 retention drop |
| Baseline rate | In the conversion funnel, 71% of users reach Browse Titles, but only 29% reach Start Playing, meaning the majority of users who begin browsing never press play. The steepest single drop is between Title Detail Page (48%) and Start Playing (29%), a 19-point loss right at the moment of decision, which is exactly where the qualitative evidence places the friction: users reach titles, but can't commit to one. |
| Guardrail metric | Catalog-wide browse diversity and amount of onboarding users. |
| Guardrail boundary | Onboarding of new users should not drop more than 5%. |
| Second guardrail | · |
| Minimum Detectable Effect | +2% pts |
| Sample size per arm | 6.278 |
| Traffic split | 50/50 |
| Test duration | 14 days |
| Significance threshold | p < 0.05 (95% confidence), industry standard, no deviation. |

## Control vs. Variant
- **Control (A):** The current home screen: a set of algorithmic rows (“Recently played”, “Made for you”, “Popular”) with no editorial framing.  The steepest single drop is between Title Detail Page (48%) and Start Playing (29%), a 19-point loss right at the moment of decision, which is exactly where the qualitative evidence places the friction: users reach titles, but can't commit to one.
- **Variant (B):** Screen 1: Home (entry point)
Top nav and the Spotlight rail in position 1 (header "Spotlight" plus a one-line subtitle)
10 cards, each with 16:9 artwork, title and runtime, in a horizontal scroll
Below the rail: a Continue Watching row and two generic catalog rows (static, to show the rail sits above the 15,000-title sprawl)
- **Held constant (isolation check):** Recommendation engine logic, the algorithmic rows below the rail, notification settings, onboarding flow, playback engine, and app version are all identical between arms. The only difference an Explorer can perceive is the presence of the Spotlight rail.

## Hypothesis
> I believe that Spotlight Curated Rail - Hand-picked homepage rail that bypasses the algorithm for A high-frequency, long-tenured subscriber who opens the app by default, not by decision., wants to Be watching something worthwhile within minutes — without the search becoming the evening., blocked by Scrolls 15,000 titles for 20 minutes, closes the app, and reaches for a DVD instead.. will result in We expect curated, mood-based discovery to shorten the path from app-open to play-start for this segment., as measured by a +2% pts change in If it works, that should show up as improved browse-to-play conversion and a smaller Mo. 0→1 retention drop within 14 days. We will protect Catalog-wide browse diversity and amount of onboarding users. throughout the test.

## Shipping criteria
> We will **ship** if If it works, that should show up as improved browse-to-play conversion and a smaller Mo. 0→1 retention drop improves by ≥ +2% pts at p < 0.05 (95% confidence), industry standard, no deviation. and Catalog-wide browse diversity and amount of onboarding users. does not reach Onboarding of new users should not drop more than 5%. after 14 days.
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 14 days, no results reviewed before this date.
