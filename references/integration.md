# Source integration and correlation
## Read-only GitLab endpoints
- `GET /api/v4/projects/:id/merge_requests`
- `GET /api/v4/projects/:id/merge_requests/:iid/commits`
- `GET /api/v4/projects/:id/repository/commits`
- `GET /api/v4/projects/:id/repository/compare`
- `GET /api/v4/projects/:id/pipelines`
- `GET /api/v4/projects/:id/pipelines/:pipeline_id/jobs`
- `GET /api/v4/projects/:id/pipelines/:pipeline_id/bridges`
- `GET /api/v4/projects/:id/jobs/:job_id/artifacts/release/manifest.json`
Implement pagination, 429 retry/backoff, timestamp and timezone normalization, read-only credentials and audit logging. Resolve downstream pipelines when parent/multi-project execution is used. Access by pinned pipeline and job IDs, not latest artifact references.

## Jira
Use the instance-supported Jira REST API for issue search, transitions, change history, issue links, owners, scope and acceptance criteria. Configure custom field mappings explicitly rather than guessing. Follow pagination; preserve current status and baseline history.

## Join keys
- Jira issue key in MR title/body/branch or explicit issue link
- exact commit SHA for upstream component
- immutable artifact digest built from commit SHA
- artifact listed in E2E pipeline release manifest
- successfully completed mandatory E2E jobs and accepted release marker

A top-level pipeline SHA may only identify the E2E orchestration repository; do not treat it as a component SHA. Persist the source pipeline/job and artifact URLs with each claim.

## Security and deployment
Host collector inside approved VPN perimeter. Inject GitLab/Jira secrets from secret manager. Use least-privilege read-only API permissions and private evidence storage. Export only approved data to Claude. No automatic write access or deployments are needed for reports.
