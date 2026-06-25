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

- [ ] **Code Doc Pipeline GitHub Rollout**
  - Make code-doc-pipeline a deliberate default where appropriate across GitHub repos.
  - Distinguish generated docs/config coverage from actual CI workflow coverage.
  - Exclude repos where generated docs are not useful or privacy-safe.

- [ ] **Personal Ops Dashboard**
  - Local dashboard for active agent tasks, waiting items, repo health, failed deploys, recent commits, memory items, and pending approvals.
  - Keep it functional before making it pretty.

- [ ] **Skill Publisher Pipeline**
  - Turn a Skill Workshop proposal into repo, docs, release artifact, and OpenClaw community publishing flow.
  - Handle ClawHub auth/publish once credentials are available.

## Current Build Target

**Code Doc Pipeline GitHub Rollout** is the next build.

Reason: a GitHub-wide audit showed code-doc-pipeline is not embedded as a default across repos. The skill repos have `code-docs.yml` and generated docs, but they do not yet have GitHub Actions docs checks; most other repos have no code-doc-pipeline config or generated docs.

## Acceptance Criteria For Code Doc Pipeline GitHub Rollout

- [ ] Produce an explicit repo inclusion/exclusion plan.
- [ ] Add or verify `code-docs.yml` for included repos.
- [ ] Generate useful docs and Mermaid diagrams for included repos.
- [ ] Add GitHub Actions docs check where CI is appropriate.
- [ ] Avoid privacy-sensitive docs in private or backup repos unless explicitly approved.
- [ ] Preserve dirty worktrees and existing CI/deploy behavior.
- [ ] Validate `code_docs.py check` and Mermaid diagrams per repo.
- [ ] Report repos intentionally deferred or excluded.

## Operating Principles

- Safe small fixes beat broad clever rewrites.
- Dirty worktrees are respected, not cleaned up casually.
- Public/external actions require approval unless already authorized.
- Reports should be short enough to read and specific enough to act on.
- The hub remains accountable for commits, pushes, and final claims.
