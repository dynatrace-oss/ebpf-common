# AGENTS.md
This file provides guidance for automated agents (e.g., AI assistants, bots, or scripts) interacting with this repository.
## Purpose

The ebpf-common repository contains shared components, helpers, and abstractions used by eBPF-based projects in the Dynatrace Open Source ecosystem. 
Agents should prioritize correctness, safety, and minimal invasiveness when making changes.
## General Guidelines

- Prefer small, focused changes over large refactorings.
- Follow existing code style and structure.
- Do not introduce unnecessary dependencies.

## Repository expectations

- Keep changes simple, explicit, and easy for maintainers to understand.
- Prefer small, reviewable pull requests.
- Preserve required governance files unless the task is explicitly to change the template standard.
- Use placeholder content only where maintainers are expected to replace it after creating a new repository from this template.
- Make ownership, support, and publication expectations explicit.


## Pull request guidance

When preparing a pull request:
- Summarize what changed
- Explain why the change improves the template
- Call out any new maintainer actions required after repository creation
- Keep the scope focused and easy to review

## Testing
- This is not a standalone project. Tested should be projects that uses this project as a git submodule  

## What to avoid

- Large-scale automated refactors
- Style-only changes
- Modifying licensing or legal files
