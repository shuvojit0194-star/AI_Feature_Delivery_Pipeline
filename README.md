# AI-Powered IT Feature Delivery Pipeline

Autonomous end-to-end SDLC pipeline that takes a Product Requirements Document (PRD) and delivers production-deployed code — replacing a 16-step manual process with a single human trigger.

## What It Does

| Phase | Step | Tool |
|---|---|---|
| 1 | Parse PRD → decompose into Epics & Stories | Claude AI |
| 2 | Generate EARS-format acceptance criteria | Claude AI |
| 3 | Create & transition JIRA tickets | Atlassian Rovo MCP |
| 4 | Scaffold code, commit to feature branch | GitHub MCP |
| 5 | Trigger CI/CD pipeline | GitHub Actions |
| 6 | Deploy to production | Render |

Human-in-the-loop at two checkpoints only: PRD creation and ticket review before code generation.

## Architecture

```
PRD Input
   │
   ▼
Claude AI (Orchestrator)
   ├── Atlassian Rovo MCP → JIRA Epic/Story creation
   ├── GitHub MCP         → Code scaffold + branch commit
   ├── GitHub Actions     → CI/CD (test → build → push)
   └── Render             → Auto-deploy on merge
```

## Tech Stack

- **Orchestrator:** Claude AI (claude-sonnet-4-5)
- **MCP Integrations:** Atlassian Rovo MCP, GitHub MCP
- **CI/CD:** GitHub Actions
- **Deployment:** Render
- **Language:** Python

## Business Impact

Eliminates an estimated 16 manual steps per feature — from PRD to deployed code — while maintaining full audit trail in JIRA and Git.

## Files

| File | Description |
|---|---|
| `pipeline_before.png` | Manual 16-step SDLC workflow (as-is) |
| `pipeline_after.png` | AI-automated pipeline (to-be) |
| `project_overview.docx` | Full design document |

## Related Projects

- [PRD to JIRA AI Agent](../PRD_to_Jira_AI_Agent) — the JIRA decomposition layer
- [MCP Deploy](../MCP_Deploy) — the MCP server powering agent integrations
