# jury-qa.md — Jury Question Preparation

> Rehearsal document for **Deep Thinkers**, Annual AI Hackathon Final. Not shown to the jury.
>
> Thirty questions across five bands. Each carries why they may ask it, a thirty second answer for
> the room, and a deep dive for follow up.
>
> **Three answers in here are deliberately not in the deck.** A-4, R-2 and S-3 cover the agent
> ablation, the implemented tool count, and capabilities that appear in our documents but are not
> demonstrable from the current tree. The deck claims none of them, so these questions are only
> reachable if a judge digs. If one does, the honest answer is stronger than a deflection.

---

## Executive band

### E-1. What problem are you actually solving, in one sentence?

**Why they ask.** To test whether the team can compress its own work. A team that cannot will
usually not have a sharp product either.

**Thirty seconds.** When a payments platform fails, everything downstream fails too, so the alerts
arrive in roughly reverse order of causation. We rank the likely causes, show the evidence for and
against each, and decline honestly when the evidence is not there.

**Deep dive.** The brief itself makes the distinction: the challenge is not detecting failure, it
is identifying the most plausible root cause fast enough to reduce impact. Everything we built
follows from taking that sentence literally, including the decision not to build any detection.

### E-2. Why should we care, commercially?

**Why they ask.** To find out whether this is a science project.

**Thirty seconds.** Two reasons. Investigation time during a payments outage is the most expensive
engineering time a bank spends. And the evidence trail we produce is exactly what a risk function
needs after the fact, which is a second buyer inside the same organisation.

**Deep dive.** Be careful here. We have no measured human baseline, so we do not quote a time
saving. What we can quote is that the rule teams start with scores 71.4% on our corpus and our
engine scores 92.3% over the incidents it decides. The commercial argument is about first
hypothesis quality, not about minutes, until a pilot produces the baseline.

### E-3. There are thirty teams here. Why do you win?

**Why they ask.** Memorability.

**Thirty seconds.** Most submissions will show you more AI. We are showing you a system that
measures whether its own AI is earning its place, and publishes the number it is worst at. In a
bank, that is the difference between a demo and something you can actually deploy.

**Deep dive.** Point at three specifics: accuracy is never shown without decision rate, a fabricated
citation rejects the whole response rather than being repaired, and our own harness caught us
reporting a false 100% and we published that.

### E-4. Is this safe to put in front of a regulated bank?

**Why they ask.** Payments is a regulated context and someone in the room owns that risk.

**Thirty seconds.** It is read only by construction, it recommends and never acts, and it holds no
customer data because the corpus is synthetic. We make no compliance claim, because a synthetic
data prototype has not earned one.

**Deep dive.** The controls that would matter in a real assessment are structural rather than
procedural: no code path to a write, credential isolation asserted at start up, an audit row on
gateway config changes written on rejection as well as acceptance, and a logging denylist that
raises rather than silently redacting.

### E-5. What would you do with another month?

**Why they ask.** To see whether the team knows its own gaps.

**Thirty seconds.** Lock the accuracy threshold and run the sealed evaluation split once, which
turns an internal validity signal into a result. Then measure a human baseline on real incidents,
which is the single missing input between us and a defensible value claim.

**Deep dive.** Third would be the airline domain pack, because it is the only way to convert
portability from designed for into demonstrated.

---

## Business and product band

### B-1. Six vendors already do this. Why are you not redundant?

**Why they ask.** It is the obvious objection and we raised it ourselves.

**Thirty seconds.** They are better than us at correlation and they always will be, because they
own the telemetry. We do not compete there. We are the layer that shows the contradiction, names
what is missing, and can be scored against a known answer, and none of those is a telemetry
problem.

**Deep dive.** IBM Instana already gates on confidence and shows up to three probable causes, so we
do not claim abstention as a novel feature. We claim it as a measured one: correct abstention
71.4%, false abstention 20.6%, published.

### B-2. Who is the user, and did you talk to any?

**Why they ask.** To test the research.

**Thirty seconds.** The user is the incident investigator. And no, we did not interview one. That
is a recorded gap, and every persona derived requirement inherits the uncertainty.

**Deep dive.** Do not let `interview-log.md` be mistaken for user research. It is a log of our own
decisions, mostly reconstructed and paraphrased. Being straight about this costs nothing and
protects everything else we claim.

### B-3. What is in the product today versus what is a slide?

**Why they ask.** It is the fastest way to catch an overclaiming team.

**Thirty seconds.** Today: banking payments, 110 incidents, 24 components, 592,842 evidence records,
scored end to end, with the console, the agent run view, analytics, corpus browsing and settings all
live. Designed but not built: the airline pack and multi tenancy.

**Deep dive.** Also be precise that authentication is a development session, not a provider
integration, and that the corpus regeneration path runs from the command line rather than the UI.

### B-4. Why is portability on your slides if you have not proven it?

**Why they ask.** Because we put it there.

**Thirty seconds.** It is on the slide as designed for, with a badge that says it is not proven.
The seam is real: the reasoning core has no banking specific branch, and domain knowledge is data
rather than code.

**Deep dive.** What a second domain actually needs is a component taxonomy, a dependency map, an
operating rules set and a generator profile. That is real work and we have not done it once.

### B-5. Why no gamification? The brief mentions it.

**Why they ask.** They may be checking whether we followed a template or thought.

**Thirty seconds.** We considered it and decided against it. The user is an engineer during a
payments outage. Streaks and badges would reward speed where we want care.

**Deep dive.** The behaviour worth reinforcing is checking the contradicting column before accepting
an answer, and we reinforce it through layout instead: both evidence columns open at equal width,
every time.

---

## Architecture and engineering band

### A-1. How many agents are there, and what does each do?

**Thirty seconds.** One. It owns a single decision: is the evidence sufficient, and if not which of
six systems do I query next. Five other nodes in its graph are deterministic code.

**Deep dive.** Multi agent was offered and we rejected it by name as modularity mistaken for agency.
Splitting one reasoning job across five agents adds serialisation latency and failure surface
without adding judgement.

### A-2. Who orchestrates the agent, and is LangGraph the agent?

**Thirty seconds.** No. The FastAPI orchestrator delegates over A2A and owns authorization.
LangGraph is the state machine inside the agent process: it sequences six nodes, evaluates one
conditional edge and enforces the loop bound. It makes no business decision.

**Deep dive.** Control flow is chosen by the state machine's conditional edge using the planner's
boolean and the round counter. The model never chooses its own control flow, which is why the worst
case call count is known before the run starts.

### A-3. Why is this workflow deterministic rather than agentic?

**Thirty seconds.** Because the seed query set is enumerable in advance. If we can write down every
query before the run, planning them at runtime buys nothing and costs latency, money and
predictability.

**Deep dive.** The converse is the justification for the one agentic step: the follow up set depends
on what the seed pass found, so it cannot be enumerated. That is the test we applied to every step.

### A-4. Did you measure whether the agent actually improves the result?

> **Not in the deck. Answer honestly if asked.**

**Why they ask.** A sharp architect will notice that our own principle demands the test.

**Thirty seconds.** Yes, and that is why the ablation switch is a shipped feature rather than a
script. Setting `k` to zero reduces the graph to the deterministic pipeline exactly, so the two are
comparable on the same corpus. On our current evidence the deterministic core is carrying the
result, and the agent has not yet cleared the bar we set for it.

**Deep dive.** ADR-052 set an explicit acceptance test: `k` greater than zero must beat 92.3% top
one accuracy, or the agent has not earned its place. On a six incident stratified ablation, `k=0`
and `k=2` both scored 80.0% top one over an identical decision rate, no follow up round actually
fired, and the agent path cost about two and a half extra seconds. The sample is far too small to
conclude the agent is useless, and it is easily large enough to conclude we have not yet
demonstrated it is useful. So the honest position is: the agentic topology is built, instrumented
and measurable, the measurement is not yet favourable, and we ship the deterministic path as the
one carrying the numbers. We would rather tell you that than show you an uplift we cannot support.

### A-5. Where does MCP fit? Which component is the client and which is the server?

**Thirty seconds.** The agent is the MCP client. The six facades over the systems of record are MCP
servers. They run as standard input child processes of the agent, so they open no ports and nothing
is network reachable.

**Deep dive.** Protocol revision `2024-11-05` is asserted at handshake and a mismatch refuses the
server. The dependency direction never inverts: a tool server cannot drive workflow control.

### A-6. What tools are exposed, and what stops the agent calling something else?

**Thirty seconds.** Windowed, filtered operations over one system of record each. A tool is an
operation, never a table dump. At run start we pin the tool set by a digest over name, description
and input schema, and re-verify it before every model call.

**Deep dive.** If the digest has drifted mid run we fail closed rather than continuing, because a
changed tool description is changed prompt content. Any tool name the planner invents is dropped
before execution.

### A-7. What happens when an agent, a tool or the model fails?

**Thirty seconds.** Nothing hard fails. Gateway down, the deterministic result returns marked as
missing its explanation. A facade down, the investigation proceeds and names the absent source. The
agent down, the orchestrator runs the deterministic pipeline in process.

**Deep dive.** The rule we designed to is that an outage must never turn a working result into no
result at all. That matters more here than in most products, because the dependencies are least
reliable at exactly the moment the tool is needed.

### A-8. Who holds workflow state, and is there memory?

**Thirty seconds.** The state machine holds run scoped state in memory for one investigation. There
is no conversational or persistent memory, and investigations are stateless re-runs.

**Deep dive.** Be precise on one point: no checkpointer is configured in the current tree, so state
does not survive a process restart. Investigations are re-run rather than resumed, which is
consistent with them being stateless by design.

### A-9. How does RAG work here?

**Thirty seconds.** Evidence retrieval is relational, not vector. Every piece of evidence reaches
the model through a SQL backed tool call. There is no embedding or similarity search over evidence
anywhere.

**Deep dive.** There is a small vector path for the operating rules knowledge base, one rule per
chunk with cosine similarity in process. In the current tree the rule embedding table is empty and
retrieval mode defaults to deterministic exact matching, so the semantic path does not execute. We
therefore do not claim vector retrieval as an operating capability, and it is on no slide.

### A-10. Nine processes for a five day build. Justify it.

**Thirty seconds.** Six of the nine are child processes the agent spawns and reaps, so operationally
it is one supervised lifecycle rather than six services. We paid that cost for three properties.

**Deep dive.** No network surface on the tool tier, because under standard input there is nothing to
bind. Credential isolation that is verifiable at start up rather than asserted, because eleven model
credential keys are stripped before spawn and their absence is re-asserted inside each child. And
one datasource per system, so a compromised facade can read one system and no more.

### A-11. What operational hardening is missing?

**Why they ask.** An engineering leader will look for the gaps a demo hides, and rate limiting is
usually the first one they reach for.

**Thirty seconds.** Three, and we would name them before you find them. There is no rate limiting
anywhere. Authentication is a development session rather than a provider integration. And nothing
survives a process restart, because investigations are stateless re-runs with no checkpointer.

**Deep dive.** None of the three is load bearing for what we demonstrate today, and all three are
straightforward rather than architectural. Rate limiting belongs at the orchestrator boundary where
authorization already sits. The authentication contract is written and the provider selection is
the open item. Persistence has a schema waiting for a writer.

---

## AI and responsible AI band

### R-1. How do you control hallucination?

**Thirty seconds.** The evidence set is sealed before each model call and frozen during it, and
every cited identifier is checked against that set. A fabricated identifier rejects the entire
response rather than being repaired.

**Deep dive.** Rejecting rather than repairing is deliberate. A model that invents a citation has
told you something about the rest of its answer, so the correct outcome is no explanation rather
than a quietly patched one.

### R-2. How many tools does the tool tier expose?

> **Not in the deck. The deck describes six facades, one per system of record, and states no count.**

**Thirty seconds.** Six servers, one per system of record. In the current working tree fourteen
tools are implemented across five of them, and the logs facade is being restored, so I would not
quote a fixed tool count today.

**Deep dive.** If pressed, be exact: `tooltier/mcp-logs` has no Java source in the current tree and
its jar is an empty archive, which means the agent cannot start until it is rebuilt. Its seed
queries are `logs_severity_summary` and `logs_search`. This is a known build defect, not a design
gap, and the deterministic fallback path is what makes it survivable rather than fatal.

### R-3. How do you stop prompt injection from the corpus?

**Thirty seconds.** Three layers. Every prompt frames corpus text as untrusted data. The planner is
shown evidence counts and never evidence text. And every streamed value is encoded rather than
formatted into the line.

**Deep dive.** The middle one is the sharpest. The component that chooses which tool to call next
never sees the text of a log line, so a poisoned log cannot influence tool selection. We tested with
twenty four planted payloads across logs, tickets and runbooks, and zero successful injections is
release blocking.

### R-4. How do you prevent an unsafe action?

**Thirty seconds.** There is no action to take. The product is read only at the database handle and
the recommendation vocabulary has two verbs, check and escalate. There is no code path from an
investigation to a write.

**Deep dive.** The one human gated write is the incident lifecycle transition, and there is
deliberately no automated path to it. We have a negative test asserting that path does not exist.

### R-5. How do you know your evaluation is not leaking the answer?

**Thirty seconds.** The answer key is a separate store, in a separate process, behind a separate
credential, and no runtime component has an edge to it. That absence is release blocking and proven
by a negative test in every process.

**Deep dive.** We also found and fixed a subtler leak: the scenario class label itself encoded the
correct behaviour for the abstention class, so a system could have scored perfectly on that
evaluation with a single query. And tracing is forced off for evaluation runs, because the harness
legitimately holds both prediction and ground truth.

---

## Scale and economics band

### S-1. What does this cost to run at scale?

**Thirty seconds.** Per investigation it is exactly two model calls plus at most `k` follow ups, and
that bound is enforced in the router rather than by a budget alarm. One measured run used just under
five thousand input and about two thousand three hundred output tokens across four calls.

**Deep dive.** In currency, we render the literal word Unknown, because our gateway publishes no
price for any model. That is deliberate: never zero, and never an estimate borrowed from an
unrelated rate.

### S-2. What is the return on investment?

**Thirty seconds.** We are not going to give you one, because we never measured how long this takes
a human today. Multiplying three assumptions together would be arithmetic dressed as evidence.

**Deep dive.** What we would need is a measured human time to root cause, an incident volume and
severity mix for a named operator, and a validated cost of a minute of payment downtime. The first
two weeks of a pilot would produce the first, because the harness that measures accuracy already
exists and would only need real incidents pointed at it.

### S-3. Your documents mention tracing and replayable runs. Show me.

> **Not in the deck. Nothing in the deck claims either.**

**Thirty seconds.** Both are designed and neither is demonstrable from the current tree. Structured
logging with a redaction allowlist, correlation identifiers and per tool call timing are real.
Distributed tracing is not wired, and investigation results are not persisted.

**Deep dive.** Be specific rather than vague: the run record and investigation tables exist in the
schema with no writer, so a replayable run is a designed capability we have not built. Saying so
costs us one feature claim and protects every other claim in the deck.

### S-4. How does this scale technically?

**Thirty seconds.** Each system of record is a separate store behind its own facade, so they scale
apart. Tenant scope is carried and filtered from day one. Domain knowledge is data rather than a
code branch.

**Deep dive.** The honest constraint is that the current stores are SQLite and the concurrency
assumption is single digit across processes. Moving to a real deployment means replacing facades,
which is the seam the architecture was drawn around, not rewriting the reasoning core.

### S-5. What breaks when you point this at real telemetry?

**Thirty seconds.** Three things we already know. Our topology is declared rather than discovered
and is therefore perfectly accurate, which real topology never is. Our noise is parameterised and
well behaved. And our causal model is knowable by construction, where real incidents sometimes have
no single recoverable root cause.

**Deep dive.** This is why we say validation against real incident data is required before any
production claim, and why every metric in the deck is labelled as an internal validity signal.
Volunteering this list is stronger than being walked into it.

---

## Three phrases to avoid on stage

1. **"Proven portability."** Say designed for. It is the easiest thing to say by accident.
2. **"Ninety two percent accurate."** Always attach the decision rate. Its absence is a reporting
   defect, not a style choice.
3. **"It saves engineers X minutes."** No human baseline was measured, so there is no such number.
