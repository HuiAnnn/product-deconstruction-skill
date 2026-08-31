# HTML Deliverable Contract

Create one standalone, readable, responsive HTML file. Save it in the user's workspace or another durable writable location, never inside this reusable skill unless the user explicitly asks to modify the skill.

## Required sections

1. Report title, inspected scope, date/build when known, product type, and evidence-gate result
2. Executive summary with the most important verified findings, risks, and opportunities
3. Evidence inventory, coverage matrix, access limitations, and unresolved gaps
4. User layer: personas/jobs, chronological journey, decisions, emotions, pain points, normal/correction/failure paths
5. Technical layer: modules or agents, tools, state machine, permissions, failures, retries, and observable architecture
6. Model layer: model responsibilities, inputs/outputs, routing or fixed selection, constraints, validation, safety, latency/cost, and unknowns
7. Data layer: entities, context boundaries, producer-consumer table, versioning, references, lineage, privacy, and consistency
8. Cross-layer end-to-end flow linking user action to technical, model/tool, data, and visible result
9. Current behavior versus inferred implementation versus recommended design
10. Risks, product opportunities, and prioritized next validation actions
11. Finding-to-evidence traceability table
12. Facts, inferences, recommendations, contradictions, and unknowns register

If a required section lacks evidence, keep the section and state `尚未确认`, what was inspected, and what evidence is needed.

## Evidence presentation

- Give each finding a stable ID such as `F-001` and cite evidence IDs such as `E-001`.
- Include a visible legend for `页面/代码事实`, `合理推断`, `建议设计`, and `尚未确认`.
- Use exact UI labels or short excerpts where needed; avoid long copyrighted quotations.
- Link local code evidence with absolute clickable paths and line numbers when available.
- Thumbnail screenshots only when useful; link to or identify the original filename and screenshot number.

## Visual design

- Use semantic HTML, self-contained CSS, strong contrast, readable typography, sticky or compact navigation, and responsive tables/cards.
- Do not imitate a particular product's brand unless requested.
- Use visualizations only when they clarify relationships: swimlanes for journeys, state diagrams for lifecycle, sequence diagrams for handoffs, architecture diagrams for components, and ER diagrams for data.
- Every diagram node or edge representing a claim must include a finding/evidence reference or connect to a nearby keyed explanation.
- If Mermaid is used, provide a visible fallback containing the diagram source or a text/table equivalent so the report remains useful offline.

## Validation checklist

Before delivery:

- Confirm the file opens as HTML and has one `html`, `head`, `title`, and `body` structure.
- Check all required sections and the evidence legend are present.
- Check evidence and finding IDs resolve consistently and no placeholder text remains.
- Check tables and diagrams at desktop and narrow viewport widths when a browser is available.
- Check Mermaid or other scripts for visible errors; keep a fallback if remote dependencies fail.
- Check that facts, inferences, recommendations, and unknowns are visually distinct.
- Check that sensitive information and unrelated personal data are absent.
- Check the report does not imply inspection beyond the declared scope.

Return the absolute clickable path to the HTML file and briefly state the evidence scope, gate result, and largest remaining gap.
