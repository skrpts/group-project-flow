---
type: skill
id: task-decomposition
title: Task Decomposition
description: "Breaks complex group assignments into manageable, assignable tasks with clear dependencies, effort estimates, and acceptance criteria"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
  - target: group-work-pedagogy-reference
    type: references
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Task Decomposition

This skill decomposes group assignment briefs into structured, manageable tasks suitable for distribution among team members. It goes beyond obvious content divisions to identify the full scope of work required for a successful group submission.

### Core Capabilities

**Brief Analysis:** Given an assignment brief, this skill identifies all explicit requirements (word count, structure, topics to cover, referencing style, submission format) and implicit requirements (consistency editing, formatting, proofreading, submission logistics, contingency planning). Many groups fail because they plan only for the content creation and ignore the coordination overhead.

**Work Breakdown Structure:** The skill produces a hierarchical task breakdown. Top-level items are major deliverables (e.g., "Literature Review Section," "Data Analysis," "Presentation Slides"). Each deliverable is decomposed into sub-tasks (e.g., "Identify 10 sources," "Draft 800 words," "Create three figures"). Sub-tasks are sized to be completable by one person in one to three working sessions.

**Dependency Mapping:** Tasks are not independent. The introduction cannot be finalised until the body sections are complete. The reference list depends on all sections being written. This skill maps dependencies explicitly, distinguishing between: hard dependencies (Task B cannot start until Task A is finished), soft dependencies (Task B is easier if Task A is done first, but can proceed in parallel), and coordination points (moments where the group must synchronise).

**Effort Estimation:** Each task receives an effort estimate calibrated to the academic level. Estimates account for: research time (finding and reading sources), drafting time (producing the initial text), revision time (improving the draft), and coordination time (meetings, communication, integration). The skill flags tasks that are disproportionately large and suggests splitting them.

**Hidden Work Identification:** Groups consistently underestimate the following categories of work, and this skill ensures they are captured:
- Formatting and style consistency across sections
- Reference list compilation and cross-checking
- Creating the submission package (cover page, appendices, file naming)
- Internal review and feedback cycles
- Contingency buffer for late contributions or quality issues
- Meeting preparation and minute-taking

### Constraints

- Task granularity is calibrated to the project size. A 2,000-word group essay does not need the same decomposition depth as a 10,000-word group report.
- Effort estimates are ranges, not precise figures. Academic work is inherently variable.
- The skill does not assign tasks to people — that is the `contribution-balancing` skill's responsibility. It produces an assignable task list.
- Dependencies are based on logical necessity, not preference. The skill will not create artificial sequential dependencies that prevent parallel work.

### Output Format

The decomposition is returned as a structured task list:

- **Deliverable name**
  - **Sub-task:** Description, effort estimate (hours), dependencies, acceptance criteria
  - **Sub-task:** Description, effort estimate (hours), dependencies, acceptance criteria
- **Hidden work tasks** (listed separately to ensure visibility)
- **Critical path:** The longest chain of dependent tasks, determining the minimum project duration
- **Parallelisation opportunities:** Which tasks can be done simultaneously
