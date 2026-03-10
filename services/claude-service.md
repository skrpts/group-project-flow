---
type: service
id: claude-service
title: Claude Service
description: "Anthropic Claude integration for group project coordination, providing task analysis, feedback generation, and document assembly checks"
tags: [Production, Tested]
connections:
  - target: anthropic-claude
    type: runs_on
metadata:
  provider: "anthropic"
  model: "claude-sonnet"
  context_window: 200000
---

## Claude Service — Group Project Flow

This service node defines how the Group Project Flow uses Anthropic Claude for group assignment coordination.

### Usage Within This Skrpt

Claude serves as the coordination intelligence for all stages of the group project workflow:

- **Project Scoping:** Analysing assignment briefs, identifying deliverables and hidden requirements, producing milestone schedules. Requires understanding of academic assignment conventions and realistic effort estimation.
- **Role Allocation:** Matching team member profiles to task requirements, calculating equitable distributions, and drafting team charters. Requires reasoning about fairness, skill alignment, and workload balancing.
- **Task Tracking:** Creating structured task trackers with dependencies, deadlines, and contingency plans. Benefits from Claude's ability to map dependencies and identify critical paths.
- **Peer Feedback:** Generating constructive, specific feedback based on contribution data. Requires careful calibration of tone — honest but supportive, specific but not punitive.
- **Final Assembly:** Reviewing assembled documents for consistency, quality, and completeness. The most token-intensive stage, as it requires processing the complete group document.

### Configuration Notes

- **Temperature:** Keep at 0.3-0.4 for task decomposition and tracking (precision matters). Raise to 0.5-0.6 for feedback generation where nuanced, empathetic language is beneficial.
- **Context window:** The final assembly checker may require the full group document in context. For documents exceeding 10,000 words, consider processing in sections with a cross-reference pass at the end.
- **System prompt:** Each prompt node contains its own complete instructions. No additional system prompt is required.

### Important Limitations

- Claude provides coordination frameworks, not interpersonal mediation. For genuine interpersonal conflicts, the conflict resolution skill produces conversation guides, but the actual conversations must happen between the humans involved.
- Task effort estimates are based on general academic norms. Actual effort depends on individual working speed, familiarity with the topic, and the quality of available sources.
- The peer feedback generator works from the information provided. If team members underreport problems or overstate their contributions, the feedback will reflect that inaccurate input.
