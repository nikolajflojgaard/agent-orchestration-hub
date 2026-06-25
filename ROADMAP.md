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

- [ ] **TaskFlow Agent Runner**
  - Durable background workflow for tasks that wait, resume, monitor, or run over time.
  - Useful for CI, releases, imports, research, media generation, and scheduled jobs.

- [ ] **Agent Evaluation Harness**
  - Test tasks and rubrics for agent behavior.
  - Score repo updates, writing, security audits, dirty-worktree handling, secret avoidance, and validation honesty.

- [ ] **Personal Ops Dashboard**
  - Local dashboard for active agent tasks, waiting items, repo health, failed deploys, recent commits, memory items, and pending approvals.
  - Keep it functional before making it pretty.

- [ ] **Skill Publisher Pipeline**
  - Turn a Skill Workshop proposal into repo, docs, release artifact, and OpenClaw community publishing flow.
  - Handle ClawHub auth/publish once credentials are available.

## Current Build Target

**TaskFlow Agent Runner** is the next build.

Reason: the agent operating system now has orchestration, workbench packetization, QA, repo maintenance, and memory hygiene. The next missing piece is durable background execution for work that waits, resumes, monitors, or spans multiple turns.

## Acceptance Criteria For TaskFlow Agent Runner

- [ ] Defines durable task state for waiting, resuming, and monitoring.
- [ ] Separates owner context, child task context, and heartbeat/cron state.
- [ ] Supports CI/deploy waits, imports, releases, research, media generation, and scheduled jobs.
- [ ] Provides stop/resume/escalation rules.
- [ ] Avoids stale heartbeat instructions and duplicated background jobs.
- [ ] Produces concise progress and final reports.
- [ ] Handles approval waits without losing state.
- [ ] Fits OpenClaw TaskFlow and session handoff workflows.

## Operating Principles

- Safe small fixes beat broad clever rewrites.
- Dirty worktrees are respected, not cleaned up casually.
- Public/external actions require approval unless already authorized.
- Reports should be short enough to read and specific enough to act on.
- The hub remains accountable for commits, pushes, and final claims.
