---
title: Issue Templates
parent: GitHub PM Setup
nav_order: 1
---

# Issue Templates
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

Issue templates live in `.github/ISSUE_TEMPLATE/` and use YAML front matter to pre-fill labels, assignees, and titles. The full template suite covers five issue types.

## Template Suite

| Template | File | Label Applied |
|---|---|---|
| Epic | `epic.yml` | `epic` |
| User Story | `user-story.yml` | `user-story` |
| Task | `task.yml` | `task` |
| Bug Report | `bug.yml` | `bug` |
| Feature Request | `feature-request.yml` | `feature-request` |

## Why Labels Instead of Issue Types?

GitHub's native issue types don't filter reliably in Projects v2 views. Label-based filtering (e.g., filtering the Roadmap view by the `epic` label) is the more dependable workaround and is used throughout this setup.

## Size Field & Estimation

Issues use a **Size** custom field (XS → XL) as the estimation proxy, mapped to Fibonacci values:

| Size | Points |
|---|---|
| XS | 1 |
| S | 2 |
| M | 3 |
| L | 5 |
| XL | 8 |

No separate Story Points field is used — Size doubles as the estimation proxy to avoid tool/process bloat.
