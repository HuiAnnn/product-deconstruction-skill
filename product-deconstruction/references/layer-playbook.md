# Four-Layer Deconstruction Playbook

Always analyze in this order. Later layers may explain earlier behavior, but should not overwrite what the user actually experienced.

## 1. User layer

Determine:

- Target users, jobs, entry points, and desired outcomes
- End-to-end journey from initial intent to observable result
- User actions, system feedback, decisions, confirmations, and exit points
- Normal, modification/correction, failure, interruption, and recovery paths
- Buttons, forms, cards, previews, history, errors, billing gates, and permission prompts
- Emotional curve: expectations, uncertainty, confidence, frustration, relief, and control
- Friction, misleading completion, visibility of status, reversibility, and accessibility

For each journey node record: user goal, action, interface response, decision condition, next state, failure recovery, emotion, pain point, and evidence IDs.

## 2. Technical layer

Determine only what evidence supports:

- Functional domains, client/server boundaries, orchestration, workers, queues, storage, and integrations
- Agents or modules that actually appear, their trigger, responsibility, input/output contract, and handoff
- Observable tools and side effects; use functional placeholders when official names are absent
- State machine, source of truth, asynchronous execution, cancellation, retry, timeout, and idempotency
- Permissions, approval gates, billing checks, and external effects
- Error propagation and contradictions between conversation, UI state, logs, and assets

Distinguish `当前可见架构`, `推断实现`, and `建议目标架构`. Never present a planned tool call as an executed call without a result or state change.

## 3. Model layer

Determine:

- Which tasks appear to require language, image, video, audio, ranking, embedding, moderation, or deterministic logic
- Model-visible inputs, structured context, upstream artifacts, and runtime results
- Model outputs and how they are validated before becoming product state
- Observable model selection, capability constraints, duration/resolution/context limits, latency, and cost
- Routing, fallback, retry, safety, copyright, and quality evaluation behavior
- Whether user correction causes local regeneration or invalidates downstream work

Do not invent model vendors, versions, routers, hidden reasoning, or prompts. When only one model is visible, do not claim dynamic routing. If a model responsibility is inferred from behavior, state the evidence and uncertainty.

## 4. Data layer

Determine:

- Core entities and relations: user, workspace/project, task, message, configuration, agent/module, asset, version, tool run, confirmation, error, entitlement, and evaluation when present
- Separation among current user input, long-term user information, project global context, upstream outputs, public platform data, and runtime/tool results
- Producers, consumers, read/write timing, ownership, and source of truth for each field
- Stable references between entities and assets, version history, lineage, invalidation, and rollback
- Retention, deletion, privacy, access control, sensitive fields, and audit needs
- Only-write, only-read, duplicated, stale, or conflicting fields

Use semantic names for inferred entities and mark them as a proposed schema. Do not expose credentials or unnecessary personal information.

## Cross-layer synthesis

Trace high-value flows across all four layers:

1. User action and UI event
2. Technical controller or state transition
3. Model/tool decision and execution
4. Data read/write and version impact
5. User-visible result or recovery path

For each major problem, show the user symptom, likely technical/model/data cause, evidence level, risk, and a product opportunity. Preserve alternate explanations when evidence cannot distinguish them.
