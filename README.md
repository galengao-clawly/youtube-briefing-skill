# YouTube Briefing Skill

Generate a curated Chinese briefing for AI-related YouTube podcasts, VC podcasts, founder interviews, and operator conversations.

This skill is designed for weekly AI media monitoring. It does not simply summarize YouTube videos. It discovers candidate episodes, filters them, ranks them, and produces an opinionated briefing that helps the reader decide what is worth watching.

## When To Use

Use this skill when the user asks for any of these workflows:

- Run a YouTube briefing
- Run a YouTube podcast briefing
- Build an AI podcast weekly ranking
- Build a 3-week ranking
- Curate editor picks
- Filter podcast candidates
- Create a recommendation list suitable for sharing

The skill is especially useful for tracking AI founders, AI executives, AI-native companies, SaaS transformation, agents, product, growth, GTM, and VC/operator conversations.

## Default Output

A full run produces three sections:

1. Weekly Overview
   - 300 Chinese characters or less
   - Summarizes the week's recurring themes, frequently mentioned companies, and major viewpoints
   - Ends with a short sentence naming 3-5 recommended channels for the week

2. 7-Day Top 3
   - Strict rolling 7-day window
   - Exactly 3 ranked items

3. 3-Week Top 8
   - Recent 3-week comparison
   - Exactly 8 ranked items

Each ranked item must include:

- Section name
- Full title, not shortened
- Guest, formatted as: `Name | Company | Title`
- Published date, using a concrete date
- View count
- Link
- Description summary or translation
- Three specific recommendation reasons

## Selection Priorities

Rank candidates by topic relevance first. Use view count only as a tie-breaker inside the same relevance tier.

Priority order:

1. Interviews with founders or executives from new and fast-growing AI companies
2. Practical AI product, design, growth, GTM, and operations discussions
3. Agent, SaaS transformation, and AI-native company debates

Filter out:

- YouTube Shorts
- Non-AI topics
- Pure benchmark or eval deep-dives
- 20VC multi-guest compilation episodes

For 20VC, include only single-guest interview episodes.

## Source Pool

The source pool is additive. These sources should be included during candidate discovery, but the final ranking still depends on the rules in `SKILL.md`.

Current source pool includes:

- The Peel with Turner Novak
- BG2Pod with Brad Gerstner and Bill Gurley
- moonshots playlist
- a16z
- Joe Lonsdale
- Subversive
- Y Combinator
- Peter Yang
- Lenny's Podcast
- Sequoia Training Data
- Long Strange Trip
- Sub Club Podcast
- Redpoint Unsupervised Learning
- The Logan Bartlett Show
- Redpoint Vital Signs
- First Round In Depth
- First Round Capital
- Bessemer This Is Series A
- Bessemer Cloud Giants
- Bessemer Wish I Knew
- Bessemer Heart of Healthcare
- Bessemer A Healthy Dose
- Greylock Greymatter
- Kleiner Perkins Grit
- Lightspeed Generative Now
- NFX Podcast
- Accel Spotlight On

## Output Style

The generated briefing should be:

- Chinese-first
- Suitable for sharing to WeChat Moments or Slack
- Specific and reusable, not generic
- Opinionated enough to help the reader decide what to watch

Avoid vague recommendation language. Every recommendation reason should say why the item matters, who it is useful for, or what decision it helps inform.

## Persistence

Each full run should save the complete briefing as a local `.md` file, usually under `notebook/`.

For Slack delivery, format video links using Slack angle-bracket links so they render as clickable hyperlinks:

```text
<https://www.youtube.com/watch?v=VIDEO_ID|YouTube video>
```

## Feedback Loop

After a weekly briefing is sent, it is useful to send a compact follow-up list of selected items and ask for feedback:

- Should this item stay?
- Should it move up or down?
- Should it be excluded next time?
- What was the real reason it mattered or did not matter?

Use that feedback to improve future ranking rules, source weighting, and exclusion criteria in `SKILL.md`.

## Maintaining The Skill

Update `SKILL.md` when:

- A new podcast or channel should be added to the source pool
- Ranking rules become more specific
- User feedback reveals better selection criteria
- Required output fields change
- Distribution format changes

`SKILL.md` is the source of truth for agent behavior. This README is the human-facing overview.
