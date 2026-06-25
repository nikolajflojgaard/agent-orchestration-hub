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

- [ ] **Agent QA / Red Team**
  - Read-only review pattern for bugs, hallucinations, security issues, missing validation, and weak reasoning.
  - Use as the default second pass for serious work.

- [ ] **Agent Memory Distiller**
  - Review daily notes, commits, chats, and outcomes.
  - Promote only durable lessons into long-term memory.
  - Avoid context rot and memory bloat.

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

**Agent QA / Red Team** is the next build.

Reason: the hub, fleet maintainer, and workbench now make it easier to split and run work. The next weak point is independent quality control: serious tasks should get a reusable read-only second pass for bugs, security, validation gaps, and weak reasoning.

## Acceptance Criteria For Agent QA / Red Team

- [ ] Defines read-only reviewer roles for code, docs, security, validation, and reasoning.
- [ ] Provides checklists that prioritize findings over summaries.
- [ ] Requires file/line evidence or reproducible commands for claims.
- [ ] Separates blockers, high-confidence findings, questions, and low-confidence risks.
- [ ] Detects missing validation and overclaimed completion.
- [ ] Includes privacy and secret-handling rules.
- [ ] Produces concise review reports that the hub can act on.
- [ ] Fits builder-reviewer and release-gate workflows.

## Operating Principles

- Safe small fixes beat broad clever rewrites.
- Dirty worktrees are respected, not cleaned up casually.
- Public/external actions require approval unless already authorized.
- Reports should be short enough to read and specific enough to act on.
- The hub remains accountable for commits, pushes, and final claims.
