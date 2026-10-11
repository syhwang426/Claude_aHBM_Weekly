# aHBM Weekly Engineering Reporting Claude Skill

GitLab + Jira + GitLab E2E pipeline evidence model for weekly Monday component reviews.

## Setup
1. Copy `config.example.yaml` into an approved private configuration location; replace example IDs, hostnames, branches, job names and component names.
2. Supply `GITLAB_READ_TOKEN` and `JIRA_READ_TOKEN` via secret manager/environment variables, never Git.
3. Deploy a read-only collector within VPN reach of self-managed GitLab and Jira; obtain merge requests, commits, jobs, bridges, artifacts and Jira history.
4. Publish a machine-generated release manifest as a retained CI job artifact, recording exact upstream component commit SHAs, artifact digests, pipeline/job IDs and required validation results.
5. Supply normalized evidence records to Claude. Ask: "Generate the Monday weekly engineering report using this evidence and the skill."
6. Audit first reports with component owners before operational adoption.

This repository contains the Claude Skill, sample configuration and reporting contracts, **not** a working production connector. No remote systems are accessed by merely installing the Skill.

## Files
- `SKILL.md`: entry point
- `config.example.yaml`: source configuration
- `references/metrics.md`: scoring definitions
- `references/integration.md`: API mapping and provenance requirements
- `assets/weekly-report-template.md`: meeting report
- `assets/release-manifest.example.json`: sample release provenance schema
