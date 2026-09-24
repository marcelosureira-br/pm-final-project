# PRD & Prototype Sprint (Module 4)

## Pick & scope with MoSCoW
- **The “Now” feature I’m scoping (name + one-line core description):** Spotlight Curated Rail - Hand-picked homepage rail that bypasses the algorithm
- **My finalized Must-Haves (after overriding the AI):** - Rail sits in position 1 or 2 on the homepage, visible without scrolling on every platform.
- Fixed list of about 10 hand-picked titles, set by editors and ranked by no algorithm.
- List is config-driven, so editors can change it without an app release
- Hard artwork gate: a title with a placeholder thumbnail (BUG-1121) cannot enter the rail.
- Suppress titles she has already finished, and hide the rail if fewer than 5 eligible titles remain
- One-action path to play from each card: play directly, or open a title page with Play as the primary button
- Rail loads with the home payload and adds no blocking call
- A named editor and a first list of about 10 titles ready by day 5
- **What I demoted from Must → Should/Won’t, and why:** - Per-region or per-locale lists. Not needed for the MVP. We can start with general lists.

## Generate your Simplified PRD
- **One thing my PRD makes explicit that a vague brief would have missed:** A vague brief would say "add a curated rail at the top of home," and the team would build it and ship whatever the data gave them. That means placeholder thumbnails and titles she has already finished, sitting in the most prominent spot on the screen.

## Prompt-to-prototype sprint
- **Where did the prototype reveal a gap in my PRD logic? (what I had to update):** NA
- **My prototype, as a link or a screenshot (publish or share from your tool; in Lovable that is Share → Share Preview, in Bolt Publish → Web. No share URL? Screenshot the working flow):** https://spotlight-curated-ra-qxjc.bolt.host
