# Claude Code Guidelines

## Core Principles

- **Simplicity First:** Make every change as simple as possible. Impact minimal code.
- **No Laziness:** Find root causes. No temporary fixes. Senior developer standards.
- **Minimal Impact:** Changes should only touch what's necessary. Avoid introducing bugs.

## Code Style

- **Primary languages:** TypeScript (primary), Python (secondary), with HTML/CSS for frontend
- Prefer TypeScript for new code unless Python is specifically appropriate (e.g., CoAP, Flask projects)

## Lessons Learned Process

- On any project, if you fail and figure out how to fix it, log a note about lessons learned in a `development.md` file that gets consulted so the mistake is not repeated.
- Review lessons learned at session start for relevant project

## Plan Mode Default

- Enter plan mode for ANY non-trivial task (3+ steps or architectural decisions)
- If something goes sideways, STOP and re-plan immediately - don't keep pushing
- Use plan mode for verification steps, not just building
- Write detailed specs upfront to reduce ambiguity

## Subagent Strategy

- Use subagents liberally to keep main context window clean
- Offload research, exploration, and parallel analysis to subagents
- For complex problems, throw more compute at it via subagents
- One task per subagent for focused execution

## Verification Before Done

- Never mark a non-trivial task complete without proving it works
- Diff behavior between main and your changes when relevant
- Ask yourself: "Would a staff engineer approve this?"
- For non-trivial tasks, run tests, check logs, demonstrate correctness

## Test-Driven Development (When Appropriate)

- At the start of a coding task, consider whether TDD makes sense for this project
- If tests exist or would be valuable, propose: "Should we use TDD? I'll write/update tests first, then implement until they pass."
- Adapt to the stack: pytest (Python), jest/vitest (JS/TS), go test, etc.
- TDD workflow when approved:
  1. Read existing tests or create test file in tests/ (or project convention)
  2. Write failing tests for the feature
  3. Implement minimally to pass tests
  4. Run tests after each change, iterate until green
  5. Document assumptions in code comments
  6. Commit when tests pass
- Skip TDD proposal for: trivial changes, exploratory scripts, demos, or when user declines

## Demand Elegance (Balanced)

- For non-trivial changes: pause and ask "is there a more elegant way?"
- If a fix feels hacky: "Knowing everything I know now, implement the elegant solution"
- Skip this for simple, obvious fixes - don't over-engineer
- Challenge your own work before presenting it

## Task Management

- **Plan First:** Write plan to tasks/todo.md with checkable items
- **Verify Plan:** Check in before starting implementation
- **Track Progress:** Mark items complete as you go
- **Explain Changes:** High-level summary at each step
- **Document Results:** Add review section to tasks/todo.md

## Windows-Specific

- **`start` command:** Always use `start "" "path"` format (empty string for window title, quoted path). Without the empty `""` as first argument, paths with backslashes get mangled.
  - Correct: `start "" "C:\Users\name\file.html"`
  - Wrong: `start C:\Users\name\file.html`

## Networking

- For network-related code (CoAP, MQTT, HTTP servers), always specify the default host and port clearly in output and comments (e.g., "Connects to localhost:5683")

## Educational/Demo Code

- When creating demo scripts or educational examples, always include detailed comments explaining each step
- Provide multiple usage variations (e.g., different ports, protocols, or configurations)

## Session Wrap-up

- Before ending: summarize what we accomplished and list any follow-up tasks I should remember
