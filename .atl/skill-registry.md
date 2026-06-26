# Skill Registry

Generated: 2026-06-25
Project: proyecto

## User Skills (opencode)

| Skill | Trigger Context | Description |
|-------|-----------------|-------------|
| judgment-day | "judgment day", "judgment-day", "review adversarial", "dual review", "doble review", "juzgar", "que lo juzguen" | Parallel adversarial review protocol with two independent blind judge sub-agents |
| skill-creator | Creating new AI agent skills, adding agent instructions, documenting patterns for AI | Creates new AI agent skills following the Agent Skills spec |
| go-testing | Writing Go tests, using teatest, or adding test coverage | Go testing patterns for Gentleman.Dots, including Bubbletea TUI testing |
| issue-creation | Creating a GitHub issue, reporting a bug, or requesting a feature | Issue creation workflow for Agent Teams Lite |
| branch-pr | Creating a pull request, opening a PR, or preparing changes for review | PR creation workflow for Agent Teams Lite |
| find-skills | "how do I do X", "find a skill for X", "is there a skill that can..." | Helps users discover and install agent skills |
| frontend-design | Building web components, pages, artifacts, posters, or applications | Creates distinctive, production-grade frontend interfaces |
| sdd-init | Initializing SDD in a project, "sdd init", "iniciar sdd" | Initialize Spec-Driven Development context in any project |
| sdd-explore | Exploring and investigating ideas before committing to a change | Explore and investigate ideas before committing to a change |
| sdd-propose | Creating or updating a change proposal | Create a change proposal with intent, scope, and approach |
| sdd-spec | Writing or updating specifications | Write specifications with requirements and scenarios |
| sdd-design | Writing or updating technical design | Create technical design document with architecture decisions |
| sdd-tasks | Breaking down a change into implementation tasks | Break down a change into an implementation task checklist |
| sdd-apply | Implementing tasks from a change | Implement tasks from the change, writing actual code |
| sdd-verify | Validating implementation matches specs/design/tasks | Validate that implementation matches specs, design, and tasks |
| sdd-archive | Archiving a completed change | Sync delta specs to main specs and archive a completed change |
| sdd-onboard | Onboarding through the SDD cycle | Guided end-to-end walkthrough of the SDD workflow |

## Project-Level Skills

None detected.

## Project Conventions

No project-level conventions files found (AGENTS.md, CLAUDE.md, .cursorrules, etc.).

## Notes

- SDD skills are auto-loaded by the orchestrator during their respective phases.
- Non-SDD skills with triggers listed above are auto-loaded based on context matching.
- Skill directory: `~/.config/opencode/skills/`
- Engine: opencode
