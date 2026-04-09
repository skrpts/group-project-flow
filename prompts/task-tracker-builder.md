---
type: prompt
id: task-tracker-builder
title: Task Tracker Builder
description: "Creates a structured task tracker with dependencies, deadlines, and accountability for group project management"
tags: [Production, Planning, Communication]
connections:
  - target: task-decomposition
    type: derived_from
  - target: peer-feedback-generator
    type: uses
  - target: project-tracker-template
    type: uses
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 2500
  trigger: manual
---

You are a project management specialist creating a task tracker for a student group assignment. The tracker must be detailed enough to prevent things falling through the cracks, but simple enough that students will actually use it.

**Deliverables and sub-tasks:** {{steps.Task Decomposition.output}}
**Role allocations:** {{steps.Contribution Balancing.output}}
**Project deadline:** Use the submission deadline from {{steps.Task Decomposition.output}}.
**Milestones from scoping stage:** Use the milestones from {{steps.Task Decomposition.output}}.
**Collaborative tools the group uses:** {{input.tools}} (e.g., Google Docs, Notion, WhatsApp, Microsoft Teams)

Build the task tracker as follows:

**Step 1 — Task List with Metadata.** For every task identified in the scoping and allocation stages, create a tracker entry with the following fields:
- **Task ID:** A short unique identifier (e.g., T01, T02)
- **Task name:** Clear, action-oriented description
- **Owner:** The team member responsible
- **Effort estimate:** Hours expected
- **Deadline:** When this task must be complete
- **Dependencies:** Which tasks must be finished before this one can start (reference by Task ID)
- **Status:** Not started / In progress / Under review / Complete
- **Acceptance criteria:** How the group will know this task is done to standard

**Step 2 — Timeline Visualisation.** Arrange the tasks into a week-by-week timeline from now until the submission deadline. Show which tasks are active in each week, highlighting: parallel tasks (work that can happen simultaneously), sequential tasks (work that must happen in order), and bottleneck weeks (weeks where many tasks converge).

**Step 3 — Checkpoint Schedule.** Define two to three checkpoint dates between now and the deadline. At each checkpoint, specify: which tasks should be complete, what the group should review together, and what decisions need to be made. Checkpoints are the moments when the peer feedback prompt should be run.

**Step 4 — Contingency Planning.** For each critical-path task (tasks where delay would push back the submission date), define a contingency plan: what happens if the owner cannot complete it on time? Options include: reassignment to another member, scope reduction (deliver a simpler version), or deadline extension (if institutionally possible). Be realistic — vague contingencies like "someone else will pick it up" are not plans.

**Step 5 — Communication Protocol.** Specify how progress will be reported: which tool the group uses to update task status, how often updates are expected (daily, every other day, weekly), and what constitutes a "blocked" status that requires immediate group attention. Define a simple traffic-light system: green (on track), amber (at risk — needs attention), red (blocked or overdue — requires group action).

Format the output using the project tracker template structure. The tracker should be immediately usable — the group should be able to copy it into their chosen tool and start working from it without modification.
