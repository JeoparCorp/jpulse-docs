# J² Pulse
A lightweight audio/video generator that delivers daily “Jeo News” briefings — like a personal business reporter for your team.


## What is J² Pulse?

**J² Pulse** is a JeoparDIZe micro-product that automatically:

- Scans your systems for relevant updates (e.g. issues, deployments, decisions, risks).
- Summarizes them into a clear narrative.
- Generates **daily or weekly audio/video briefings** tailored to your team.
- Delivers them where people already are (Slack, email, MS Teams, internal wiki, etc.).

Think of it as your **in-house business reporter** who never gets tired of explaining what actually matters. This will be used when the team meetings will be difficult to be hold, to connect the teams and gain some time back 

## Key Features

-  **Audio & Video Briefings**
  - Auto-generated voice briefings (podcast-style).
  - Optional video with slides / key points.

-  **Context-Aware Storyline**
  - Groups updates into themes: releases, incidents, experiments, decisions.
  - Highlights what changed since the last briefing — not a repeat of dashboards.

-  **Team-Specific Feeds**
  - Separate "News” channels for:
    - Engineering
    - Product
    - Design / UX
    - Leadership
  - Each team hears **only what is relevant** to them.

-  **Configurable Signal Sources**
  - Integrates with:
    - Issue trackers (e.g. Jira, Linear)
    - Repos / CI-CD (e.g. GitHub, GitLab)
    - Product tools (e.g. Notion, Confluence, FigJam links)
    - Communication tools (e.g. Slack channels, email summaries)

-  **Time-Bound, Digestible Format**
  - 3–7 minutes per briefing.
  - Designed for:
    - Commuting
    - First coffee of the day
    - Stand-up prep

-  **Private & Organization-Specific**
  - Learns from your **internal patterns**, not the public internet.
  - Respects access controls and team boundaries.

---

## Example News Briefing

> “Good morning, Product & Engineering.  
> In the last 24 hours, the team shipped **v1.4.2 of the AR rendering engine**, reducing load times by **18%**. Two high-priority bugs remain open, both related to audio sync on iOS.  
> Design completed the first round of usability tests for the onboarding flow — users struggled at step three; a follow-up iteration is already scheduled.  
> Today’s biggest risk: the payment integration is blocking the Friday release. Three dependencies are waiting on legal sign-off.  
> Recommended focus for today: unblock the payment integration and close the remaining iOS bugs.”

---

## Who Is J² Pulse For?

- **Heads of Engineering / VP Eng**
  - Stay on top of progress and risks without reading every ticket.
- **Product Managers**
  - Keep everyone aligned on priorities, decisions, and trade-offs.
- **Team Leaders**
  - Get a single narrative view across multiple squads.
- **Distributed / Hybrid Teams**
  - Reduce meeting overload by replacing status calls with Jeo News briefings.

---

## How It Works (Conceptual Flow)

1. **Connect Systems**
   - Select data sources (Jira, GitHub, Miro, Slack, etc.).
   - Define which team(s) each source belongs to.

2. **Configure Pulse**
   - Set frequency: `daily`, `weekly`, or `per-release`.
   - Choose output: `audio only`, `audio + video`, `video with slides`.
   - Configure tone: `formal`, `neutral`, or `conversational`.

3. **J² Pulse Engine Runs**
   - Extracts key events, decisions, anomalies.
   - Clusters by topic and team relevance.
   - Generates script + voice + (optional) visuals.

4. **Delivery**
   - Sends the briefing to:
     - Slack channel(s)
     - Email distribution lists
     - Internal wiki / portal
     - Shared drive / video hub

---

## Example Configuration (Pseudo-YAML)

```yaml
pulse_name: "Weekly Eng News"
frequency: "weekly"
duration_target_minutes: 5

audience:
  - "engineering"
  - "product"

sources:
  jira:
    projects: ["ENG", "MOBILE"]
    include_statuses: ["In Progress", "Done"]
  github:
    repos: ["org/app-frontend", "org/app-backend"]
    include: ["merged_prs", "releases"]
  slack:
    channels: ["#incidents", "#product-announcements"]

output:
  format: "audio_video"
  style: "conversational"
  voice_profile: "head_of_engineering_style"
  destination:
    slack_channels: ["#jeo-news-eng", "#jeo-news-product"]
    email_lists: ["eng-all@company.com"]


