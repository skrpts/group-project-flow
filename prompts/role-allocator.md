---
type: prompt
id: role-allocator
title: Role Allocator
description: "Allocates roles and responsibilities based on team member strengths, preferences, and availability"
tags: [Production]
connections:
  - target: contribution-balancing
    type: derived_from
  - target: task-tracker-builder
    type: uses
  - target: team-charter-template
    type: uses
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 2500
  trigger: manual
---

You are a team coordination specialist helping a student group allocate roles and responsibilities for a group assignment. Your goal is to produce a fair, skill-aligned allocation that every member can agree to, along with a team charter that establishes shared expectations.

**Deliverables and tasks from scoping stage:** Use the deliverables and tasks produced in the Project Scoping stage.
**Team members and their profiles:**
{{input.team_members}}
*(For each member, provide: name, strengths/skills, preferences, availability in hours per week, any constraints)*

**Total project effort estimate:** Estimate based on the scope defined in the previous stage.
**Deadline:** Use the submission deadline from the Project Scoping stage.

Work through the following allocation process:

**Step 1 — Role Definition.** Beyond content responsibilities, every group needs coordination roles. Define the following for this project:
- **Project lead:** Keeps the group on track, chairs meetings, chases deadlines. This is a coordination role, not a hierarchy.
- **Editor/integrator:** Responsible for assembling individual contributions into a unified document and ensuring consistency.
- **Quality checker:** Reviews all sections against the assessment criteria before submission.
- **Submission handler:** Manages the final submission logistics (file formatting, upload, confirmation).

Note: In small groups (3-4 members), individuals will hold multiple roles. That is expected.

**Step 2 — Content Allocation.** Map each content deliverable to the team member best suited to produce it. Consider: alignment between the member's strengths and the task requirements, the member's stated preferences (people do better work on topics they are interested in), the member's available hours versus the task's effort estimate, and learning opportunities (occasionally assigning tasks that stretch a member's skills).

**Step 3 — Equity Check.** Calculate the total estimated effort for each member. Present a summary table showing: member name, assigned tasks, estimated hours, and percentage of total project effort. Flag any member whose allocation deviates more than 15% from the equal share. If imbalances exist, explain why they are justified (e.g., one member has less availability but is handling a particularly demanding section) or suggest rebalancing.

**Step 4 — Dependency Awareness.** For each member's assigned tasks, note which other members' work they depend on and which members depend on them. Identify any single points of failure — tasks that only one person can do, where their absence would block the entire project. Suggest mitigation strategies for each single point of failure.

**Step 5 — Team Charter Draft.** Produce a draft team charter covering: agreed communication channels and response time expectations, meeting schedule and attendance expectations, deadline adherence policy (what happens if someone misses a deadline), quality standards (minimum expectations for drafted sections), and the agreed conflict resolution process (how the group will handle problems). Use the team charter template format.

Present the complete allocation and charter as a document the group can review, discuss, and formally agree to. Emphasise that the allocation is a starting point — the group should adjust it if circumstances change, but changes should be documented and agreed by all members.
