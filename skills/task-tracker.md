---
type: skill
id: task-tracker
title: Task Tracker Builder
description: "Building a structured task tracker with dependencies, deadlines, checkpoints, and accountability for a group assignment"
tags: [Production, Planning, Communication]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Task Tracker Builder

This skill turns an agreed project scope and role allocation into a concrete task tracker that a student group can copy into their chosen tool and start working from immediately.

### Core Capability

Given the deliverables and sub-tasks from the scoping stage plus the role allocations from the team-setup stage, this skill assembles a per-task tracker (owner, effort, deadline, dependencies, status, acceptance criteria), a week-by-week timeline, a checkpoint schedule, contingency plans for critical-path tasks, and a communication protocol.

### Method

1. **Task metadata:** For every scoped task, record ID, name, owner, effort estimate, deadline, dependencies, status, and acceptance criteria.
2. **Timeline and checkpoints:** Arrange tasks week by week, flag parallel, sequential, and bottleneck work, and define two to three checkpoints at which peer feedback is run.
3. **Contingency and communication:** Give each critical-path task a realistic contingency plan and set a traffic-light reporting protocol the group will actually maintain.

### Output Structure

A tracker table followed by the timeline, checkpoint schedule, contingencies, and communication protocol. The tracker feeds the progress-tracking and final-assembly stages downstream.
