# GTM Launch Plan, StreamLine (B2C)

| Field | Value |
|---|---|
| Feature | Spotlight Curated Rail - Hand-picked homepage rail that bypasses the algorithm |
| Goal | Conversion |
| Launch tier | S, Minimal |

## Goal & Audience
- **Goal:** Conversion, It's the only goal that matches what we already committed to measuring. My experiment brief's primary metric is browse-to-play conversion, with a guardrail on diversity. The rail's entire job is to move one business metric , a user who opened the app presses play , without the detour through 15,000 titles
- **Target audience:** Primary: the long-tenured, high-frequency subscriber who opens the app by default, not by decision: the persona, operationalized as the rail-eligible segment: existing users (excludes new-user onboarding cohort, which is explicitly out of scope per PRD), who  opens ≥3x/week, active ≥6 months, who are not in the 10% experiment holdout.

## Launch Tier
- **S, Minimal**, This touches existing users only, inside a product they already open by default. There's no one to reach who doesn't already have the app open. The rail simply appears in position 1 on their next session.

Revenue impact. The target is a +2pt browse-to-play shift inside one segment, at MDE/sample sizes built for a 14-day read, not a quarter-moving launch. This is upstream of revenue (it feeds retention, not a direct monetization event), unproven (it's still in experiment phase against a holdout), and small by design. We are not launching a priced feature, a tier change, but just testing whether a homescreen change moves a conversion funnel. Nothing here justifies press, events, or even a dedicated comms push.

Risk: A long-tenured subscriber who's used the same algorithmic home screen for years could react to an unannounced layout change with confusion or a sense that "something's different and I wasn't told." That's a real cost for exactly the loyal, long-tenured segment we are trying to protect. But the fix for that risk is in-product, not GTM. A one-line "Spotlight" header and subtitle functions as the entire announcement this feature needs.

## Channels
1. **Owned: The in-product surface itself. This is the primary and arguably only channel that matters. The rail's own header ("Spotlight") and one-line subtitle, already specified in the Screen 1 build, is the announcement**
2. **Owned: Release notes / changelog.  Low-cost, low-noise, and matches the size. A one- or two-line changelog entry**
3. **Owned: Support / Help Center article. Some fraction of a long-tenured base will notice an unfamiliar row and do what long-tenured users do: contact support or search Help before assuming it's fine**

## Enablement & Assets
Sales: Not applicable. 
CS / Support, what they need:

- What it is and why, in one paragraph, without jargon. CS needs to answer "why am I seeing this new row?" without parroting "browse-to-play conversion." Plain version: "Spotlight is a small, hand-picked row of 10 titles chosen by our editors, so you don't have to scroll the whole catalog to find something to watch."
- Why some users see it and others don't. Because of the 10% holdout, support will get "my friend has Spotlight and I don't" tickets. CS needs a sanctioned, honest answer  (something like "we're rolling this out gradually and you'll see it soon" ), not an admission that the user is in a control group, which undermines the experiment's blindness if it leaks back to users comparing notes.

Assets to build:

- Internal one-pager for CS/Support
- Help Center / KB article
- Release notes entry

## Ownership, Budget & Timeline
- **Ownership & budget:** Eng Lead - Feature itself
Content Manager - Editorial title list
Data Analyst - Experiment analytics
PM - Release notes
Support Content manager - Help Center Article
CS Lead - Support One Pager

Budget note: everything above is $0 in media spend, consistent with S sizing. The only real budget risk is the editorial list row
- **Timeline:** Phase 1 — Beta (pilot, weeks 1–3, matches sprint + 14-day experiment window)
- Week 1: Rail ships behind the flag to 90% / 10% holdout split. Editorial list is live. CS one-pager and KB article are published before rail goes live, not after 
- Weeks 1–3: Dashboard runs live, checks guardrail (diversity) and primary metric (browse-to-play) at a minimum weekly, not just at day 14 
- End of week 3 : Read the experiment against the shipping criteria  (ship / hold-and-iterate / kill). This is a decision gate, not a milestone

Phase 2 — Launch moment (only if Phase 1 result is "ship")
- Flag moves from 90/10 to 100%. Reconsider whether S still holds or whether a release-note promotion / in-app "New" tag (M-leaning) is now warranted. 
- PM updates release notes from "New: Spotlight" to a permanent-feature framing
- CS lead confirms the one-pager's "gradual rollout" answer is retired, since the holdout no longer exists

Phase 3 — Post-launch (ongoing)

- Content manager owns the refresh cadence set in Phase 1 for the editorial content
- Data analyst moves from weekly pilot checks to a standing guardrail watch
- Mo. 0→1 retention. Gets its first real read here, once a full cohort has matured.

## Success Metrics
- **Metrics:** 1. Browse-to-play conversion (rail arm vs. holdout), ≥ +2pts absolute, p < 0.05 at full power
2. Title Detail Page→Start Playing rate, rail-originated sessions vs. non-rail sessions
3. Time-to-play (home-open to play-start), median, rail arm vs. control
- **Bad signal to watch for:** Browse-to-play conversion hits target while catalog-wide browse diversity drops beyond 5% relative to control
- **Likely post-launch decision:** Hold and iterate: ship to 100% only if diversity holds inside the 5% band . Most likely outcome is conversion hits target while diversity sits near that line, forcing the call rather than settling it.
