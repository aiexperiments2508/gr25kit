# presentation-analysis.md — Phase 1 Analysis

> Produced under `presentation_master_prompt.md` section 28, for the Annual AI Hackathon Final.
> Product **Ledgerline** · team **Deep Thinkers** · 15 minute jury presentation.
>
> Inputs bound to the master prompt's slots: the hackathon brief
> (`01_AI_Root_Cause_Navigator_for_Complex_Systems.docx`), the research deck
> (`research_product_discovery_story.pptx`, evidence only), `prd.md`,
> `architecture-baseline.md` v1.1 as the authoritative architecture, and the shipped code.
>
> **Superseded, do not cite:** `architecture.md`, `workflow-architecture.md` section 6 and
> `project-layout.md` section 6 still record agentic orchestration, MCP and A2A as Not Applicable.
> All three were reversed on 2026-08-27.

---

## A. Core problem

Time is lost assembling and reconciling evidence, not detecting failure. When a payments platform
degrades, every dependent component alerts, usually in reverse dependency order, and the
investigator has to reconstruct which of the now forty broken things broke first.

## B. User and business pain

Persona PER-1, the incident investigator, works across metrics, logs, alerts, deployment history,
tickets and operating rules under time pressure, and loses time to four specific frictions: noise
(duplicate alerts, false positives), time (clock skew, delayed events), context (which deploy,
which dependency) and trust (contradictions, absent evidence).

**Evidence strength, stated plainly.** PER-1 is an unvalidated hypothesis. No SME interview was
conducted (gap G-3), and `interview-log.md` is a log of the engagement owner's own decisions with
eleven of twelve entries reconstructed and paraphrased. It is not voice of customer and must never
be presented as such. The pain statement above is grounded in the brief, which is a stronger source
than the deck for this specific claim.

## C. Research insight

Six mature products already perform AI assisted root cause analysis: Dynatrace, Datadog Bits, New
Relic Autopilot, IBM Instana, ServiceNow ITOM and BigPanda. Alert and telemetry correlation,
dependency traversal and probable cause ranking are therefore **market parity and may not be
presented as innovation**. IBM Instana already shows up to three probable causes and withholds a
result below sufficient confidence, which specifically lowers the novelty of abstention as a
feature and raises it as an execution and measurement problem.

The one hard external statistic in the corpus is RCAEval's 735 failure cases across 15 baselines,
recorded as a benchmark pattern and never as a target. A 2026 study on realistic evaluation finds
simplified benchmarks can overstate state of the art performance on noisy failures, which is the
direct justification for building a noise contract and a hidden answer key.

**Blanket caveat (gap G-9):** no cited source was independently read in this engagement. Every
research claim is attributed, not verified.

## D. White space

Not "nobody does root cause". The gap is trust and evaluability:

1. Support shown without the contradiction beside it.
2. Missing evidence treated as silence rather than as an output.
3. Confidence presented as certainty.
4. A next action that does not discriminate between hypotheses.
5. No objective score against a known correct answer.

**Honesty constraint.** The research itself rates white space strength as medium to high and states
it still needs real customer validation. Anti-goal AG-6 makes claiming market exclusivity, vendor
superiority or regulatory compliance a recorded violation. The deck therefore says the market is
crowded and names the six competitors by name.

## E. Product insight

**Use the least probabilistic method that can reliably solve each part.** Three tiers:
deterministic (schema validation, deduplication, clock skew, scoring, abstention), causal and
statistical (dependency traversal, anomaly strength, temporal precedence, ranking), and bounded
generative (explanation, contradiction wording, next check, follow up questions).

The corollary is the positioning: build a trustworthy investigation layer, not another
observability platform.

## F. Value proposition

For engineers investigating payments incidents: ranked causes with the evidence for and against
each one, the missing evidence named, and an honest decline with a next check when the evidence
does not support a conclusion.

## G. Differentiation

Governed by one rule from `prd.md`: a claim with no observable behaviour and no measure is not a
differentiator.

| Claim | Status |
|---|---|
| Support and contradiction shown together | Qualifies. FR-022, FR-023, EVAL-4 |
| Missing evidence named as an output | Qualifies. FR-024, EVAL-5 |
| Uncertainty without false certainty | Qualifies. FR-025, FR-026, EVAL-3 |
| Next check chosen to discriminate | Qualifies. FR-027, EVAL-6 |
| Ranking moves as evidence arrives | Qualifies. FR-029, EVAL-7 |
| Objective evaluation against hidden ground truth | Qualifies. FR-060, FR-004, EVAL-1, EVAL-9 |
| Domain portability without forking | **Does not qualify.** Designed for, never proven |
| Vendor neutral evidence contract | **Not a differentiator.** Positioning language only |

## H. Strongest MVP proof point

Scored against a hidden answer key over the 70 incident open split: **92.3% top one accuracy over
the 74.3% of incidents the system chose to decide**, against **71.4%** for the earliest alert rule
on the same corpus, an uplift of **20.9 points**. Correct abstention is **71.4%**, raised from
14.3% after the evaluation harness caught the system being confidently wrong on the one scenario
class built to test exactly that.

The second strongest proof point is a self inflicted defect: the evaluation sampler took the first
N incidents by sorted identifier, returned twenty incidents of the single easiest class, and
reported 100% top one accuracy. That is the inflated claim this product exists to prevent,
produced by its own harness, found and guarded.

## I. Most important architecture decision

Deterministic seed, then at most `k` agentic follow ups. The seed query set is enumerable in
advance, so it is enumerated rather than planned. The follow up set is not, because it depends on
what the seed pass found, so that single decision point is where a model sits. Everything the
system is judged on numerically, the ranking and the abstention, is produced by deterministic code
before any model is called.

## J. Top five KPIs

| # | KPI | Baseline | Value | How measured |
|---|---|---|---|---|
| 1 | Top one accuracy over decided incidents | Earliest alert, 71.4% | **92.3%** | Open split, 52 decided of 70, against hidden ground truth |
| 2 | Decision rate | None. Reported always, no target | **74.3%** | Same run. Never separated from accuracy (FR-061) |
| 3 | Correct abstention on insufficient evidence | 14.3% before fix | **71.4%** | Scored on the SC-5 class, n=7 |
| 4 | Investigation latency, p95 | Target under 30 s | **603 ms** deterministic, **17.4 s** full path | Measured per run |
| 5 | Release blocking safety gates | Zero tolerance | **4 of 4 pass** | Ground truth leakage, prompt injection over 24 payloads, role bypass, latency |

SM-1 and SM-3 carry **no numeric target**. ADR-028 deferred the blocking threshold and it was never
locked, which is why the sealed 30 incident split has correctly never been run.

## K. Main risks

| Risk | Severity | Note |
|---|---|---|
| Generator produces subtly wrong causality | High | Every downstream number becomes confidently and unfalsifiably wrong. The most expensive possible defect |
| Portability claimed rather than demonstrated | Medium | Recorded as the easiest thing to say by accident on stage |
| Simulator to reality gap | Structural | Topology is declared not discovered, noise is parameterised, the causal model is knowable by construction |
| Blocking threshold not locked, sealed split not run | Medium | Every number is open split only |
| No human baseline exists | Blocking for value claims | No task time reduction figure may be reported anywhere |
| Model citation fidelity is not uniform | Medium, mitigated | Two candidate models fabricated citations in 2 of 3 trials. Assignment now requires a measured fidelity check |

## L. Recommended jury narrative

The earliest alert is rarely the root cause, and the rule everyone reaches for first is right about
seventy one percent of the time. Six mature products already correlate telemetry, so we did not
build a seventh. We built the investigation layer that shows what argues against its own answer,
names what is missing, and declines when the evidence is not there. We scored it against a hidden
answer key, we publish the decision rate beside every accuracy figure, and the most useful defect
we found was one our own harness produced in us.

## M. Contradictions and missing evidence

Flagged rather than hidden, per section 28.M.

1. **`prd.md` contradicts itself inside one approved document.** Section 13's capability matrix marks
   agentic orchestration, tool execution, MCP and A2A as Not Applicable. Section 13A.2 marks all
   four Required. Section 13A was appended as impact analysis rather than as an amendment, so both
   tables are live.
2. **The PRD was approved before the topology changed** (risk R-11). NFR-015 no longer holds as
   written. Requirement re-tracing is a condition of Phase 2 entry.
3. **The agentic case rests on a stated requirement, not a measurement** (risk R-9). ADR-052 set an
   explicit acceptance bar for the agent. The measured outcome and the honest answer to the jury
   question this invites are recorded in `jury-qa.md` under architecture question A-4, which is
   where the presenter rehearses them. They are deliberately absent from the deck.
4. **Portability is the largest gap between the research story and the build.** The brief headlines
   industry transferability and names airline as a second domain. Only banking payments shipped.
5. **Re-ranking and interactive questioning** are bonus value in the brief and P0 or P1 in the deck.
   Resolved by building both.
6. **Scope outgrew the window.** Four capabilities turned Required after Gate 1. The engagement's
   own estimate was 9 to 12 days against an approved 5 to 6, resolved by staging rather than
   extending.
7. **Documented but not demonstrable from the tree**, and therefore claimed nowhere in the deck:
   Langfuse tracing, vector retrieval in operation (the rule embedding table is empty and retrieval
   mode defaults to deterministic), run record persistence and replayable runs, and any response
   cache.
8. **Missing evidence, named:** no judging rubric was ever issued (G-1), no human time to root cause
   baseline (G-2), no SME validation of the banking causal storyline (G-3), no persona validation,
   white space unvalidated with users (G-5), vendor ratings not benchmarked (G-7), no cited source
   independently read (G-9).

## N. System workflow classification

Eleven major workflows: **seven deterministic, zero purely agentic, four hybrid.**

**Overall classification: DETERMINISTIC-FIRST with a single bounded agentic decision point.**

The system contains exactly one agentic step. Both figures that the product is judged on, the
ranking and the abstention decision, are produced deterministically before any model is called.

## O. Workflow inventory

| Workflow | Type | Trigger | Key steps | Agent involvement | Deterministic controls | Output |
|---|---|---|---|---|---|---|
| Investigation | **Hybrid** | `POST /investigations` | seed, core, assess, follow up ×k, explain, recommend | One node, `assess` | Capability check, tool pin re-verify, allowlist seal, citation validation | Ranked hypotheses, evidence, next check |
| Deterministic pipeline | **Deterministic** with 2 bounded model calls | Agent unavailable, or `k = 0` | Normalize, rank, abstain, explain, recommend | None | Same allowlist for both model calls, abstention before models | Same shape, marked degraded |
| Grounded question answering | **Hybrid**, 1 model call | `POST /incidents/{id}/ask` | Re-derive deterministically, then one answer call | None | Question treated as untrusted, citation validation | Grounded answer |
| Postmortem | **Deterministic** | `POST /postmortem` | Template over a computed result | None | No model call, so no new citation surface | Narrative |
| Rules semantic search | **Hybrid**, 1 embedding call | `GET /rules/search` | Embed query, cosine over rule embeddings | None | Capability gated, text returned as data | Ranked rules |
| Embedding rebuild | **Hybrid** | `POST /corpus/rebuild-embeddings` | One batched embedding call | None | Corpus admin only | Index |
| Gateway and model admin | **Deterministic** | `PUT /admin/gateway` | SSRF validate, assignment validate, optimistic concurrency write | None | Audit row written on accept **and** on reject | Config, audit |
| Ablation switch | **Deterministic** | `PUT /agent/mode` | Clamp `k` to 0 through 5 | None | Administrator only | Mode |
| Incident lifecycle | **Deterministic, human only** | `PATCH /incidents/{id}/status` | Validate transition, write history | None | No automated code path exists, by design | State change |
| Corpus generation | **Deterministic** | Offline CLI | Truth first, seeded, then derive evidence | None | Truth first ordering assertion | Corpus, answer key |
| Evaluation | **Deterministic harness** | Offline CLI | Stratified sampling, score against ground truth | None | Answer key credential mandatory, tracing forced off | Result file |

## P. Agent inventory

**There is exactly one agent. Do not inflate this.** Multi agent orchestration was offered and
rejected by name as modularity mistaken for agency.

| Agent | Responsibility | Tools | Input | Output | Why agentic |
|---|---|---|---|---|---|
| `InvestigationAgent`, A2A card `rca-navigator` | Own one investigation: acquire evidence, run the deterministic core, explain, recommend | The pinned MCP tool set across six systems of record | Incident identifier, window, components, `k`, correlation identifier, delivered as an A2A task | Ranked hypotheses, evidence with provenance, planning trace, tool set digest, usage delta | Only for the follow up decision. The seed set is enumerable in advance so it is not planned. The follow up set depends on what the seed found |

Detail for the single agent:

- **Reasoning responsibility.** One question, in the `assess` node: is the evidence sufficient, and
  if not, which of six systems should I query next.
- **Guardrails.** Schema constrained output. At most four tool requests per round from a closed
  enum. Tool names outside the run start pin are dropped. The planner is shown evidence **counts,
  never evidence text**, which is the sharpest single injection control in the system.
- **Fallback.** Planner unavailable, mark degraded and treat the evidence as sufficient. Tool tier
  unverifiable, skip and mark degraded. Agent unreachable, the orchestrator runs the deterministic
  pipeline in process.
- **Human approval.** None inside the loop. The only human gated write is the incident lifecycle
  transition, and there is deliberately no code path from an investigation to it.

Four further model call sites exist and **are not agents**: explanation, recommendation, question
answering and embedding rebuild. All are single shot, schema bound, non planning, with no tool
access.

## Q. Deterministic component inventory

| Component | Responsibility | Why deterministic |
|---|---|---|
| Seed acquisition | Fixed window queries, component discovery capped at eight | The query set is enumerable in advance. No choice is being made |
| Normalisation | Deduplicate by marking never deleting, correct clock skew by per source median lag, weight by source quality | Pure function over records |
| Candidate generation | Upstream closure over the declared topology | Graph traversal. Edges are given, never inferred |
| Scoring | Five weighted signals: explanatory reach 0.40, temporal precedence 0.20, change proximity 0.20, anomaly strength 0.15, criticality 0.05 | Fixed arithmetic, and the weights are published on the response so a reader can re-derive the score |
| Contradiction computation | Symptoms preceding the candidate cause, or anomalies unreachable from it | Computed, not cosmetic |
| Missing evidence detection | Causal path components with no anomalous evidence | Set difference |
| Baseline comparator | Earliest alert wins, computed and never used to rank | An honest opponent for the uplift figure |
| Abstention gate | Three thresholds on top score, separation and direct evidence | Arithmetic on deterministic scores, and it runs **before** any model call |
| Tool set pinning | Digest over tool name, description and input schema, re-verified before every model call | Hash comparison, fails closed on drift |
| Evidence allowlist | Seed sealed at round zero, follow ups append only, re-sealed before each model call | Data structure invariant |
| Citation validation | Set difference of cited identifiers against the allowlist | Reject the whole response, never repair it |
| Credential scrubbing | Strip eleven model credential keys before spawning each tool server | Explicit denylist, asserted on both sides of the process boundary |
| Answer key guards | Refuse to open the ground truth store, refuse to boot if its credential is present | Filename and environment assertion, release blocking |
| Access control | Three roles across fifteen capabilities, fail closed | Static table, re-checked per operation |
| Log redaction | Serialisation time field allowlist plus a denylist that raises | Field name filtering, so a leak is an exception rather than a silent pass |

## R. Agent orchestration pattern

**Single agent with tools, sequenced by a custom state machine, with a bounded plan and execute
loop.** Six nodes and one conditional edge:

```
START -> seed -> core -> assess --+-> follow_up -> core -> assess  (at most k times)
                                  +-> explain -> recommend -> END
```

It is not supervisor and worker, not hierarchical, not a router and not event driven, because there
is only one worker and no dispatch. It is planner and executor only in the narrow sense that
`assess` plans and `follow_up` executes, and both live inside the same agent.

- **Who invokes the first agent.** The FastAPI orchestrator, over A2A.
- **Who chooses the next step.** The state machine's conditional edge, using the planner's boolean
  and the round counter. The model does not choose its own control flow.
- **Who maintains workflow state.** The state machine, in memory, for the duration of one
  investigation. There is no checkpointer configured and investigations are stateless re-runs.
- **How tools are exposed.** MCP over standard input, from six servers pinned at run start.
- **How failures are handled.** A degradation ladder, never a hard failure. See section T.

## S. AI control boundary

**What the AI may decide**

1. Whether the evidence gathered so far is sufficient.
2. Which of six systems of record to query next, from a closed enumeration, at most four requests
   per round.
3. The wording of the explanation, the contradiction and the recommendation, and the answer to a
   follow up question.

**What the AI may not decide**

- The ranking. Produced by scoring code. The prompt states explicitly that the model does not
  re-rank and does not propose hypotheses of its own.
- Whether to abstain. The gate runs before any model call.
- Any authorization decision.
- Which tools exist. There is no dynamic registration and the pin is frozen at run start.
- The incident lifecycle state, which is human only.
- Any remediation. The output vocabulary is restricted to check or escalate, and the database
  handles are read only by construction.

## T. Representative runtime flow

`POST /api/v1/investigations` for one incident, with `k = 3`:

| # | Step | Type |
|---|---|---|
| 1 | Bearer session resolved to an identity | **[D]** |
| 2 | Capability checked, fails closed | **[D]** |
| 3 | Incident window read from the corpus | **[D]** |
| 4 | A2A task opened over loopback with transport authentication | **[D]** |
| 5 | Seed pass across changes, tickets, alerts, metrics and logs | **[D]** |
| 6 | Every returned row validated. Unparseable or unprovenanced rows dropped, never coerced | **[D]** |
| 7 | Evidence admitted at round zero, then sealed | **[D]** |
| 8 | Normalize, rank, abstention gate | **[D]** |
| 9 | Tool set digest re-verified, evidence re-sealed | **[D]** |
| 10 | Sufficiency and next query decided | **[A]** |
| 11 | Tool names outside the pin dropped, follow up executed, loop back to step 8 | **[D]** |
| 12 | Explain, then recommend, over the frozen evidence set | **[H]** |
| 13 | Citation validation. A fabricated identifier rejects the whole response | **[D]** |
| 14 | Streamed to the browser. Timeline and ranking arrive before either model call | **[D]** |

**Degradation ladder.** Gateway unreachable, the deterministic result returns marked as missing its
explanation and recommendation. A facade unreachable, the investigation proceeds and names the
absent source. The agent unreachable, the orchestrator runs the deterministic pipeline in process
and says so on the stream. An outage never turns a working result into no result.

## U. MCP model

| Component | Role |
|---|---|
| MCP client | The agent process. It initiates every tool call. The dependency direction never inverts |
| MCP servers | Six Java facades, one per system of record, spawned as **standard input child processes of the agent**. No ports are opened |
| MCP tools | Windowed and filtered operations over one system each. A tool is an operation, never a table dump |
| Tool consumers | The agent only. Nothing else in the system holds an MCP client |
| Systems accessed | Six separate stores: metrics, logs, alerts, changes, tickets, runbooks |
| Protocol revision | `2024-11-05`, asserted at handshake. A mismatch refuses the server |
| Authorization | Structural rather than protocol level. Under standard input there is no listener to authenticate. Each server receives exactly one datasource and an environment scrubbed of eleven model credential keys, which it re-asserts before start up |

## V. Framework role

**LangGraph** is the workflow state machine inside the agent process. It sequences the six nodes,
evaluates the conditional edge, and enforces the loop bound. It holds run scoped state in memory,
with no checkpointer configured, so investigations are stateless re-runs and no cross session
context is carried. It makes **no business decision** and it is **not the agent**. Presenting it as
the agent would be a category error, and the deck says so explicitly on the agent scene.

**A2A** is the process boundary protocol between the orchestrator and the agent, over loopback with
transport authentication, with the agent set pinned by identity, name and card version at run start
and frozen for the run.

**LiteLLM** is the single routing owner. Every model call in the system, from the agent and from
the orchestrator, goes through it. No other component holds a model provider credential, and in the
tool tier the absence of one is asserted at start up rather than assumed.
