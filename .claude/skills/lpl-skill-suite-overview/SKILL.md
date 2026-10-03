---
name: lpl-skill-suite-overview
description: "Index and reference docs for the 12-skill AWS + agentic AI suite (from lpl-hackathon-team-21). Use when choosing which skill applies to a task, or when you need the full combined spec, the UX research behind it, or a worked example of how the skills were applied to a real app."
---

# AWS & Agentic AI skill suite (overview)

Source: https://github.com/tysons0/lpl-hackathon-team-21 (`skills/` and `docs/skills-applied.md`).

| # | Skill | Use it for |
| --- | --- | --- |
| 01 | `behavioral-intake-crs` | Conversational intake, PII screening, risk scoring |
| 02 | `agentic-rag-kg-retrieval` | Grounded retrieval over a fixed inventory |
| 03 | `mcdm-ahp-scoring-engine` | Weighted multi-criteria ranking (AHP) |
| 04 | `explainable-match-generator` | Explaining why a result was recommended |
| 05 | `crm-sync-scheduling-agent` | Booking/scheduling and CRM sync |
| 06 | `portfolio-opt-harmonizer` | Portfolio optimization (finance only) |
| 07 | `aws-agentic-ai-toolset-setup` | Bedrock Agents, Action Groups, Knowledge Bases, Guardrails |
| 08 | `aws-cdk-foundation-bootstrap` | Base infra: CDK, KMS, IAM, VPC |
| 09 | `aws-serverless-microservice-deploy` | Lambda/API backends |
| 10 | `aws-event-driven-pipeline-orchestration` | EventBridge, SQS, Step Functions |
| 11 | `aws-containerized-batch-compute` | ECS Fargate / AWS Batch jobs |
| 12 | `aws-observability-guardrails-ops` | Metrics, alarms, budgets |

Related: `aws-agent-toolkit-setup` sets up AWS CLI credentials and the AWS MCP server for the coding agent.

## Reference files in this folder

- `aws-infrastructure-and-agentic-ai-skills.md` - master document combining all 12 skills
- `coding-agent-skills-aws-python.md` - full Python/CDK spec for the suite
- `lpl-financial-ux-matching-analysis.md` - UX research the suite was derived from
- `skills-applied.md` - worked example: how each skill mapped onto the Advisor Match app (including which were skipped and why)

## Applying these to Seagrass (sea drone control UI)

Skills 01-06 are written for a wealth-management matching domain; borrow their patterns (PII screening, grounded retrieval, weighted ranking, explanations) rather than their finance specifics. Skills 07-12 are general AWS patterns and map directly onto a backend for this site, e.g. drone telemetry ingest (09, 10), imagery processing (11), an AI assistant for operators (07), and monitoring (12). As in `skills-applied.md`, skip a skill when it does not fit and say why.
