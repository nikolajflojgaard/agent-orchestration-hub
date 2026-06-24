# Agent Orchestration Hub

Reusable OpenClaw/Codex skill for coordinating multiple agents without turning the work into chaos.

The skill treats the main agent as the orchestration hub. Subagents can research, build, review, test, monitor, or write, but the hub remains responsible for scope, privacy, validation, merge gates, and the final answer.

## What It Solves

Multi-agent work fails when agents all act with equal authority, share too much context, or write into the same files. This skill gives the hub a simple operating model:

- split work only when parallelism is useful
- assign one owner per writable surface
- brief agents with narrow scope and clear stop conditions
- track lane state and artifacts
- verify subagent output before merging
- clean up and report what actually shipped

## Contents

- `SKILL.md` - the reusable skill instructions
- `templates/agent-brief.md` - subagent launch template
- `templates/hub-state.json` - resumable orchestration state template
- `templates/final-report.md` - final synthesis template
- `examples/hub-state-example.json` - example multi-repo security sweep state
- `docs/` - generated architecture documentation and orchestration model notes

## Quick Use

1. Decide whether the task deserves multiple agents.
2. Pick the orchestration shape: `solo`, `fanout`, `builder-reviewer`, `pipeline`, or `monitor`.
3. Create a lane board with one writer per file surface.
4. Brief each agent with `templates/agent-brief.md`.
5. Track state with `templates/hub-state.json` for long-running work.
6. Verify everything in the hub before committing, pushing, publishing, or finalizing.

## Status

This repo packages the pending Skill Workshop proposal:

`agent-orchestration-hub-20260624-932a2d3058`

It is ready for review, iteration, and eventual application/publishing.
