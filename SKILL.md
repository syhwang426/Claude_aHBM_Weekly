---
name: weekly-engineering-achievement-tracker
description: Generate evidence-based Monday engineering progress reports from GitLab, Jira and E2E CI pipelines.
---
# Weekly Engineering Achievement Tracker
Use this skill when asked for weekly release achievement, component progress, blockers, or Monday engineering reviews.

## Workflow
1. Read `config.example.yaml`; substitute approved environment configuration.
2. Collect read-only GitLab merged merge requests, related commits, pipelines, jobs, downstream bridges, and build-manifest artifacts; collect Jira planned issues, change histories, and issue links.
3. Freeze planned deliverable scope at the configured baseline cutoff. Report scope changes separately.
4. Correlate deliverables from Jira keys to MRs/SHAs to built artifact digests to the accepted E2E pipeline manifest and required successful validation jobs.
5. Mark each deliverable Released & Verified, Integrated, Implemented, In Progress, Blocked, or Unverified. Never infer release inclusion from a merged MR or E2E pipeline success alone.
6. Compute metrics using `references/metrics.md`, and render `assets/weekly-report-template.md`.
7. Provide each claim's Jira/MR/commit/pipeline evidence URLs and flag missing permissions, records or provenance. Never invent verification.
8. Summarize last week's work, this week's plan, and dependency requests per component. Prioritize decisions for Monday review.

## Safety
Operate read-only against source services. Never print tokens or confidential payloads. Never rank engineers by commit counts. If sources are unavailable, explicitly label metrics unavailable and provide partial evidence-backed reporting. Meeting notes are context, not independent completion evidence.

## Setup
See README.md and config.example.yaml. This is a Skill plus integration blueprint; live collectors require deployment and credentials in an approved environment.
