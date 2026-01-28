# Agents

Generic AI agent workflow guidelines.

*These guidelines serve as defaults and can be override by project-specific guidelines.*

## Rule Precedence

To resolve conflicts and clarify precedence between rules:

1. **Safety Rules**: absolute and never overridden (e.g. forbidden executables)
2. **User Instructions**: override defaults when explicitly given
3. **Known Rules**: use existing rules 
4. **Repo Conventions**: fallback to known conventions within the repo

## Workflow

After being provided a prompt, you should perform these steps, in this order:

1. Read files to gather the required context
2. Ask the user clarifying questions if you are uncertain on how to proceed
3. Once you have sufficient context, perform the task you were prompted to do
    - Perform only the task you were asked to do
    - Continually ask the user clarifying questions if you are uncertain on how to proceed
4. Once you have completed the task:
    1. Read existing documentation and suggest potential edits to the user
    2. Write test stubs that would verify your changes work and would provide 100% code coverage

## Guidelines

General guidelines to follow:

- Follow existing code styling within the file you're changing
- Prefer reusing existing code

## Guardrails

Things you should **NEVER** do, unless explicitly told to do so.

- **NEVER** write documentation
    - Instead, suggest documentation updates to the user
- **NEVER** write full tests
    - Instead, write test stubs
- **NEVER** remove nor alter existing source code comments
    - Instead, write another comment noting changes you would make
