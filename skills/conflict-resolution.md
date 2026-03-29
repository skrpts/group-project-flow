---
type: skill
id: conflict-resolution
title: Conflict Resolution
description: "Provides structured mediation strategies for common group work conflicts including unequal contribution, disagreements, and communication breakdowns"
tags: [Production, Tested, communication:team, planning:team]
connections:
  - target: llm-service
    type: runs_on
  - target: group-work-pedagogy-reference
    type: references
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Conflict Resolution

This skill provides structured approaches to resolving the conflicts that commonly arise in student group work. It is not a replacement for human conversation — it is a preparation tool that helps groups approach difficult discussions productively.

### Core Capabilities

**Conflict Diagnosis:** Given a description of a group tension or dispute, this skill identifies the type of conflict and its likely root causes. It classifies conflicts into four categories:

1. **Task conflict** — Disagreements about the work itself (what the assignment requires, how to approach a problem, what standard of quality to aim for). These are often productive if managed well.
2. **Process conflict** — Disagreements about how the work should be done (who does what, what tools to use, how to communicate). These are common and usually resolvable with clear agreements.
3. **Contribution conflict** — One or more members are not contributing fairly. This is the most common source of resentment in group work and requires direct, documented intervention.
4. **Relational conflict** — Interpersonal friction that is not directly about the work. These are the hardest to manage and may require external support (tutor, module leader).

**Mediation Scripting:** For each conflict type, this skill produces a structured conversation guide. The guide includes: how to raise the issue without accusation (using "I" statements and specific observations), questions to understand the other person's perspective, a framework for negotiating a resolution, and concrete next steps with accountability measures.

**Escalation Assessment:** Not all conflicts can be resolved within the group. This skill assesses whether a conflict has escalated beyond the group's capacity to manage it and recommends appropriate escalation paths: involving the module tutor, requesting mediation from student services, or formally documenting the issue for the assessment.

**Prevention Strategies:** The skill also operates proactively. Given a team charter and project plan, it identifies likely friction points and recommends preventive measures. Common preventive actions include: establishing communication norms early, setting intermediate deadlines with check-ins, agreeing on quality standards before anyone starts writing, and creating a clear process for raising concerns.

**Contribution Recovery Plans:** When a member has fallen behind, the skill produces a realistic recovery plan. This is not about punishment — it is about getting the project back on track. The plan includes: a frank conversation framework, adjusted task assignments, a compressed timeline with check-ins, and contingency arrangements in case recovery is not possible.

### Constraints

- This skill does not take sides. It provides frameworks for productive conversation, not judgements about who is right.
- It acknowledges that some group conflicts have legitimate external causes (illness, family emergencies, mental health difficulties). Recovery plans accommodate these realities.
- It does not produce formal complaints or academic misconduct reports. If a situation requires formal intervention, the skill advises the group on the appropriate institutional process.
- The skill encourages direct communication first. Going straight to the tutor without attempting to resolve the issue within the group is not recommended unless there are safety concerns or the conflict involves harassment.

### Output Format

Conflict resolution guidance is returned as:
- **Conflict type:** Classification and root cause analysis
- **Conversation guide:** Step-by-step script for raising and discussing the issue
- **Proposed resolution:** Concrete actions, owners, and deadlines
- **Escalation recommendation:** Whether and how to involve external parties
- **Prevention notes:** How to avoid similar issues going forward
