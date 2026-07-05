# Thoth — Universal Agent Operating Directives

This is MY Agent Operating directives, written in the way that I MYSELF utilise it.
Im happy to share it for whomever may be interested.

A single, model-agnostic markdown file that governs how an AI coding agent reasons,
searches for existing capability before generating new work, executes changes, and keeps
project documentation honest — without assuming a specific language, framework, project
domain, or harness.

Drop it at the root of a repository (or reference it from your global agent config) and
any agent that reads project-level instructions — Claude Code, Cursor, Windsurf, Copilot,
or similar — inherits the same operating discipline.

## What it actually does

- **Stops the agent from guessing when an answer already exists.** Before generating
  anything from scratch, the agent has to check: explicit instructions, existing project
  resources (docs, schemas, code), available Skills, and connected tools/MCP servers — in
  that order — and say so when it skips a step.
- **Gives it a decision hierarchy instead of vibes.** A fixed order for resolving
  conflicting instructions, and a "stop at first match" rule for choosing between a Skill,
  a tool, or plain generation, so the same request resolves the same way twice.
- **Makes self-review checkable, not just claimed.** A named failure taxonomy (blind
  generation, hallucinated absence, silent default, scope creep, test-shaped solutions,
  and more) the agent can audit its own output against, instead of a vague "did I do a
  good job" pass.
- **Keeps long-running and multi-session work coherent.** Rules for structured vs.
  unstructured state, git as a checkpoint mechanism, and how to re-orient after a context
  reset without re-litigating settled decisions.
- **Documents the project as it changes.** A [DOX framework](https://github.com/agent0ai/dox)
  (documentation hierarchy) that keeps a chain of `AGENTS.md` files current as the codebase
  grows — parent docs own broad rules, child docs own local specifics, and both get updated
  as part of finishing the work, not as an afterthought.
- **Enforces structural discipline on autonomous multi-file changes.** Isolation-by-default
  at new boundaries, topological organization for flow-shaped systems, discoverable naming,
  and a documented perimeter around legacy code instead of a risky one-shot rewrite.

## Design principles

- **Written to the agent, not about it.** Every line is a behavioral instruction, not a
  configuration note or deployment guide.
- **Deliberately domain- and language-neutral.** Where an example is unavoidable, it's
  flagged as illustrative so a fresh context window doesn't mistake it for a fact about
  your actual project.
- **Versioned and self-correcting.** The file carries its own changelog (§12) and expects
  corrections to be recorded there when drift is found — the same way a codebase tracks
  its own history.

## Usage

Copy `AGENTS.md` into the root of your project. That's it — no build step, no
configuration. Add subtree-specific `AGENTS.md` files as your project grows, per §13
(the [DOX framework](https://github.com/agent0ai/dox)) and §14.4 (hyper-local docs at
boundary creation).

## Works alone, better together

This file governs *reasoning and behavior*. It's fully functional on its own, but it's
written to complement — not duplicate — a dedicated skills framework. It's intended and
preferred to be used alongside
[obra/superpowers](https://github.com/obra/superpowers), which supplies the
procedural playbooks this file's Skill-check step (§2, §3) is designed to find and defer
to.

## Status

Actively maintained and corrected against real usage. See the file's own §12 Changelog
for version history.
