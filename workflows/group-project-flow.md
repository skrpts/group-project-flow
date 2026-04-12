---
type: workflow
id: group-project-flow
title: Group Project Flow
description: "End-to-end workflow for coordinating group assignments from initial brief through role allocation, task tracking, and final assembly"
tags: [Production, Tested, Quality, Planning]
connections:
  - target: task-decomposition
    type: uses
  - target: contribution-balancing
    type: uses
  - target: conflict-resolution
    type: uses
  - target: llm-service
    type: runs_on
  - target: group-work-pedagogy-reference
    type: references
  - target: group-project-survival-guide
    type: references
  - target: project-tracker-template
    type: uses
  - target: team-charter-template
    type: uses
  - target: progress-tracking
    type: uses
  - target: consistency-check
    type: uses
metadata:
  estimated_duration: "30-60 minutes"
  avg_tokens: 12000
  trigger: manual
execution:
  - skill: "task-decomposition"
    step_type: "generation"
  - skill: "contribution-balancing"
    input_from: "task-decomposition"
    step_type: "synthesis"
  - skill: "conflict-resolution"
    input_from: "contribution-balancing"
    step_type: "synthesis"
  - skill: "project-tracker-template"
    input_from: "conflict-resolution"
    step_type: "generation"
  - skill: "team-charter-template"
    input_from: "project-tracker-template"
    step_type: "generation"
  - skill: "progress-tracking"
    input_from: "team-charter-template"
    step_type: "synthesis"
  - skill: "consistency-check"
    input_from: "progress-tracking"
    step_type: "review"
---

## Group Project Flow

This workflow orchestrates the complete lifecycle of a group assignment, from receiving the brief through to submitting a polished, unified piece of work. It is designed for student groups of three to six members who need structured guidance on dividing labour, tracking progress, and maintaining quality across contributions.

### Pipeline Stages

#### Stage 1: Project Scoping
**Node:** `project-scoper`
**Input:** The assignment brief and group details (number of members, deadline, word count)
**Output:** A structured breakdown of deliverables, milestones, and success criteria

The workflow begins by analysing the assignment brief and decomposing it into clear, measurable deliverables. The `task-decomposition` skill powers the analysis, identifying both the obvious deliverables and the hidden work (formatting, referencing, editing, submission logistics) that groups often forget to plan for.

**Error handling:** If the brief is ambiguous about expectations, the scoper flags specific questions the group should ask their lecturer before proceeding. The group should not move to Stage 2 until the scope is confirmed.

#### Stage 2: Team Setup
**Nodes:** `role-allocator` → `team-charter-template`
**Depends on:** Stage 1 output (deliverables list)
**Skills used:** `contribution-balancing`
**Output:** Role assignments and a completed team charter

This stage allocates roles and responsibilities based on team members' strengths, interests, and availability. The `contribution-balancing` skill ensures that work is distributed fairly, accounting for task difficulty, time requirements, and individual circumstances.

The team charter (produced using `team-charter-template`) establishes shared expectations around communication, deadlines, quality standards, and conflict resolution procedures. Groups that skip this step almost invariably encounter problems later.

**Error handling:** If the group has fewer members than the number of major deliverables, the allocator flags overloaded members and suggests strategies for managing the workload. If members have significantly unequal availability, it adjusts allocations accordingly and documents the rationale.

#### Stage 3: Task Tracking Setup
**Node:** `task-tracker-builder`
**Depends on:** Stage 1 (deliverables) and Stage 2 (role assignments)
**Output:** A structured task tracker using `project-tracker-template`

With roles assigned and deliverables defined, this stage creates a detailed task tracker with dependencies, deadlines, and accountability assignments. Each deliverable is broken into sub-tasks with clear owners and due dates.

**Error handling:** If the deadline is too tight for the number of tasks identified, the tracker flags this with specific recommendations: which tasks can be parallelised, which can be simplified, and what the critical path looks like.

#### Stage 4: Progress Check and Feedback
**Node:** `peer-feedback-generator`
**Depends on:** In-progress contributions from team members
**Skills used:** `contribution-balancing`, `conflict-resolution`
**Output:** Constructive peer feedback for each team member

This stage runs at one or more checkpoints during the project (ideally at the midpoint and again before final assembly). It generates structured, constructive feedback on each member's contributions so far. The `conflict-resolution` skill is available if feedback reveals tensions or issues within the group.

**Execution:** This stage is designed to be run multiple times throughout the project. Each run takes the current state of contributions and produces feedback. It can be triggered whenever the group feels a check-in is needed.

**Error handling:** If contributions are significantly unequal at a checkpoint, the feedback generator flags this as a critical issue and invokes the `conflict-resolution` skill to produce specific mediation strategies. It does not ignore imbalances or gloss over them with vague encouragement.

#### Stage 5: Final Assembly and Quality Check
**Node:** `final-assembly-checker`
**Depends on:** All completed individual contributions
**Skills used:** `contribution-balancing`
**Output:** A unified, consistent final submission with a quality report

The final stage assembles all individual contributions into a single coherent document. It checks for stylistic consistency (voice, tense, formatting, referencing), content overlap or gaps, logical flow between sections written by different authors, and overall quality against the assignment criteria.

**Error handling:** If the checker identifies significant inconsistencies, it produces specific revision instructions for each affected section, indicating what needs to change and who is responsible. Critical issues (contradictory content, missing sections, incorrect referencing) are escalated as blockers that must be resolved before submission.

### Parallel Execution Notes
Stages 1 and 2 are sequential. Once Stage 3 is complete, individual work happens in parallel (this is outside the workflow — it is the actual work the students do). Stage 4 can run multiple times during the parallel work phase. Stage 5 runs once all contributions are submitted.

### Quality Gates
- After Stage 1: All team members agree on the deliverables and scope
- After Stage 2: All team members accept their role assignments and sign the team charter
- After Stage 3: Task tracker is reviewed and confirmed by all members
- After Stage 4: Feedback is discussed and any issues are resolved before continuing
- After Stage 5: All members review the assembled document before submission

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.assignment_brief}}` | Yes | The assignment brief | `Write a 3000-word group report on renewable energy policy in the UK.` |
| `{{input.module_name}}` | Yes | The module or course name | `Environmental Policy` |
| `{{input.group_size}}` | Yes | Number of group members | `4` |
| `{{input.deadline}}` | Yes | Submission deadline | `2026-04-30` |
| `{{input.total_scope}}` | Yes | Total word count or scope | `3000 words plus references` |
| `{{input.assessment_criteria}}` | No | Assessment criteria or marking rubric | `Research depth 30%, Analysis 30%, Writing quality 20%, Presentation 20%` |
| `{{input.additional_requirements}}` | No | Any additional requirements | `Harvard referencing, contribution statement required` |
| `{{input.team_members}}` | Yes | Team member profiles (names, strengths, availability) | `Alice (research, 10hrs/wk), Bob (writing, 8hrs/wk), Carol (data, 12hrs/wk), Dan (editing, 6hrs/wk)` |
| `{{input.tools}}` | No | Collaborative tools the group uses | `Google Docs, WhatsApp` |
| `{{input.current_milestone}}` | No | Current project milestone for feedback stage | `midpoint check-in` |
| `{{input.member_contributions}}` | No | Team member contributions for feedback stage | `Alice: literature review complete. Bob: introduction drafted.` |
| `{{input.concerns}}` | No | Specific concerns raised by group members | `Bob missed last two meetings.` |
| `{{input.assembled_document}}` | No | Complete assembled document for final check | `Paste the assembled group document here.` |
| `{{input.referencing_style}}` | No | Required referencing style | `Harvard` |
| `{{input.section_authors}}` | No | Which team member wrote each section | `Introduction: Bob, Literature Review: Alice, Analysis: Carol, Conclusion: Dan` |

## Outputs

| Name | Description |
|------|-------------|
| A structured breakdown of deliverables, milestones, and success criteria | A structured breakdown of deliverables, milestones, and success criteria |
| Role assignments and a completed team charter | Role assignments and a completed team charter |
| A structured task tracker using project-tracker-template | A structured task tracker using project-tracker-template |
| Constructive peer feedback for each team member | Constructive peer feedback for each team member |
| A unified, consistent final submission | A unified, consistent final submission with a quality report |

## Setup

Before running this workflow:

1. No external services required — paste your content directly and provide any supporting context as inputs or source nodes.
2. Review the included documents, assets, or source nodes and customise them to match your team, brand, or domain conventions where needed.
3. No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Most stages work with any capable model; stronger models usually improve synthesis, judgement, and writing quality.
- Extraction, classification, and formatting steps generally run well on smaller or faster models.
- Because there are no vendor-specific integrations here, provider choice is mostly a trade-off between speed, quality, and cost.

## Example Input

To test this workflow immediately after import:

```
Assignment Brief: "Write a 3000-word group report on renewable energy policy in the UK."
Module Name: "Environmental Policy"
Group Size: "4"
Deadline: "2026-04-30"
Total Scope: "3000 words plus references"
Team Members: "Alice (research, 10hrs/wk), Bob (writing, 8hrs/wk), Carol (data, 12hrs/wk), Dan (editing, 6hrs/wk)"
```

