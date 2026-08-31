---
name: product-deconstruction
description: Evidence-first deconstruction and reverse analysis of software and AI products from complete screenshots, accessible product pages, source code, recordings, logs, or other primary artifacts. Use when the user asks to 拆解、逆向分析或复盘 a product's user journey, interaction logic, agents, tools, models, architecture, state, or data flow and expects a traceable HTML report. Do not use for opinion-only reviews, market research, or architecture claims unsupported by product evidence.
---

# Product Deconstruction

Produce an evidence-traceable product deconstruction as one standalone HTML file. Identify the product type before choosing emphasis, enforce an evidence gate before analysis, and work in this order: user layer, technical layer, model layer, data layer.

## Required references

Read these files before acting:

1. `references/evidence-protocol.md` for every task. Apply its evidence gate before analysis.
2. `references/product-types.md` to classify the product and select the relevant focus.
3. `references/layer-playbook.md` before analyzing the four layers.
4. `references/html-deliverable.md` before creating the final artifact.

## Operating workflow

1. Establish scope.
   - Identify the product, page or feature boundary, target user, desired depth, and available artifacts.
   - Classify the product as one primary type and, when necessary, one secondary type. Never infer a universal focus for all products.
2. Run the evidence gate.
   - Inventory the supplied screenshots, live pages, source code, recordings, exports, logs, and official documentation.
   - If no primary product evidence is available, stop and request it. Do not begin the deconstruction from a description, memory, marketing copy, or general product knowledge alone.
   - If evidence supports only a partial scope, state that scope and ask for the missing evidence before making claims outside it.
3. Inspect safely and chronologically.
   - Default to read-only inspection. Do not send messages, generate content, publish, buy, delete, overwrite, or otherwise mutate the product unless the user separately authorizes that action.
   - For a live product, inspect visible text, controls, forms, assets, states, errors, history, and previews—not only chat copy.
   - If login, verification, CAPTCHA, or user takeover is required, present the browser to the user and wait.
   - Never inspect or expose passwords, cookies, tokens, browser storage, or unrelated personal data.
4. Build an evidence ledger.
   - Assign stable IDs such as `E-001` to screenshots, quotes, UI labels, code locations, state changes, and errors.
   - Label every conclusion as `页面/代码事实`, `合理推断`, `建议设计`, or `尚未确认`.
   - Treat product or agent claims of completion as claims until the corresponding UI state, asset, output, or code path is verified.
   - Preserve contradictions between chat, UI, state, assets, logs, and code instead of silently choosing one source.
5. Analyze in the mandated order.
   - User layer: goals, journey, decisions, feedback, emotions, friction, recovery, and business gates.
   - Technical layer: modules, workflows, agents, tools, permissions, state machine, failures, retries, and integrations.
   - Model layer: model responsibilities, inputs and outputs, routing, constraints, safety, quality checks, cost, latency, and fallback.
   - Data layer: entities, context boundaries, producers and consumers, references, versions, lineage, retention, privacy, and consistency.
6. Synthesize cross-layer findings.
   - Trace important user actions through UI, orchestration, model/tool execution, state writes, and resulting assets.
   - Separate observed current behavior from inferred implementation and proposed improvements.
   - Record evidence gaps and the next validation action for each material unknown.
7. Deliver and verify.
   - Create one self-contained `.html` file following `references/html-deliverable.md`.
   - Validate that required sections, evidence links, labels, diagrams, responsive layout, and HTML structure work.
   - Return a clickable absolute path and a short statement of scope and unresolved gaps.

## Hard constraints

- Do not save product-specific names, screenshots, URLs, findings, or proprietary details inside this reusable skill.
- Do not fabricate hidden prompts, hidden reasoning, official API names, model names, tool calls, or architecture.
- Use semantic placeholders and mark them as inferred when the official field or tool name is not visible.
- Do not collapse inference or recommendations into facts.
- Do not output only prose when the task asks for the completed deconstruction; the final artifact is HTML.
- Do not proceed past the evidence gate merely because a plausible industry pattern is known.

## Completion criteria

The task is complete only when the evidence gate passed for the declared scope, all four layers were addressed or explicitly marked unsupported, cross-layer claims are traceable to evidence IDs, material contradictions and unknowns are visible, and the final HTML file has been checked.
