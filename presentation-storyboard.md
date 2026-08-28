# presentation-storyboard.md — Phase 2 Storyboard

> Seventeen scenes for a fifteen minute slot, roughly fifty seconds each.
> Implemented in `frontend/public/presentation.html`.
>
> The full presenter notes for every scene live in the deck itself, behind the notes toggle
> (`N` key). Each scene carries: what this slide means, what the presenter should say, why it
> matters, evidence, architecture detail where relevant, the likely jury question and a suggested
> answer. This document records the storyboard decisions and the narrative spine, not a second copy
> of that text.

## Narrative spine

```
Problem -> why it matters -> what research tells us -> the whitespace -> our product insight
  -> our solution -> how the system works -> deterministic versus agentic -> what the agent does
  -> why the architecture is this way -> how we measure -> how we keep it safe -> what it costs
  -> how it scales -> does it work -> back to the problem
```

Chapters in the dot rail: **Story** (1 to 6), **Architecture** (7 to 11), **Proof** (12 to 16),
**Close** (17).

---

## 1. Title

- **Takeaway.** Ledgerline helps payments investigators find a defensible cause, and says so when it cannot.
- **Visible.** Eyebrow with event and team. Product name at 76px. Gold rule. A two sentence proposition. A control hint.
- **Visual.** Full bleed editorial photograph on the left, content on the right, soft gradient between them. One of only two photographic scenes.
- **Evidence.** Product name is established across the shipped application. The proposition is the vision statement from `prd.md` section 3.
- **Jury question.** Is this a monitoring tool?
- **Transition.** From who we are to what is broken.

## 2. Problem

- **Takeaway.** The earliest alert is rarely the root cause.
- **Visible.** One headline. A four point alert timeline. Three columns: current reality, friction, consequence.
- **Visual.** A horizontal timeline with Checkout at 0s, Payments at 9s, Ledger at 22s, Database at 40s, and a single dependency arrow running the opposite way. The database node is gold, the loudest node is the decoy colour.
- **Evidence.** The incident shape from the product film, drawn from the synthetic corpus. The claim that the earliest alert misleads is measured later, not asserted here.
- **Jury question.** Is this shape typical, or a convenient example?
- **Transition.** Having seen why this is hard, here is how we decided to attack it.

## 3. Approach

- **Takeaway.** Use the least probabilistic method that can reliably solve each part.
- **Visible.** Three framed tiers with four examples each, then one closing line.
- **Visual.** Three equal frames, each headed by a semantic chip in the deterministic, hybrid and agentic colours. The colour language introduced here is reused on scenes 8 and 10.
- **Evidence.** Research deck slide 8, adopted as the governing architecture principle in the approved baseline.
- **Jury question.** Is this not an excuse for using less AI?
- **Transition.** That principle came out of what we found in the market.

## 4. Research

- **Takeaway.** The market already solved detection. It did not solve trust.
- **Visible.** Three columns: what the market does with all six competitors named, what remains unsolved, our opportunity. A framed verdict. A fidelity note.
- **Visual.** Editorial three column split with the verdict in a bordered band beneath. No logos.
- **Evidence.** Six vendor documentation sets, a 2026 realistic evaluation study, the Bank of England 2026 operational resilience statement for context only. All attributed, none independently read.
- **Jury question.** Why would a bank buy this instead of extending Dynatrace?
- **Transition.** So where exactly is the gap.

## 5. Whitespace and product insight

- **Takeaway.** Trust is the product. The telemetry is just the input.
- **Visible.** Five small frames, one per whitespace pillar, each headed in its own semantic colour. One rule about what counts as a differentiator. A fidelity note.
- **Visual.** A five up row, which is the widest grid in the deck and reads as a spectrum rather than a list.
- **Evidence.** The differentiation traceability matrix in `prd.md`. Each of the five has a functional requirement and an evaluation case. The two claims that did not qualify are deliberately absent.
- **Jury question.** Which of these is genuinely hard?
- **Transition.** Here is what that looks like as a product.

## 6. Solution, business

- **Takeaway.** One investigation, instead of six consoles and a whiteboard.
- **Visible.** Before, with Ledgerline, after. Three capabilities. A now, next, later strip. A portability badge.
- **Visual.** Three stacked bands separated by hairlines, so the eye reads across each band rather than down.
- **Evidence.** Corpus counts read directly from the shipped database: 110 incidents, 24 components, 592,842 evidence records. The next and later items are recorded architecture decisions with the seam designed and the build deferred.
- **Jury question.** You say it transfers to other industries. Prove it.
- **Transition.** From what it does to how it actually works.

## 7. Architecture, 6A

- **Takeaway.** Nine processes, seven trust boundaries, one agent.
- **Visible.** The full system diagram, then three notes on the controls that are structural rather than procedural.
- **Visual.** Boxes for processes, dashed for the sealed answer key and the store tier, one accent bordered box for the agent. A bordered band at the foot carries the release blocking invariant.
- **Evidence.** `architecture-baseline.md` sections 3 to 5, approved 2026-08-27.
- **Jury question.** Nine processes for a hackathon, is that not over engineering?
- **Transition.** Now, who does what inside that.

## 8. Workflow model, 6B

- **Takeaway.** One decision in this chain is made by a model. The rest is code.
- **Visible.** A ten step chain, each row carrying a D, A or H chip. A legend. One closing line.
- **Visual.** A single framed column of hairline separated rows. The one pink chip is the only spot of accent in the frame, so it is found by the eye immediately.
- **Evidence.** The implemented node sequence and the model call budget of two plus k, enforced in the router.
- **Jury question.** Why is the ranking not done by the model, it would be more flexible.
- **Transition.** So what is that one agentic step, precisely.

## 9. Agent landscape, 6C

- **Takeaway.** One agent, six nodes, one decision.
- **Visible.** The node graph with the loop. A four cell panel giving the agent's responsibility, tools, fallback and justification. A right hand panel separating four things that get confused. A rejection badge.
- **Visual.** Two columns. The right panel is the argumentative half and is bordered more strongly than anything else in the deck, because it is the scene's real payload.
- **Evidence.** The implemented graph, the planning schema, and the recorded rejection of multi agent orchestration as modularity mistaken for agency.
- **Jury question.** Why an agent at all, could a fixed script not do this?
- **Transition.** Let us trace one real request through all of it.

## 10. Runtime flow, 6D

- **Takeaway.** One incident, end to end, every step labelled.
- **Visible.** Twelve labelled steps across two columns. A framed degradation ladder.
- **Visual.** The same chip language as scene 8, so the reader already knows how to read it. The ladder sits in a bordered band beneath.
- **Evidence.** The implemented request path and the recorded degradation behaviour.
- **Demo handoff.** This is the strongest moment to leave the deck. One scenario only: the decoy incident, where the loudest service was deployed this morning and looks guilty but its error window opens before the deploy landed, while the real cause is three hops away and quiet because a certificate expired and it failed closed. The audience should watch two things: the ranking arrives before the explanation, and the contradicting evidence column is the same width as the supporting one. Return to scene 12.
- **Transition.** A short technology reference, then the proof.

## 11. Technology stack, 6E

- **Takeaway.** Technology mapped to responsibility, not a logo wall.
- **Visible.** Eight responsibility rows across two columns. A framed panel splitting where a model is used from where it is deliberately not.
- **Visual.** Label and description rows, hairline separated. No logos anywhere.
- **Evidence.** Every technology named is present in the shipped code with a pinned version. The model call sites are the four that exist, no more.
- **Jury question.** Why Java for the tool tier when everything else is Python?
- **Transition.** That is what we built. Here is whether it works.

## 12. KPIs

- **Takeaway.** Accuracy never appears without the decision rate beside it.
- **Visible.** A four up metric row with animated counters. Three KPI groups. A long fidelity note.
- **Visual.** Hairline divided metric row, the headline figure in the decided colour. The fidelity note is the longest body text in the deck, deliberately.
- **Evidence.** Read directly from `data/eval_open_nomodel.json` and `data/eval_open_full.json`, cross checked rather than transcribed from another slide.
- **Jury question.** Ninety two percent of what, and what about the other twenty six percent?
- **Transition.** Numbers only matter if the system is safe to run.

## 13. Guardrails

- **Takeaway.** The model chooses what to look at next. It never chooses what the system may do.
- **Visible.** Four lifecycle frames: input, reasoning, action, output. A framed control boundary panel. A line on the four release blocking gates.
- **Visual.** Four equal frames headed in four different semantic colours, then a two column boundary panel with "may" and "may not" facing each other.
- **Evidence.** The implemented controls. Injection resistance tested with 24 planted payloads and release blocking at zero successes.
- **Jury question.** What stops the model from taking an unsafe action?
- **Transition.** Safe and accurate. What does it cost.

## 14. Economics

- **Takeaway.** The cost of an investigation is bounded by design, not by a budget alarm.
- **Visible.** Three frames: measured, honestly unknown, what we would need to claim value. A dashed illustrative model with lettered inputs. A fidelity note.
- **Visual.** The only dashed border in the deck, marking the illustrative frame as structurally different from everything else on screen. The inputs are letters, not numbers, so no figure can be misread as a finding.
- **Evidence.** The two plus k bound is enforced in the router. Token counts are from a real measured run. The currency behaviour is a functional requirement: the display renders the literal word rather than zero or an estimate.
- **Jury question.** So you cannot tell me what this is worth?
- **Transition.** If the economics work, what does adoption look like.

## 15. Adoption and scale

- **Takeaway.** Adoption comes from declining well, not from answering always.
- **Visible.** Three columns: why an investigator keeps using it, how it scales technically, what the path actually requires. A framed panel explaining the gamification decision.
- **Gamification.** Deliberately replaced, which master prompt section 10 explicitly permits. The user is an engineer under time pressure during a payments outage. Streaks and badges would reduce the seriousness of the moment and reward speed where the product wants care. The behaviour actually worth reinforcing, checking the contradicting column before accepting an answer, is reinforced by layout instead: both evidence columns open, at equal width, every time.
- **Jury question.** How long to a second domain, honestly?
- **Transition.** All of that rests on whether the testing is real.

## 16. Testing and proof

- **Takeaway.** The most useful defects were the ones our own harness found in us.
- **Visible.** Test, evidence, and confidence with its limits. A framed panel on the sampling defect. A fidelity note.
- **Visual.** Three columns, then the defect in a strongly bordered band as the scene's payload.
- **Evidence.** 346 tests collected with the last full run clean. Release blocking negative tests. Citation fidelity measured per model. The sampling defect and its regression guard are recorded in the roadmap and the guard is in the evaluation runner.
- **Jury question.** You have not run the sealed evaluation, why should we trust the open number?
- **Transition.** Back to where we started.

## 17. Close

- **Takeaway.** The earliest alert is rarely the root cause, and we built the layer that says which one is.
- **Visible.** Team and product eyebrow, the opening line as the closing line, the proposition, two live links, one word inviting questions.
- **Visual.** The second and last photographic scene, mirroring scene 1 so the deck visually closes its own loop.
- **Links.** Launch the console and back to Ledgerline, both absolute to the dev server so they work when the deck is opened from disk.

---

## Density check

Outside the architecture scenes, where labels legitimately need more text, every scene holds one
primary message and stays under roughly forty five visible words. Scenes 7 through 11 are the
declared exception under master prompt section 12.

## Copy rules applied throughout

No em dashes anywhere, punctuation only. No whole phrase set in capitals, and no CSS
`text-transform` is used, so eyebrows are sentence case with letter spacing rather than uppercase.
Score is never described as a probability. Contradicting evidence is always a visual peer of
supporting. Abstention is drawn as an answer, never as an error. The fidelity notice appears on
every scene that carries a metric.
