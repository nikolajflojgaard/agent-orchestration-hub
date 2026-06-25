# Agent Utilization Roadmap

This is the working tasklist for building a stronger personal agent operating system around the orchestration hub.

## Priority Queue

- [x] **Repo Fleet Maintainer**
  - Maintain all active repos with dependency audits, CI/deploy checks, stale branch checks, missing docs, security headers, and safe small updates.
  - Output weekly report plus safe commits/PRs where appropriate.
  - Keep breaking upgrades, missing secrets, and dirty worktrees as explicit human-review items.
  - Repo shipped: https://github.com/nikolajflojgaard/repo-fleet-maintainer

- [x] **Agent Workbench**
  - Turn messy user requests into lanes, briefs, state, artifacts, validation gates, and final reports.
  - Make this the day-to-day operating workflow for multi-agent tasks.
  - Repo shipped: https://github.com/nikolajflojgaard/agent-workbench

- [x] **Agent QA / Red Team**
  - Read-only review pattern for bugs, hallucinations, security issues, missing validation, and weak reasoning.
  - Use as the default second pass for serious work.
  - Repo shipped: https://github.com/nikolajflojgaard/agent-qa-red-team

- [x] **Agent Memory Distiller**
  - Review daily notes, commits, chats, and outcomes.
  - Promote only durable lessons into long-term memory.
  - Avoid context rot and memory bloat.
  - Repo shipped: https://github.com/nikolajflojgaard/agent-memory-distiller

- [x] **TaskFlow Agent Runner**
  - Durable background workflow for tasks that wait, resume, monitor, or run over time.
  - Useful for CI, releases, imports, research, media generation, and scheduled jobs.
  - Repo shipped: https://github.com/nikolajflojgaard/taskflow-agent-runner

- [x] **Agent Evaluation Harness**
  - Test tasks and rubrics for agent behavior.
  - Score repo updates, writing, security audits, dirty-worktree handling, secret avoidance, and validation honesty.
  - Repo shipped: https://github.com/nikolajflojgaard/agent-evaluation-harness

- [x] **Code Doc Pipeline GitHub Rollout**
  - Make code-doc-pipeline a deliberate default where appropriate across GitHub repos.
  - Distinguish generated docs/config coverage from actual CI workflow coverage.
  - Exclude repos where generated docs are not useful or privacy-safe.
  - Wave 1 shipped to the skill/agent repos with green Code docs Actions.
  - Wave 2 shipped to clean public app/integration repos with green Code docs Actions.

- [ ] **Personal Ops Dashboard**
  - Local dashboard for active agent tasks, waiting items, repo health, failed deploys, recent commits, memory items, and pending approvals.
  - Keep it functional before making it pretty.

- [ ] **Skill Publisher Pipeline**
  - Turn a Skill Workshop proposal into repo, docs, release artifact, and OpenClaw community publishing flow.
  - Handle ClawHub auth/publish once credentials are available.

## Current Build Target

**Personal Ops Dashboard** is the next build.

Reason: the core workflow skills, QA, memory, TaskFlow runner, evaluation harness, and code-doc CI rollout are now in place. The next useful layer is a local operational view of active tasks, waits, repo health, failed deploys, recent commits, memory items, and pending approvals.

## Acceptance Criteria For Code Doc Pipeline GitHub Rollout

- [x] Produce an explicit repo inclusion/exclusion plan.
- [x] Add or verify `code-docs.yml` for included repos.
- [x] Generate useful docs and Mermaid diagrams for included repos.
- [x] Add GitHub Actions docs check where CI is appropriate.
- [x] Avoid privacy-sensitive docs in private or backup repos unless explicitly approved.
- [x] Preserve dirty worktrees and existing CI/deploy behavior.
- [x] Validate `code_docs.py check` and Mermaid diagrams per repo.
- [x] Report repos intentionally deferred or excluded.

## Code Doc Pipeline GitHub Rollout Summary

Included with green Code docs Actions:

- `agent-orchestration-hub`
- `repo-fleet-maintainer`
- `agent-workbench`
- `agent-qa-red-team`
- `agent-memory-distiller`
- `taskflow-agent-runner`
- `agent-evaluation-harness`
- `home-assistant-home-brief`
- `homeassistant-household-chores`
- `homeassistant-investing-score-card`
- `homeassistant-weekly-training`
- `mjk-judo`
- `reichkendlersolutions`

Supporting generator update:

- `code-doc-pipeline` now supports stable `repository_name` metadata so CI checkout folder names do not create false docs drift.
- `code-doc-pipeline` excludes `.husky` helper files by default.

Deferred or excluded:

- Dirty local repos deferred to avoid trampling active work: `brands`, `egedalbogholderi`, `nikolajflojgaard.me`, `social-media-engagementbooster`, `tesla-fsd-ai-bot`, `venture-ai-copilot`.
- Private, backup, template, owner-mismatch, or unclear-scope repos are deferred until explicitly approved or classified.
- `code-doc-pipeline` remains self-managed with its existing validation workflow.

## Operating Principles

- Safe small fixes beat broad clever rewrites.
- Dirty worktrees are respected, not cleaned up casually.
- Public/external actions require approval unless already authorized.
- Reports should be short enough to read and specific enough to act on.
- The hub remains accountable for commits, pushes, and final claims.
