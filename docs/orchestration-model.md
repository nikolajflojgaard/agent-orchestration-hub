# Orchestration Model

This skill uses the main agent as an orchestration hub, not a passive dispatcher.

## Control Loop

1. Intake the user's objective, constraints, and approval boundaries.
2. Decide whether multi-agent work is worth the overhead.
3. Split the work into lanes with one owner per writable surface.
4. Brief each agent with narrow context, scope, validation, and stop conditions.
5. Track lane state, artifacts, blockers, and merge gates.
6. Verify subagent output from the hub session.
7. Consolidate the smallest coherent result.
8. Clean up sessions, scratch files, and final status.

## State Model

The hub state captures:

- objective and constraints
- lane ownership
- allowed reads and writes
- current status
- validation gates
- artifacts and evidence
- residual risks

Use `templates/hub-state.json` for long-running or resumable work.

## Agent Roles

| Role | Writes | Primary Output |
| --- | --- | --- |
| Researcher | No | sourced findings |
| Mapper | No | inventory and boundaries |
| Builder | Scoped | patch and validation |
| Reviewer | No | risks and findings |
| Tester | Usually no | test results |
| Release Captain | Scoped after approval | release/deploy proof |
| Monitor | No | final job status |
| Writer | Scoped | channel-ready prose |

## Merge Discipline

The hub should never merge or ship work simply because a subagent produced it.

Before finalizing, the hub checks scope, dirty worktrees, validation output, security/privacy boundaries, and external-action approval. This is the main difference between orchestration and chaos.
