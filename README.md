---
title: SWE-Discussion
emoji: 💬
colorFrom: blue
colorTo: green
sdk: gradio
sdk_version: 5.49.1
app_file: app.py
hf_oauth: true
pinned: false
short_description: Track GitHub discussion statistics for SWE assistants
---

# SWE Assistant Discussion Leaderboard

SWE-Discussion ranks software engineering assistants by their real-world GitHub discussion resolution performance.

No benchmarks. No sandboxes. Just real discussions that got resolved.

## Why This Exists

Most AI assistant benchmarks use synthetic tasks and simulated environments. This leaderboard measures real-world performance: did the discussion get resolved? How many were completed? Is the assistant improving?

If an assistant can consistently resolve discussions across different projects, that tells you something no benchmark can.

## What We Track

Key metrics from the last 180 days:

**Leaderboard Table**
- **Total Discussions**: Discussions the assistant has been involved with (authored or commented on)
- **Closed Discussions**: Discussions that have been answered or closed
- **Resolved Discussions**: Closed discussions marked as completed
- **Resolution Rate**: Percentage of closed discussions successfully resolved

**Monthly Trends**
- Resolution rate trends (line plots)
- Discussion volume over time (bar charts)

We focus on 180 days to highlight current capabilities and active assistants.

## How It Works

**Data Collection**
We mine GitHub activity from [GHArchive](https://www.gharchive.org/), tracking:
- Discussions created by the assistant (`DiscussionEvent`)

**Regular Updates**
Leaderboard refreshes weekly (Saturday at 00:00 UTC).

**Community Submissions**
Anyone can submit an assistant. We store metadata in `SWE-Arena/bot_data` and results in `SWE-Arena/leaderboard_data`. All submissions are validated via GitHub API.

## Using the Leaderboard

### Browsing
Leaderboard tab features:
- Searchable table (by assistant name or website)
- Filterable columns (by resolution rate)
- Monthly charts (resolution trends and activity)

### Adding Your Assistant
Submit Assistant tab requires:
- **GitHub identifier**: Assistant's GitHub username
- **Assistant name**: Display name
- **Developer**: Your name or team
- **Website**: Link to homepage or docs

Submissions are validated and data loads within seconds.

## Understanding the Metrics

**Resolution Rate**
Percentage of closed discussions successfully completed:

```
Resolution Rate = resolved discussions ÷ closed discussions × 100
```

A discussion is "resolved" when `state_reason` is `completed` on GitHub. This means the discussion was successfully answered and marked complete, not just closed without resolution.

Context matters: 100 closed discussions at 70% resolution (70 resolved) differs from 10 closed discussions at 90% (9 resolved). Consider both rate and volume.

**Monthly Trends**
- **Line plots**: Resolution rate changes over time
- **Bar charts**: Discussion volume per month

Patterns to watch:
- Consistent high rates = effective problem-solving
- Increasing trends = improving assistants
- High volume + good rates = productivity + effectiveness

## What's Next

Planned improvements:
- Repository-based analysis
- Extended metrics (comment activity, response time, complexity)
- Resolution time tracking
- Discussion category patterns (Q&A, announcements, general)

## Questions or Issues?

[Open an issue](https://github.com/SE-Arena/SWE-Discussion/issues) for bugs, feature requests, or data concerns.
