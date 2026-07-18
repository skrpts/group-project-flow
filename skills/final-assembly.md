---
type: skill
id: final-assembly
title: Final Assembly Checker
description: "Assembling individually authored sections into one coherent submission and checking it for consistency, completeness, and quality"
tags: [Production, Quality, Planning]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "10-15 minutes"
  avg_tokens: 3500
  trigger: manual
---

## Final Assembly Checker

This skill produces the workflow's final deliverable: a unified, submission-ready group document with an accompanying quality report. It reads across sections written by different authors and checks that the assembled whole reads as though one person wrote it.

### Core Capability

Given the assembled document plus the project scope, role allocations, task tracker, and peer feedback as context, this skill runs structural, consistency, stylistic, citation, quality, and formatting checks, then produces a prioritised issue log and an overall readiness verdict.

### Method

1. **Completeness and consistency:** Confirm all required components are present and check across sections for contradictions, overlap, gaps, and logical flow.
2. **Style, citations, and formatting:** Assess voice, tense, terminology, and heading uniformity; audit in-text citations against the reference list in the required style; review presentation details.
3. **Quality and verdict:** Rate the document against the assessment criteria and give a clear recommendation — ready, ready with minor fixes, or requires significant revision.

### Output Structure

A prioritised issue log (Critical / Important / Minor, each with location, description, fix, and responsible member) followed by an assembly summary and readiness recommendation. This is the last content stage before language polish.
