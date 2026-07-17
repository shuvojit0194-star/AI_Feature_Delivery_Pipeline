# AI-Powered IT Feature Delivery Pipeline

An end-to-end autonomous SDLC pipeline that takes a Product Requirements Document and delivers production-deployed code — replacing a 16-step manual process with a single human trigger.

## Pipeline Architecture

### Before (Manual — 16 Steps)
![Manual SDLC Process](pipeline_before.png)

### After (AI-Automated)
![AI-Powered Pipeline](pipeline_after.png)

---

## How It Works

```
PRD Input
   │
   ▼
Claude AI — decomposes PRD into Epics & Stories
   │         with EARS-format acceptance criteria
   │
   ▼
Atlassian Rovo MCP — creates structured JIRA tickets
   │                  (Epic → Stories → Acceptance Criteria)
   │
   ▼
WebStorm IDE — JIRA integration pulls ticket automatically
   │            Claude AI coding agent reads the spec
   │            and implements the code (spec-driven development)
   │
   ▼
GitHub — code committed to feature branch
   │
   ▼
GitHub Actions — CI/CD pipeline (test → build → push)
   │
   ▼
Render — auto-deploy to production
```

## Human Touchpoints

Only **two** human checkpoints in the entire pipeline:
1. Writing the PRD
2. Reviewing JIRA tickets before code generation begins

Everything else — decomposition, spec writing, ticket creation, coding, CI/CD, and deployment — is automated.

## What Makes This Different

The key insight: **the JIRA ticket IS the spec.**

JIRA stories are written in EARS format (Easy Approach to Requirements Syntax) with precise acceptance criteria. When WebStorm's JIRA integration surfaces the ticket to the Claude AI coding agent, Claude has everything it needs to implement the feature without further instruction — no Slack messages, no handoff meetings, no back-and-forth.

## Tech Stack

| Layer | Tool |
|---|---|
| PRD Decomposition | Claude AI |
| JIRA Integration | Atlassian Rovo MCP |
| IDE + Coding Agent | WebStorm + Claude AI |
| Version Control | GitHub |
| CI/CD | GitHub Actions |
| Deployment | Render |

## Related Projects

- [PRD to JIRA Agent](https://github.com/shuvojit0194-star/PRD_to_Jira_AI_Agent) — the n8n workflow that handles PRD decomposition → JIRA ticket creation
- [MCP Chatbot](https://github.com/shuvojit0194-star/Chatbot) — a live project built using this pipeline
- [Weather Feature SCRUM Specs](https://github.com/shuvojit0194-star/Weather_Feature_SCRUM) — example EARS-format ticket specs that feed the coding agent
