# Product Type Routing

Classify before analyzing. Select one primary type and optionally one secondary type for a hybrid product. State the evidence for the classification and adapt emphasis accordingly.

| Product type | Primary decomposition focus | Evidence that matters most | Typical risks to verify |
|---|---|---|---|
| AIGC creation tool | Input specification, generation stages, user confirmation gates, asset consistency, editing, preview/export, model choice, quality, cost | Complete creation journey, prompt/configuration forms, generated assets and versions, model settings, task states, errors, billing/credits | Claimed completion without assets, style or identity drift, hidden cost, non-idempotent retry, upstream edits not invalidating downstream output |
| General execution agent | Goal intake, planning, tool use, permissions, approvals, external side effects, state machine, retry and rollback, handoff | Full task history, plan or thought summaries exposed to users, tool/result panels, permission prompts, logs, final side effects | Acting without approval, duplicate execution, stale state, unsafe permissions, failure concealed by conversational success |
| Conversational or companion product | Persona, turn-taking, memory, emotional adaptation, safety, boundary setting, long-term context, escalation, retention loops | Longitudinal conversations, memory controls, safety responses, profile/preferences, deletion/privacy settings | False intimacy, memory leakage, unsafe escalation, inconsistent persona, inability to correct or forget |
| Workflow or business SaaS | Job-to-be-done, information architecture, roles, forms, state transitions, collaboration, integrations, auditability | Representative records, role views, workflow statuses, history/audit log, integration settings, errors | Ambiguous ownership, status mismatch, permission gaps, broken handoffs, hard-to-recover edits |
| Knowledge, search, or research product | Query formation, retrieval scope, source ranking, citations, synthesis, uncertainty, freshness | Queries, result pages, source panels, citation links, filters, failure/no-result states | Unsupported claims, stale sources, weak provenance, citation mismatch, unclear confidence |
| Content, community, or marketplace product | Creation/discovery, ranking, trust, moderation, transactions, identity, incentives, lifecycle | Feed/search states, detail pages, creator/seller flows, moderation, payment and dispute states | Dark patterns, ranking opacity, trust failures, moderation gaps, irreversible transactions |

## Classification procedure

1. Identify the user's primary job and the product's observable terminal result.
2. Identify the dominant interaction loop: generate, execute, converse, manage workflow, retrieve knowledge, or transact/discover.
3. Cite the product evidence supporting the type.
4. For a hybrid, name the primary type by the terminal value and the secondary type by the supporting interaction loop.
5. Use the primary type to set report emphasis. Add only the relevant secondary checks; do not merge every checklist indiscriminately.

## If classification is unclear

Do not guess from branding. Ask for the landing state, a representative end-to-end task, or source modules that reveal the primary job. If primary evidence still supports multiple interpretations, label the classification `尚未确认` and produce only a limited evidence inventory.
