---
title: Automation & Workflows
parent: GitHub PM Setup
nav_order: 3
---

# Automation & Workflows
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Date Auto-Population

A GitHub Action (`set-dates.yml`) automatically sets **Start Date** and **End Date** on a project item when its status changes.

### Trigger

The workflow fires on the `projects_v2_item.edited` event — specifically when the `Status` field changes.

### Logic

| Status Change | Action |
|---|---|
| → In Progress | Sets `Start Date` to today |
| → Done | Sets `End Date` to today |

### Setup Requirements

To complete this workflow, you need the field IDs for `Start Date` and `End Date` from the GraphQL API:

```graphql
query {
  organization(login: "olliekrow") {
    projectV2(number: YOUR_PROJECT_NUMBER) {
      fields(first: 20) {
        nodes {
          ... on ProjectV2Field {
            id
            name
          }
          ... on ProjectV2SingleSelectField {
            id
            name
          }
        }
      }
    }
  }
}
```

Run this in the [GitHub GraphQL Explorer](https://docs.github.com/en/graphql/overview/explorer) and copy the `id` values for `Start Date` and `End Date` into your workflow secrets or hardcoded into `set-dates.yml`.

{: .warning }
Field IDs are project-specific. You'll need to re-query if you recreate a project.

---

## Status

| Workflow | Status |
|---|---|
| `set-dates.yml` | 🟡 In Progress — field IDs needed |
| Label sync | 🔴 Planned |
| Stale issue closer | 🔴 Planned |
