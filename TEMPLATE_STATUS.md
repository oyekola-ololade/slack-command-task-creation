# Template Status & Verification

**Classification:** Configurable n8n template asset — not a verified production deployment.

The workflow export and documentation are inspectable template evidence. They do not prove a configured production Slack/task-management deployment, SLA, ROI, or client outcome.

## Verification gate
1. Parse/import into a clean current n8n instance.
2. Inspect command parsing, authorization assumptions, task mapping, branches, expressions, and Code nodes.
3. Replace placeholder Slack credentials/signing/webhook values, task-system IDs, URLs, and resource references.
4. Run valid command, invalid command, unauthorized/unknown user, duplicate/replay, malformed-input, and provider-failure cases.
5. Verify command acknowledgement and task creation occur exactly once where intended; record configured test date/result.

## Security
Never commit Slack tokens/signing secrets, private channel/user data, task-system credentials, or production payloads. Use test workspaces/projects and synthetic commands.

## Change record
- **2026-09-03:** Added repository verification/security/status control. No workflow-logic change or runtime pass is implied.
