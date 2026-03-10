---
type: asset
id: project-tracker-template
title: Project Tracker Template
description: "Structured task tracker template for group project management with dependencies, deadlines, and progress monitoring"
tags: [Production, Customer-Facing]
connections:
  - target: group-work-pedagogy-reference
    type: references
metadata:
  format: "template"
  file_type: "markdown"
---

## Group Project Tracker

Use this template to track all tasks, deadlines, and progress for your group assignment. Update it regularly — a tracker that is not kept current is worse than no tracker at all.

---

### Project Overview

| Field | Value |
|-------|-------|
| **Assignment** | {{assignment_name}} |
| **Module** | {{module_name}} |
| **Submission deadline** | {{deadline}} |
| **Group members** | {{member_1}}, {{member_2}}, {{member_3}}, {{member_4}} |
| **Total word count** | {{word_count}} |
| **Referencing style** | {{referencing_style}} |

---

### Milestone Schedule

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| Scope agreement and role allocation | {{date}} | Not started / Complete |
| Research and planning complete | {{date}} | Not started / Complete |
| First drafts submitted internally | {{date}} | Not started / Complete |
| Peer review complete | {{date}} | Not started / Complete |
| Final assembly and editing | {{date}} | Not started / Complete |
| Final proofread | {{date}} | Not started / Complete |
| Submission | {{deadline}} | Not started / Complete |

---

### Task Register

#### Content Tasks

| ID | Task | Owner | Effort (hrs) | Deadline | Dependencies | Status | Notes |
|----|------|-------|-------------|----------|--------------|--------|-------|
| T01 | {{task_name}} | {{owner}} | {{hours}} | {{date}} | — | Not started | |
| T02 | {{task_name}} | {{owner}} | {{hours}} | {{date}} | T01 | Not started | |
| T03 | {{task_name}} | {{owner}} | {{hours}} | {{date}} | — | Not started | |
| T04 | {{task_name}} | {{owner}} | {{hours}} | {{date}} | — | Not started | |
| T05 | {{task_name}} | {{owner}} | {{hours}} | {{date}} | T03, T04 | Not started | |
| T06 | {{task_name}} | {{owner}} | {{hours}} | {{date}} | T02 | Not started | |

#### Coordination Tasks

| ID | Task | Owner | Effort (hrs) | Deadline | Dependencies | Status | Notes |
|----|------|-------|-------------|----------|--------------|--------|-------|
| C01 | Compile reference list | {{owner}} | {{hours}} | {{date}} | T01-T06 | Not started | |
| C02 | Assemble sections into unified document | {{owner}} | {{hours}} | {{date}} | T01-T06 | Not started | |
| C03 | Style and consistency edit | {{owner}} | {{hours}} | {{date}} | C02 | Not started | |
| C04 | Final proofread | {{owner}} | {{hours}} | {{date}} | C03 | Not started | |
| C05 | Format and submit | {{owner}} | {{hours}} | {{date}} | C04 | Not started | |

---

### Workload Summary

| Member | Content Tasks | Coordination Tasks | Total Estimated Hours | % of Project |
|--------|--------------|--------------------|-----------------------|-------------|
| {{member_1}} | T01, T02 | C01 | {{hours}} | {{percentage}} |
| {{member_2}} | T03 | C02, C03 | {{hours}} | {{percentage}} |
| {{member_3}} | T04 | C04 | {{hours}} | {{percentage}} |
| {{member_4}} | T05, T06 | C05 | {{hours}} | {{percentage}} |

---

### Weekly Progress

#### Week 1: {{date_range}}

| Member | Tasks Active | Progress | Status |
|--------|-------------|----------|--------|
| {{member_1}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_2}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_3}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_4}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |

#### Week 2: {{date_range}}

| Member | Tasks Active | Progress | Status |
|--------|-------------|----------|--------|
| {{member_1}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_2}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_3}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_4}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |

#### Week 3: {{date_range}}

| Member | Tasks Active | Progress | Status |
|--------|-------------|----------|--------|
| {{member_1}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_2}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_3}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |
| {{member_4}} | {{tasks}} | {{progress_notes}} | Green / Amber / Red |

---

### Checkpoint Log

#### Checkpoint 1: {{date}}

**Tasks that should be complete:** {{expected_tasks}}
**Tasks actually complete:** {{actual_tasks}}
**Issues identified:** {{issues}}
**Actions agreed:** {{actions}}

#### Checkpoint 2: {{date}}

**Tasks that should be complete:** {{expected_tasks}}
**Tasks actually complete:** {{actual_tasks}}
**Issues identified:** {{issues}}
**Actions agreed:** {{actions}}

---

### Contingency Plans

| Critical Task | Risk | Contingency | Trigger |
|--------------|------|-------------|---------|
| {{task}} | Owner unavailable | {{backup_owner}} takes over; scope reduced to {{reduced_scope}} | If no progress by {{trigger_date}} |
| {{task}} | Insufficient sources found | Broaden search to {{alternative_databases}}; adjust argument scope | If fewer than {{min_sources}} sources by {{trigger_date}} |
| {{task}} | Quality below standard | Peer review with {{reviewer}}; additional revision cycle | If flagged at checkpoint |

---

### Communication Log

| Date | Type | Attendees | Key Decisions | Action Items |
|------|------|-----------|--------------|-------------|
| {{date}} | Meeting / Message | {{attendees}} | {{decisions}} | {{actions}} |
| {{date}} | Meeting / Message | {{attendees}} | {{decisions}} | {{actions}} |
