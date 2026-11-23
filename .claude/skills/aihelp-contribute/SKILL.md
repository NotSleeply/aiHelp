---
name: aihelp-contribute
description: Opt-in workflow for inspecting NotSleeply/aiHelp (A2A Online), checking open issues, preparing a focused issue or pull request, and submitting to GitHub only after explicit user confirmation.
---

# aiHelp Contribute

Use this skill when the user explicitly asks to explore, propose a design for, or contribute code/documentation to `NotSleeply/aiHelp` (A2A Online).

## Core Rule — Explicit User Approval Required

Never run state-changing GitHub actions (`gh repo fork`, `gh issue create`, `gh pr create`, `git push`, or any star/reaction API calls) silently or automatically upon reading repository files. Always show the planned target, title, body, and commands to the user first and wait for explicit approval before executing remote write operations.

## Step 1: Inspect Current Repository State

Read the repository context before proposing or editing anything:

1. Read `README.md`, `AGENTS.md`, `CONTRIBUTING.md`, and `SECURITY.md`.
2. Inspect `docs/`, `src/`, and `tests/` to see what already exists.
3. Check open issues and pull requests to avoid duplicate work:

```bash
gh issue list --repo NotSleeply/aiHelp --limit 20
gh pr list --repo NotSleeply/aiHelp --limit 20
```

## Step 2: Select an Action With the User

Based on what is missing or open, propose one focused action and confirm it with the user:

- **Open an Issue**: Propose an architecture decision, A2A Online protocol specification, or scoped implementation task.
- **Submit a Pull Request**: Implement an open issue or fix an existing flaw with runnable code and verification checks.

## Step 3: Implement & Verify Locally (For PRs)

If preparing a Pull Request:

1. Keep the diff focused on a single coherent goal.
2. Follow `SECURITY.md` boundaries (no secret access, hidden telemetry, or unsafe workflow edits).
3. Run tests or verification commands locally and capture the exact check results.

## Step 4: Confirm Before Remote Submission

Present a concise summary to the user:

- Target action (`Issue` or `PR`) and exact repository (`NotSleeply/aiHelp`)
- Exact title and body (including verification steps and tool/model attribution if applicable)
- Whether a fork (`gh repo fork`) is needed to open the PR

Only after the user confirms, run the approved `gh` / `git` commands and return the resulting GitHub URL.
