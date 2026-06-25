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

- [x] **Personal Ops Dashboard**
  - Local dashboard for active agent tasks, waiting items, repo health, failed deploys, recent commits, memory items, and pending approvals.
  - Keep it functional before making it pretty.
  - Repo shipped: https://github.com/nikolajflojgaard/personal-ops-dashboard
  - Local refresh LaunchAgent installed: `ai.openclaw.personal-ops-dashboard`

- [x] **Skill Publisher Pipeline**
  - Turn a Skill Workshop proposal into repo, docs, release artifact, and OpenClaw community publishing flow.
  - Handle ClawHub auth/publish once credentials are available.
  - Repo shipped: https://github.com/nikolajflojgaard/skill-publisher-pipeline

## Current Build Target

**Roadmap core stack is shipped.**

Reason: the core workflow skills, QA, memory, TaskFlow runner, evaluation harness, code-doc CI rollout, startup layer, local ops visibility, and skill packaging path are now in place. The remaining gap is not another local skill; it is authenticated community publishing once ClawHub/community credentials are ready.

## Acceptance Criteria For Skill Publisher Pipeline

- [x] Package a local skill or proposal export into a clean release directory.
- [x] Validate `SKILL.md` frontmatter and skill naming.
- [x] Copy only approved support folders into the package.
- [x] Generate manifest, validation report, release notes, publish checklist, and zip archive.
- [x] Keep community/ClawHub publishing as an explicit gate instead of an implied success.
- [x] Generate docs, diagrams, and Code docs CI for the repo.
- [x] Publish public repo and verify Code docs workflow.

## Skill Publisher Pipeline Summary

Skill Publisher Pipeline turns local skills or proposal exports into release-ready packages while keeping release statuses honest.

Runtime:

- Source repo: https://github.com/nikolajflojgaard/skill-publisher-pipeline
- Packager: `scripts/skill_publisher_pipeline.py`
- Current community publishing status: blocked on ClawHub/community auth readiness.

## Acceptance Criteria For Personal Ops Dashboard

- [x] Show OpenClaw gateway and node service status.
- [x] Show active tasks, task audit health, cron snapshot, and recent sessions.
- [x] Show local repo dirty/clean state and latest commits.
- [x] Show recent GitHub workflow runs for tracked repos.
- [x] Show pending approvals snapshot.
- [x] Show memory note freshness.
- [x] Generate a local dashboard without requiring a dev server.
- [x] Install a macOS LaunchAgent refresh loop.
- [x] Keep generated dashboard data out of git.
- [x] Generate docs, diagrams, and Code docs CI for the dashboard repo.

## Personal Ops Dashboard Summary

The dashboard is a local static HTML surface generated from OpenClaw, git, GitHub, and memory files. It is deliberately local-first because it can show private operational context.

Runtime:

- LaunchAgent: `ai.openclaw.personal-ops-dashboard`
- Refresh cadence: every five minutes and at login.
- Runtime path: `~/.openclaw/personal-ops-dashboard/dashboard/index.html`
- Source repo: https://github.com/nikolajflojgaard/personal-ops-dashboard

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
