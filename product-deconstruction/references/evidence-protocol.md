# Evidence Protocol

## 1. Evidence inventory

Record each artifact with an ID, type, source, capture time when known, scope, and access status.

Primary product evidence includes:

- Full or sequential screenshots showing the product state, controls, and results
- An accessible live product page or authenticated session supplied by the user
- Original source code, repository, configuration, schemas, or tests
- Screen recordings, exported conversations, task logs, public-safe traces, or generated assets

Secondary evidence includes official help pages, API documentation, changelogs, and user-provided notes. Secondary evidence may explain a fact but cannot replace direct evidence of the inspected product behavior.

Marketing copy, memory, industry conventions, and assumptions are not operational evidence.

## 2. Mandatory evidence gate

Do not begin substantive analysis unless at least one primary evidence source is available and the intended scope can be tied to it.

Check the following dimensions:

| Dimension | Pass condition |
|---|---|
| Identity and scope | The inspected product, feature, page, version, or build is identifiable. |
| Entry state | The beginning of the target journey or code path is visible. |
| Progression | Enough ordered states exist to explain what happens between entry and result. |
| Decisions | Relevant controls, confirmations, choices, or branching conditions are visible. |
| Result state | The resulting page, asset, status, or code-side outcome is inspectable. |
| Architecture basis | Technical, model, and data claims have code evidence or observable runtime/state evidence. |

Failure and recovery evidence is desirable but not required for the gate. If unavailable, mark those paths as `尚未确认`; do not invent them.

### Gate outcomes

- `PASS`: Evidence supports the requested scope. Continue.
- `LIMITED`: Primary evidence exists but covers only part of the scope. Offer a bounded analysis and request what is missing before broader claims.
- `BLOCKED`: No primary evidence, inaccessible evidence, or evidence too fragmentary to identify an ordered interaction. Stop and request specific artifacts.

Examples of useful requests:

- Full-page screenshots from the first input through the final result, including dialogs and errors
- A product URL with a session the user is prepared to take over when login is required
- The relevant repository or exact source directories
- Exported chat/task history and generated asset history
- Screenshots of model, billing, permissions, state, or history panels needed for the requested layer

## 3. Evidence labels

Use exactly these semantic classes in the report:

- `页面/代码事实`: Directly visible in the product, artifact, source, or verified runtime result.
- `合理推断`: Supported by two or more facts or by one strong fact plus a transparent inference.
- `建议设计`: A proposed improvement or stabilizing rule, not a claim about the inspected product.
- `尚未确认`: Evidence is missing, inaccessible, contradictory, or insufficient.

Every material finding must cite one or more evidence IDs. Recommendations should cite the facts or gaps that motivate them.

## 4. Evidence ledger format

| ID | Source | Location/time | Direct observation | Supports | Limitations |
|---|---|---|---|---|---|
| E-001 | Screenshot/code/live page | Precise filename, URL section, line, or timestamp | Exact visible fact or concise quote | Finding IDs | Cropping, missing state, ambiguity |

For UI evidence, capture visible labels, buttons, cards, assets, statuses, errors, and the screenshot number. For code evidence, cite an absolute file path and line when possible. For a live page, record the visible route or page title without exposing sensitive URL parameters.

## 5. Contradictions and completion claims

- A natural-language statement such as “completed” is not proof of completion.
- Verify the resulting asset exists, the expected state is written, and the interface exposes the corresponding result.
- When chat, canvas, task status, asset history, logs, or code disagree, record all sides as separate facts and create a contradiction finding.
- Do not resolve a contradiction by preference. State the current source-of-truth uncertainty and the next validation step.

## 6. Safe inspection

- Use read-only actions by default: open, scroll, expand, switch views, inspect existing versions, and preview existing assets.
- Do not send, generate, regenerate, publish, delete, purchase, recharge, or overwrite without separate user authorization.
- Avoid secrets and unrelated personal data. Redact sensitive identifiers in evidence excerpts.
- If authentication, verification, or CAPTCHA blocks access, hand control to the user and wait for confirmation.
- When source code is supplied, do not execute unknown destructive scripts. Prefer static inspection and narrowly scoped safe tests.
