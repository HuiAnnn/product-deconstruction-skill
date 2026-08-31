# Product Deconstruction Skill

An evidence-first Codex skill for deconstructing software and AI products from primary product evidence.

The skill first classifies the product type, checks whether the available evidence is sufficient, and then analyzes the product across four layers:

1. User layer
2. Technical layer
3. Model layer
4. Data layer

The final deliverable is a standalone, traceable HTML report.

## Features

- Adapts the analysis focus to AIGC tools, execution agents, conversational products, workflow SaaS, knowledge products, and other product types
- Requires primary evidence such as complete screenshots, accessible product pages, source code, recordings, logs, or exported histories
- Stops or limits the analysis when the evidence is incomplete
- Separates direct facts, reasonable inferences, proposed improvements, and unknowns
- Tracks findings back to stable evidence IDs
- Produces a responsive standalone HTML report
- Preserves conflicts among interface copy, task state, assets, logs, and code instead of silently resolving them

## Repository Structure

```text
product-deconstruction-skill/
├── README.md
└── product-deconstruction/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── evidence-protocol.md
        ├── product-types.md
        ├── layer-playbook.md
        └── html-deliverable.md
```

## Evidence Requirements

Provide at least one primary evidence source:

- Complete or chronological product screenshots
- An accessible product URL
- Original source code or a relevant repository
- Screen recordings, task logs, exported conversations, or generated asset histories

Marketing copy, product descriptions, memory, and industry conventions do not replace primary product evidence.

## Installation

Use the repository's **Code** button on GitHub to copy its clone URL, then clone it with Git or GitHub Desktop.

Copy the skill directory into your personal Codex skills directory:

```bash
cp -R product-deconstruction ~/.codex/skills/
```

Restart Codex if the skill does not appear immediately.

## Usage

Example request:

> Use the product-deconstruction skill to analyze this product. I have provided chronological screenshots and the source repository. Analyze the user, technical, model, and data layers and deliver the result as a standalone HTML file.

The skill can also be invoked naturally in Chinese:

> 使用 product-deconstruction 拆解这个产品。这是完整截图和源代码，请按用户层、技术层、模型层、数据层分析，最终输出 HTML 文件。

## Output

The generated HTML report includes:

- Product type and evidence-gate result
- Evidence inventory and coverage gaps
- User journey, decisions, emotions, and friction
- Technical modules, agents, tools, states, errors, and retries
- Model responsibilities, constraints, validation, cost, and fallback behavior
- Data entities, context boundaries, producer-consumer relationships, versions, and lineage
- Cross-layer flows, risks, opportunities, and traceability tables

## Safety and Evidence Rules

- Use read-only inspection by default
- Do not expose credentials, tokens, cookies, browser storage, or unrelated personal data
- Do not invent hidden prompts, hidden reasoning, official tool names, model names, or architecture
- Treat conversational completion claims as unverified until the corresponding state or asset exists
- Mark unsupported behavior as unknown rather than filling gaps with product conventions

## License

No open-source license has been selected yet. The repository owner should add a license before inviting third-party reuse.
