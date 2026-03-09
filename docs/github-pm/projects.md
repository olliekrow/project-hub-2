---
title: Projects & Structure
parent: GitHub PM Setup
nav_order: 2
---

# Projects & Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Org-Level Architecture

All projects live at the **org level**, not the repo level. This is intentional — repo-level projects can't surface issues from other repos, which makes cross-repo reporting impossible.

The org currently has 17 existing projects (roughly half active, half stale). This documentation covers the new structure being proposed.

---

## The Three Core Projects

### 1. Roadmap

**Purpose:** High-level planning — Epics on a timeline, grouped by milestone.

| Field | Type | Notes |
|---|---|---|
| Status | Select | Backlog, In Progress, Done |
| Milestone | Text | Sprint or release name |
| Start Date | Date | Auto-set on status transition |
| End Date | Date | Auto-set on status transition |
| Size | Select | XS / S / M / L / XL |

**Primary filter:** `label:epic`

---

### 2. Team Planning

**Purpose:** Sprint-level work — Kanban board with iterations.

- Uses GitHub's native **Iterations** field for sprint cycles
- Columns: Backlog → In Progress → In Review → Done
- Filtered to active User Stories and Tasks

---

### 3. Bug Tracker

**Purpose:** Dedicated bug triage and resolution tracking.

- Filtered to `label:bug`
- Priority field: P0 / P1 / P2 / P3
- Linked to Roadmap Epics where applicable

---

## Custom Fields

| Field | Type | Used In |
|---|---|---|
| Start Date | Date | Roadmap, Team Planning |
| End Date | Date | Roadmap |
| Size | Select | All projects |
| Milestone | Text | Roadmap |
| Priority | Select | Bug Tracker |
| Iteration | Iteration | Team Planning |
