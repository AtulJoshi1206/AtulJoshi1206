# Atul Joshi

**AI Engineer & Delivery Lead** · agent systems, reliability and evaluation

I build AI systems that make auditable decisions in production, and I fix the agent frameworks they run on.

My work starts from a concrete constraint: an SLA at risk, a review process that's too slow, financial data nobody trusts an LLM near. It ends as a system where the model reasons and routes, while deterministic layers decide, verify and keep a record.

[Portfolio](https://atuljoshi.netlify.app/) · [LinkedIn](https://www.linkedin.com/in/atul-joshi-54928018a/) · [Email](mailto:atul.joshi1206@gmail.com)

---

## Open-source contributions

I contribute root-cause fixes to the frameworks that teams use to build agents. Each fix:

- names the invariant that broke;
- covers every place that shared the flaw;
- ships with a test that fails before the change and passes after it.

### Google Agent Development Kit (ADK): 8 merged

| Area | What was broken | PR |
| --- | --- | --- |
| Live API | A non-resumable update erased the session-resumption handle, so a reconnect in the middle of a turn lost the live conversation | [#7939](https://github.com/google/adk-python/pull/7939) |
| Workflows | A `ParallelAgent` run as a workflow node passed one sub-agent's branch downstream, so the next step saw only that branch's output | [#7940](https://github.com/google/adk-python/pull/7940) |
| Sessions | Concurrent sessions overwrote each other's shared `app:` and `user:` state on the SQL and Redis backends | [#7942](https://github.com/google/adk-python/pull/7942) |
| MCP tools | Cancelling a run left the in-flight MCP tool call running | [#7199](https://github.com/google/adk-python/pull/7199) |
| A2A | Converting a remote A2A task into an event kept only its last artifact | [#7201](https://github.com/google/adk-python/pull/7201) |
| Instructions | Artifact placeholders inserted a raw `Part` dump instead of the artifact's text | [#7391](https://github.com/google/adk-python/pull/7391) |
| Gemini streaming | With thought summaries on, the thought signature was attached to the summary text instead of its own part | [#7588](https://github.com/google/adk-python/pull/7588) |
| Gemini client | Reused agents failed once their event loop was torn down; the client is now cached per event loop | [#7187](https://github.com/google/adk-python/pull/7187) |

### AWS Powertools for Lambda (Python): 3 merged

| Area | What was broken | PR |
| --- | --- | --- |
| Event handler | Exceptions raised inside `Depends()` dependencies skipped the registered exception handlers | [#8568](https://github.com/aws-powertools/powertools-lambda-python/pull/8568) |
| Idempotency | Idempotent results containing UUIDs, datetimes or enums failed to save after the function had already run | [#8570](https://github.com/aws-powertools/powertools-lambda-python/pull/8570) |
| VPC Lattice | Any request with a query string returned 404 | [#8572](https://github.com/aws-powertools/powertools-lambda-python/pull/8572) |

Also contributing to [AWS Strands Agents](https://github.com/strands-agents/harness-sdk/pulls?q=author%3AAtulJoshi1206), [Google ADK for Go](https://github.com/google/adk-go/issues?q=author%3AAtulJoshi1206) and [Microsoft Agent Framework](https://github.com/microsoft/agent-framework/issues?q=author%3AAtulJoshi1206).

---

## How I work

- **Start from the constraint, not the model.** Scope the problem with the people who own it, agree on what "working" means, then design the system around that.
- **Root cause over symptoms.** Find the invariant that broke, fix every place that shares the flaw, and prove it with a test that fails before the change.
- **Deterministic where it counts.** Let the model reason and route, and make the decision path verifiable and auditable.
- **Own it end to end.** Take work from the problem statement to a shipped, measured outcome, keeping stakeholders and maintainers in the loop.

---

## Selected projects

| Problem | System | Outcome |
| --- | --- | --- |
| Traffic violation review is slow and inconsistent | [GridLock-VioScan](https://github.com/AtulJoshi1206/GridLock-VioScan): YOLOv8 and Gemini Vision detection, automated severity scoring (VSI) and fine-waiver logic | An evidence-backed, auditable violation pipeline |
| SRE teams need to trust AI triage before it touches production | [IncidentOps-Agentic-SRE](https://github.com/AtulJoshi1206/IncidentOps-Agentic-SRE): an OpenEnv benchmark scoring LLM triage, diagnosis and remediation | A measurable trust bar before agentic response ships |
| Finance can't risk LLM hallucination on order-to-cash data | [Dodge-AI-FDE](https://github.com/AtulJoshi1206/Dodge-AI-FDE): SAP order-to-cash data modelled as a graph, with the LLM as a strict router, never a guesser | A zero-hallucination query layer over sensitive financial data |
| Farm operations need decisions committed, not advised | [AI-Autonomous-Farming-Operator](https://github.com/AtulJoshi1206/AI-Autonomous-Farming-Operator): a deterministic safety pipeline with a conversational multi-agent layer in English and Hindi | The system authorizes and verifies real actions, not recommendations |
| Support organizations need SLOs held under load | [supportops-env](https://github.com/AtulJoshi1206/supportops-env): an OpenEnv benchmark where an AI coordinator triages tickets and holds SLOs | A reproducible stress test for agentic support operations |
| Hidden system failures need diagnosis, not dashboards | [sentinel-os-agentic-benchmark](https://github.com/AtulJoshi1206/sentinel-os-agentic-benchmark): a diagnostic-reasoning benchmark with trajectory-based scoring | Quantified recovery efficiency for LLM agents |

---

## Focus areas

- **Agent reliability:** live and streaming sessions, tool and MCP lifecycles, state under concurrency.
- **Evaluating LLM agents:** benchmarks with trajectory-based scoring for operations and incident response.
- **Auditable AI decisions:** deterministic safety layers around model reasoning, with a record of every decision.

**Tools:** Python, TypeScript, C++, FastAPI, React, Node.js, MongoDB, Docker, Google ADK, AWS Lambda, MCP, A2A, Gemini API, YOLOv8

---

Always happy to talk about agent infrastructure, evaluating LLM agents, or turning a messy business process into a reliable AI system. Reach me on [LinkedIn](https://www.linkedin.com/in/atul-joshi-54928018a/) or by [email](mailto:atul.joshi1206@gmail.com).
