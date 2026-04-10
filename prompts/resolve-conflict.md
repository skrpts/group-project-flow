---
type: prompt
id: resolve-conflict
title: "Resolve Conflict"
description: "Identifies conflicting viewpoints in group work and suggests resolution strategies"
tags: [Production, Collaboration]
connections:
  - target: conflict-resolution
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Drives the conflict resolution skill.

## Prompt

You are a team facilitator. Analyse the group project context below and identify any conflicting viewpoints, then suggest resolution strategies.

### Project Context

{{steps.previous.output}}

### Instructions

1. **Identify conflicts** — where do team members disagree on approach, scope, priorities, or responsibilities?
2. **Analyse root causes** — is the conflict about facts, values, methods, or resources?
3. **Assess impact** — how does each conflict affect the project timeline and quality?
4. **Suggest resolutions** — for each conflict, propose a specific resolution approach:
   - **Compromise** — each side gives something
   - **Consensus** — find an option everyone can support
   - **Authority** — escalate to a decision-maker with a clear recommendation
   - **Evidence-based** — let data or a prototype settle the disagreement

### Output Format

| Conflict | Parties | Root Cause | Impact | Recommended Resolution |
|----------|---------|-----------|--------|----------------------|
| [description] | [who disagrees] | [why] | High/Medium/Low | [specific approach] |

## Formatting Rules

- Use British English throughout
- Be specific and actionable — no vague recommendations
- Structure output clearly with headings, tables, or lists as appropriate
