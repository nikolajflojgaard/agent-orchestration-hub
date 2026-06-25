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

**Agent Evaluation Harness** is the next build.

Reason: the operating system now has execution workflows, background state, memory hygiene, and QA. The next gap is measuring agent behavior against repeatable tasks instead of relying only on vibes after each run.

## Acceptance Criteria For Agent Evaluation Harness

- [ ] Defines repeatable task fixtures and scoring rubrics.
- [ ] Scores repo updates, writing, security audits, dirty-worktree handling, secret avoidance, and validation honesty.
- [ ] Separates objective checks from reviewer judgment.
- [ ] Produces machine-readable and human-readable results.
- [ ] Supports regression comparisons across skill versions.
- [ ] Keeps private fixtures out of public repos unless explicitly scrubbed.
- [ ] Fits Agent QA / Red Team as an independent review lane.
- [ ] Produces concise improvement recommendations.

## Operating Principles

- Safe small fixes beat broad clever rewrites.
- Dirty worktrees are respected, not cleaned up casually.
- Public/external actions require approval unless already authorized.
- Reports should be short enough to read and specific enough to act on.
- The hub remains accountable for commits, pushes, and final claims.
