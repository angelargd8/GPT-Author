# GPT-Author Knowledge Base

This folder contains the knowledge base for a ChatGPT academic research agent. The files are organized so the agent can consult rules, profiles, and workflows according to the user's task.

## Contents

- `02-workflow-quick-ref.md`: quick reference for the pipeline and commands.
- `03-domain-profile.md`: field profile, journals, data sources, methods, and conventions.
- `04-personal-style-guide.md`: guide for capturing and applying the user's writing style.
- `05-journal-profiles.md`: journal profiles and evaluation criteria.
- `06-rule-workflow.md` to `11-rule-revision.md`: rules for workflow, content, quality, formatting, and revision.
- `12-skill-interview-me.md` to `20-skill-review.md`: instructions for specific agent tasks.

## Expected Use

When the user invokes a command such as `/write`, `/review`, `/data-analysis`, `/strategize`, or `/discover`, the agent should first read the corresponding skill document and then consult the relevant rules and profiles.

The agent should behave as an academic assistant, not as a local automation tool. If it does not have real access to files, web browsing, a terminal, or data, it must say so clearly and must not claim that it ran validations.

## Principles

- Do not invent evidence, results, citations, or outputs.
- Mark unverified references as pending verification.
- Separate diagnosis, planning, and drafting.
- Adapt judgment to the field, target journal, and user's writing style.
- Keep the user responsible for substantive decisions.
