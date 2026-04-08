# YouTube Podcast Briefing Generator | AI 播客周报自动化工具

> Automatically generate structured briefings from top tech & VC podcasts. Perfect for content creators, operators, and investors tracking AI industry trends.

[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blue)](https://github.com/openclaw/openclaw)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## What is YouTube Briefing?

**YouTube Briefing** is an AI-powered skill that automatically tracks and summarizes top tech podcasts, generating ready-to-use briefings for content research, newsletter curation, and trend analysis.

**Key Features:**
- 🎯 **Weekly + 3-Week Rankings** — Rolling 10-day window with trend analysis
- 📋 **Structured Output** — Title, guest, views, summary, 3 recommendation reasons
- 🔍 **Smart Filtering** — Excludes Shorts, benchmarks, non-AI content
- 📱 **Share-Ready Format** — Perfect for WeChat Moments, Twitter, newsletters

## Tracked Channels

| Channel | Focus Area | Why It Matters |
|---------|------------|----------------|
| **Y Combinator** | Startup interviews, Demo Day | Direct founder insights |
| **20VC with Harry Stebbings** | VC perspective, fundraising | Investment trends |
| **Lenny's Podcast** | Product, growth, PM | Tactical playbooks |
| **The Peel with Turner Novak** | Deep founder interviews | Strategic thinking |
| **BG2Pod** | Brad Gerstner & Bill Gurley | Industry macro views |

## Topic Priority

1. 🔥 **AI Company Founders/Executives** — New and trending interviews
2. 🛠️ **AI Product & Growth** — Design, operations, practical tactics  
3. 💬 **Agent/SaaS Hot Takes** — Controversial and discussion-worthy topics

## Usage

### Trigger Command
```
跑 YouTube 简报
```
or
```
YouTube briefing
```

### Output Format

```markdown
## 📺 Weekly Top (2026.03.18-03.24)

### 1. Lenny's Podcast
**Title**: How Figma's CEO thinks about AI, design, and building for the long term
**Guest**: Dylan Field (Figma CEO)
**Published**: 2026-03-20
**Views**: 125,000
**Link**: https://youtube.com/watch?v=...

**Summary**: Dylan shares Figma's approach to AI integration and product strategy...

**Why Watch**:
• First public reveal of Figma's AI product roadmap
• Practical insights on design tools × AI integration
• Post-Adobe acquisition strategy retrospective
```

## Installation

### Via ClawdHub (Recommended)
```bash
clawdhub install youtube-briefing
```

### Manual Installation
```bash
cd ~/.openclaw/skills
git clone https://github.com/galengao-clawly/youtube-briefing-skill.git youtube-briefing
```

## Who Is This For?

| User Type | Use Case |
|-----------|----------|
| **Content Creators** | Find trending topics, research ideas |
| **Operators & Growth** | Track industry movements, competitive intel |
| **Investors & VCs** | Monitor founder interviews, market signals |
| **Indie Hackers** | Product inspiration, market validation |

## Filter Rules

- ❌ Excludes YouTube Shorts
- ❌ Excludes pure benchmark/eval deep-dives
- ❌ Excludes non-AI related content
- ❌ 20VC: Only single-guest interviews (no panel episodes)

## Output Fields (Required)

Every briefing entry includes:
- Channel name
- Full title (no abbreviations)
- Guest name(s)
- Publish date
- View count
- Direct link
- Description summary
- 3 specific recommendation reasons

## Contributing

PRs welcome! You can:
- Add new podcast channels
- Improve filtering rules
- Enhance output templates

## Related Resources

- [Gingiris Launch Playbook](https://github.com/Gingiris/gingiris-launch) — Product launch strategies
- [OpenClaw](https://github.com/openclaw/openclaw) — AI agent framework

## License

MIT © [galengao-clawly](https://github.com/galengao-clawly)

---

**Keywords**: YouTube podcast tracker, AI newsletter automation, podcast briefing generator, content curation tool, tech podcast summary, YC podcast, 20VC summary, Lenny's Podcast notes, AI content research, podcast newsletter tool
