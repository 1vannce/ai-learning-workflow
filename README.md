# AI Learning Workflow

This repository is a provider-agnostic wrapper around the ideas from [amosblomqvist/learn](https://github.com/amosblomqvist/learn), adapted so the same teaching workflow can be used with external agent environments such as Claude, Codex, and GitHub Copilot.

The original project is centered around a teaching system built around strong fundamentals, dependency graphs, and structured learning loops. This fork keeps that core approach but separates the reusable instructions from the provider-specific adapter files, making it easier to use the same agent design across different tools and platforms.

## What this repo does

It provides:

- a shared, canonical set of agent instructions
- reusable teaching and visualization skills
- provider-specific adapter folders so the same behavior can be exposed through different agent runtimes
- a structure that is easy to extend with new roles, tools, and workflows

The goal is not just to let an AI answer questions, but to make it teach in a way that builds real understanding instead of memorized facts.

## Why this exists

The base `learn` project demonstrates a powerful pattern: use a small number of strong principles, a clear teaching process, and explicit dependency-driven explanations.

This repository adapts that pattern for agent ecosystems outside the original environment by dividing the project into:

- shared prompts and rules in `AGENTS.md`, `agents/`, and `skills/`
- provider adapters in `.github/`, `.claude/`, and `.agents/`

That makes the same underlying teaching system portable across multiple AI coding assistants.

## Repository structure

- `AGENTS.md` — top-level instructions for the project and shared behavioral rules
- `agents/` — canonical agent definitions used as the base behavior
- `skills/` — reusable skill files such as teaching and visualization workflows
- `.github/` — GitHub Copilot adapter files
- `.claude/` — Claude adapter files
- `.agents/` — additional provider-specific adapter layer
- `.gitignore` — repo-local ignore rules

## Core idea

The system follows a teaching loop built around:

- understanding the learner's current level
- finding the actual learning goal
- planning the dependency graph of concepts
- teaching from foundations upward
- checking understanding before moving forward

This is encoded in the teaching skill and the role prompts, and it is intentionally designed to work across different AI environments.

## Example usage

This repository is meant to be used as a reusable prompt/agent library. The same conceptual teaching framework can be plugged into different environments:

- Claude Code via `.claude/`
- GitHub Copilot via `.github/`
- Codex or similar agent runtimes via provider-specific adapters or custom wrappers

In other words, the shared logic stays in one place, while the surrounding runtime integration remains lightweight and portable.

## Design philosophy

This repo keeps the original learning system's philosophy:

- start from unconditional truths
- make the path of discovery explicit
- build understanding through dependencies
- test understanding before moving on
- prefer durable understanding over shallow recall

## Notes

This is a configuration and prompt-oriented repository rather than an application server or package. It is best thought of as a reusable teaching scaffold for AI agents.

If you want to adapt it further, the easiest path is:

1. keep the canonical instructions in `AGENTS.md` and `agents/`
2. add or modify provider adapters in the runtime-specific folders
3. expand `skills/` with new reusable capabilities as your workflow grows

## Credits

Inspired by the teaching-oriented agent work in [amosblomqvist/learn](https://github.com/amosblomqvist/learn), with adaptations for multi-provider agent usage across Claude, Codex, and Copilot-style environments.
