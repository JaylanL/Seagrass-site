# Seagrass site

React 19 + Vite sea drone control UI (Leaflet map, camera, compass, depth and battery meters), packaged with Electron.

- Dev server: `npm run dev` · Build: `npm run build` · Lint: `npm run lint` · Desktop: `npm run electron:dev`
- Components live in `src/components/`; app shell in `src/App.jsx`.

## Agent skills

Project skills are in `.claude/skills/` and load automatically in Claude Code. Start with `lpl-skill-suite-overview` to pick the right one.

- `aws-agent-toolkit-setup` - connect the coding agent to AWS (CLI, `aws login`, AWS MCP server, toolkit skills)
- SKILL-01..06 (patterns from lpl-hackathon-team-21): `behavioral-intake-crs`, `agentic-rag-kg-retrieval`, `mcdm-ahp-scoring-engine`, `explainable-match-generator`, `crm-sync-scheduling-agent`, `portfolio-opt-harmonizer`
- SKILL-07..12 (AWS): `aws-agentic-ai-toolset-setup`, `aws-cdk-foundation-bootstrap`, `aws-serverless-microservice-deploy`, `aws-event-driven-pipeline-orchestration`, `aws-containerized-batch-compute`, `aws-observability-guardrails-ops`

Before AWS work, check whether one of these skills applies and follow it over general knowledge. Where a skill is written for a different domain (finance), reuse its pattern, not its specifics.

<!-- BEGIN AWS Agent Toolkit rules -->
# AWS Guidance

- Where these AWS rules conflict with the project's own instructions, the
  project's instructions take precedence.
- Prefer the AWS MCP Server for AWS interactions — it provides sandboxed
  execution, observability, and audit logging. If unavailable, use the
  AWS CLI directly.
- Before starting a task, check whether a relevant AWS skill is available.
  Load the skill with `retrieve_skill` and prefer its guidance over
  general knowledge.
- When uncertain about specific AWS details (API parameters, permissions,
  limits, error codes), verify against documentation rather than guessing.
  State uncertainty explicitly if you cannot confirm.
- When creating infrastructure, prefer infrastructure-as-code (AWS CDK or
  CloudFormation) over direct CLI commands.
- When working with infrastructure, follow AWS Well-Architected Framework
  principles.
- Do not use em dashes in AWS resource names or descriptions. Use
  hyphens instead.

## Secret Safety

- MUST load the `aws-secrets-manager` skill first for any secret,
  credential, API key, token, or password task. MUST NOT call
  `secretsmanager get-secret-value` or `batch-get-secret-value`, and MUST
  NOT hit the Secrets Manager Agent daemon directly. MUST use
  `{{resolve:secretsmanager:secret-id:SecretString:json-key}}` with
  `asm-exec` so the secret resolves at runtime without entering context.
<!-- END AWS Agent Toolkit rules -->
