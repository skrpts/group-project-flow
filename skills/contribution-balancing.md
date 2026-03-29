---
type: skill
id: contribution-balancing
title: Contribution Balancing
description: "Ensures fair and equitable distribution of work across group members, accounting for skills, availability, and task difficulty"
tags: [Production, Tested, communication:team, planning:team]
connections:
  - target: llm-service
    type: runs_on
  - target: group-work-pedagogy-reference
    type: references
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Contribution Balancing

This skill ensures that group work is distributed fairly among team members. Fairness does not mean identical workloads — it means equitable distribution that accounts for individual circumstances, skills, and the varying difficulty of different tasks.

### Core Capabilities

**Workload Assessment:** Given a task list and team member profiles, this skill calculates the total effort required and determines a fair distribution. It accounts for task difficulty (a literature review section requires different effort from formatting the reference list), skill alignment (assigning research-heavy tasks to strong researchers), and time availability (adjusting for members with competing commitments).

**Skill-Task Matching:** The skill maps team members' stated strengths and preferences against the task requirements. It prioritises assignments where a member's skills align with the task, but it also ensures that no member is permanently assigned only to their comfort zone — group projects are learning opportunities, and some stretch assignments are valuable. The balance between efficiency (play to strengths) and development (try something new) is configurable.

**Equity Monitoring:** At any point during the project, this skill can assess whether contributions remain balanced. It takes the current state of the task tracker and each member's progress, calculates the percentage of total effort each person has contributed, and flags significant imbalances. An imbalance is not automatically a problem — it may reflect agreed-upon adjustments — but it must be visible and documented.

**Redistribution Recommendations:** When a member falls behind, drops out, or encounters unforeseen difficulties, this skill recalculates the distribution. It identifies which incomplete tasks can be reassigned, which members have capacity to absorb additional work, and whether the scope of the project needs to be adjusted. It explicitly avoids dumping extra work on the most reliable members without acknowledgement.

**Fairness Documentation:** For assignments that include a group contribution statement or peer assessment, this skill produces a clear record of who did what. It generates both a factual summary (tasks completed by each member) and an equity assessment (whether the distribution was fair, and any adjustments that were made).

### Constraints

- The skill does not override explicit agreements made by the group. If the team has agreed to an unequal distribution for legitimate reasons (e.g., one member is doing a larger share of a different component), it respects that decision but documents it.
- It treats all members' time as equally valuable. A member who works part-time is not expected to match the hours of a member with no other commitments.
- The skill avoids gender, racial, or personality-based assumptions about who should do which tasks. Allocation is based on stated skills, preferences, and availability — not stereotypes.
- It does not resolve interpersonal conflict directly. When imbalances stem from conflict rather than circumstance, it hands off to the `conflict-resolution` skill.

### Output Format

Balanced allocations are returned as:
- **Member name** → assigned tasks with effort estimates → total estimated hours → percentage of project
- **Equity summary:** Whether the distribution is balanced, and any flags
- **Adjustment log:** Any redistributions from the original plan, with rationale
