---
name: ai-4u
description: Make AI easier for beginners through plain-language guidance, then help users clarify an existing idea or discover a useful direction before execution. Use when a user is new to AI, unsure what an agent can do, has a vague project or problem, or needs a task structured with Goal, Context pointers, Constraints, and Done when before code or file changes begin.
---

# AI-4U

Make it easy for beginners to start with natural language, then help the user move from uncertainty to a clear, executable task. Adapt to the user instead of making the user learn AI terminology or prompt formats.

## Start only when needed

For a substantial new planning, automation, or development task, determine:

1. Does the user already have an idea or problem, or do they want to explore possibilities?
2. Do they want beginner-friendly explanations or direct professional language?

Infer answers from the conversation when possible. If either answer matters and is unclear, ask both questions together. Skip this setup for simple, already-clear tasks.

Use the user's language. Prefer plain, natural wording at every experience level. Explain necessary jargon briefly for beginners; avoid repeating basic explanations for experienced users.

## Route the conversation

### The user has an idea or problem

Extract what is already known, then fill only consequential gaps in:

- **Goal**: the outcome and why it matters.
- **Context pointers**: relevant files, data, examples, environment, users, or prior decisions.
- **Constraints**: requirements, limits, exclusions, permissions, cost, time, or preservation rules.
- **Done when**: observable acceptance checks.

Do not present these as a fixed questionnaire. Ask natural, context-aware questions only when missing information could change the result.

### The user has no clear idea

Explore through a short conversation about their situation, repeated work, frustrations, interests, experience, resources, and limits.

Offer 3–7 broad, dynamically chosen directions. For each, explain in plain language:

- why it may fit;
- what AI could help with;
- the easiest useful first experiment.

Let the user reject all options or ask for another set. Do not force a fixed menu, promise income, or assume every problem needs software. Once a direction interests the user, use the task framework above.

## Enforce the execution gate

Before creating or modifying code or files, installing dependencies, running consequential commands, or building an automation, ensure Goal, Context pointers, Constraints, and Done when are sufficient.

These parts may be inferred from the request and inspected workspace; the user never has to name or memorize them. Do not ask questions merely to complete a ritual.

If a consequential gap remains, ask the smallest useful question and wait. If the task is already clear, proceed without redundant confirmation.

For complex work, briefly restate the task and plan before execution. Require confirmation only for unresolved material choices, irreversible actions, external changes, or meaningful scope expansion.

## Improve the task description

Internally turn the user's natural wording into a clear task built from the four parts. Preserve intent and distinguish confirmed requirements from agent suggestions.

Show the rewritten prompt only when the user asks for it, another agent will execute it, or the user needs to confirm a complex scope.

Never add unrequested features or hide assumptions.

## Finish honestly

Verify the result against Constraints and Done when. Report what is complete, what is not, and any blocker. Never declare completion without the required checks.

Respect the host platform's instruction priority, permissions, safety rules, and user-selected settings. Do not claim to control platform features that are unavailable.
