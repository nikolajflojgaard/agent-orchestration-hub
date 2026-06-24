# Agent Utilization Roadmap

This is the working tasklist for building a stronger personal agent operating system around the orchestration hub.

## Priority Queue

- [x] **Repo Fleet Maintainer**
  - Maintain all active repos with dependency audits, CI/deploy checks, stale branch checks, missing docs, security headers, and safe small updates.
  - Output weekly report plus safe commits/PRs where appropriate.
  - Keep breaking upgrades, missing secrets, and dirty worktrees as explicit human-review items.
  - Repo shipped: https://github.com/nikolajflojgaard/repo-fleet-maintainer

- [ ] **Agent Workbench**
  - Turn messy user requests into lanes, briefs, state, artifacts, validation gates, and final reports.
  - Make this the day-to-day operating workflow for multi-agent tasks.

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

**Repo Fleet Maintainer** is the next build.

Reason: today already proved the value. Several repos had stale dependencies, missing deploy secrets, dirty worktrees, and repeated Astro upgrade risk. This should become a repeatable agent workflow instead of manual sweeping.

## Acceptance Criteria For Repo Fleet Maintainer

- [ ] Discovers active repos from configured roots.
- [ ] Classifies repo type: Node, Python, static site, Home Assistant integration, skill repo, unknown.
- [ ] Runs read-only health checks first.
- [ ] Detects dirty worktrees and preserves user changes.
- [ ] Runs dependency audits where safe.
- [ ] Applies only non-breaking fixes automatically when explicitly authorized.
- [ ] Separates breaking upgrades into review items.
- [ ] Checks CI/deploy status and failed workflow logs.
- [ ] Scans for obvious leaked secret files or token patterns.
- [ ] Produces a concise fleet report.
- [ ] Can be scheduled later without becoming noisy.

## Operating Principles

- Safe small fixes beat broad clever rewrites.
- Dirty worktrees are respected, not cleaned up casually.
- Public/external actions require approval unless already authorized.
- Reports should be short enough to read and specific enough to act on.
- The hub remains accountable for commits, pushes, and final claims.
