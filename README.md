# Superpowers — Antigravity 2.0 Edition

Superpowers is a complete software development methodology for your coding agents, built on top of composable skills that trigger automatically. Your agent just has Superpowers.

## How it works

It starts from the moment you fire up your coding agent. As soon as it sees that you're building something, it *doesn't* just jump into trying to write code. Instead, it steps back and asks you what you're really trying to do.

Once it's teased a spec out of the conversation, it shows it to you in chunks short enough to actually read and digest.

After you've signed off on the design, your agent puts together an implementation plan that's clear enough for an enthusiastic junior engineer with poor taste, no judgement, no project context, and an aversion to testing to follow. It emphasizes true red/green TDD, YAGNI (You Aren't Gonna Need It), and DRY.

Next up, once you say "go", it launches a *subagent-driven-development* process, having agents work through each engineering task, inspecting and reviewing their work, and continuing forward. It's not uncommon for agents to work autonomously for a couple hours at a time without deviating from the plan you put together.

There's a bunch more to it, but that's the core of the system. And because the skills trigger automatically, you don't need to do anything special. Your coding agent just has Superpowers.

## Sponsorship

If Superpowers has helped you do stuff that makes money and you are so inclined, I'd greatly appreciate it if you'd consider [sponsoring the original project's opensource work](https://github.com/sponsors/obra).

## Installation

### macOS / Linux

* **Global plugin** (available in all projects):

```bash
git clone https://github.com/roundpilot/superpowers ~/.gemini/config/plugins/superpowers
```

* **Workspace plugin** (project-level only):

```bash
git clone https://github.com/roundpilot/superpowers .agents/plugins/superpowers
```

* **Update later:**

```bash
cd ~/.gemini/config/plugins/superpowers && git pull
```

### Windows (PowerShell)

* **Global plugin** (available in all projects):

```powershell
git clone https://github.com/roundpilot/superpowers "$env:USERPROFILE\.gemini\config\plugins\superpowers"
```

* **Workspace plugin** (project-level only):

```powershell
git clone https://github.com/roundpilot/superpowers .agents\plugins\superpowers
```

* **Update later:**

```powershell
cd "$env:USERPROFILE\.gemini\config\plugins\superpowers"; git pull
```

### Windows (WSL)

If you run Antigravity inside WSL, use the Linux paths above.

If you run the **Windows Antigravity IDE** but your workspace is in **WSL**, the plugin scope determines the location:

* **Global plugin** (installed on Windows side):

```bash
git clone https://github.com/roundpilot/superpowers /mnt/c/Users/$USER/.gemini/config/plugins/superpowers
```

* **Workspace plugin** (inside your WSL workspace):

```bash
git clone https://github.com/roundpilot/superpowers /path/to/your/wsl/project/.agents/plugins/superpowers
```

### Verify Installation

1. Start a new Antigravity session
2. Say "Let's make a react todo list"
3. The brainstorming skill should trigger automatically

## The Basic Workflow

1. **brainstorming** - Activates before writing code. Refines rough ideas through questions, explores alternatives, presents design in sections for validation. Saves design document.
2. **using-git-worktrees** - Activates after design approval. Creates isolated workspace via `invoke_subagent` with `Workspace: "branch"`, runs project setup, verifies clean test baseline.
3. **writing-plans** - Activates with approved design. Breaks work into bite-sized tasks (2-5 minutes each). Every task has exact file paths, complete code, verification steps.
4. **subagent-driven-development** - Activates with plan. Uses `define_subagent` to set up implementer, spec-reviewer, and code-reviewer types, then dispatches fresh subagent per task with two-stage review.
5. **test-driven-development** - Activates during implementation. Enforces RED-GREEN-REFACTOR: write failing test, watch it fail, write minimal code, watch it pass, commit. Deletes code written before tests.
6. **requesting-code-review** - Activates between tasks. Reviews against plan, reports issues by severity. Critical issues block progress.
7. **finishing-a-development-branch** - Activates when tasks complete. Verifies tests, presents options (merge/PR/keep/discard) via `ask_question`, cleans up workspace.

**The agent checks for relevant skills before any task.** Mandatory workflows, not suggestions.

## What's Inside

### Skills Library

**Testing**

* **test-driven-development** - RED-GREEN-REFACTOR cycle (includes testing anti-patterns reference)

**Debugging**

* **systematic-debugging** - 4-phase root cause process (includes root-cause-tracing, defense-in-depth, condition-based-waiting techniques)
* **verification-before-completion** - Ensure it's actually fixed

**Collaboration**

* **brainstorming** - Socratic design refinement
* **writing-plans** - Detailed implementation plans
* **dispatching-parallel-agents** - Concurrent subagent workflows via `invoke_subagent`
* **requesting-code-review** - Pre-review checklist
* **receiving-code-review** - Responding to feedback
* **using-git-worktrees** - Workspace isolation via native `Workspace: "branch"`
* **finishing-a-development-branch** - Merge/PR decision workflow
* **subagent-driven-development** - Fast iteration with two-stage review (spec compliance, then code quality)

**Meta**

* **writing-skills** - Create new skills following best practices (includes testing methodology)
* **using-superpowers** - Introduction to the skills system

## Philosophy

* **Test-Driven Development** - Write tests first, always
* **Systematic over ad-hoc** - Process over guessing
* **Complexity reduction** - Simplicity as primary goal
* **Evidence over claims** - Verify before declaring success

Read [the original release announcement](https://blog.fsck.com/2025/10/09/superpowers/).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines, PR requirements, and quality standards.

## License

MIT License - see LICENSE file for details

## Community

Superpowers is built by [Jesse Vincent](https://blog.fsck.com) and the rest of the folks at [Prime Radiant](https://primeradiant.com).

* **Discord**: [Join us](https://discord.gg/35wsABTejz) for community support, questions, and sharing what you're building with Superpowers
* **Issues**: https://github.com/obra/superpowers/issues
* **Release announcements**: [Sign up](https://primeradiant.com/superpowers/) to get notified about new versions
