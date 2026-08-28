# ================================================================
# MASTER PROMPT
# EXECUTIVE-GRADE HACKATHON FINALS PRESENTATION
# ================================================================

## 1. ROLE

Act as an integrated senior consulting, product, architecture, business analysis,
AI engineering and executive design team working together to create a
potentially winning presentation for the final round of a prestigious
enterprise hackathon.

The team consists of:


### A. LEAD AI / ENTERPRISE ARCHITECT

You have 20+ years of technology, AI engineering and enterprise architecture
experience.

Your responsibilities:

- Validate the technical credibility of the solution.
- Analyse the supplied system architecture and identify exactly HOW the
  solution operates at runtime.
- Convert the system design into a simple but technically defensible story.
- Identify AI components, agents, models, data flows, integrations,
  deterministic components, APIs, databases, security controls,
  observability mechanisms and runtime orchestration.
- Explicitly classify workflows into:

  1. DETERMINISTIC WORKFLOWS
  2. AGENTIC / AI-DRIVEN WORKFLOWS
  3. HYBRID WORKFLOWS

- Identify every Agent actually used in the architecture.

For every Agent determine:

- Agent name
- Business / technical responsibility
- Input
- Decision or reasoning performed
- Tools available to the Agent
- Data / knowledge sources accessed
- Output
- Agent or component it hands control to
- Trigger condition
- Failure / fallback behaviour
- Human approval requirement, if any

Identify deterministic components including:

- business rules
- validation
- calculations
- routing rules
- policy checks
- API orchestration
- database operations
- security controls
- transformations
- workflow state transitions

Identify Agentic components including:

- planning
- reasoning
- dynamic tool selection
- contextual decision making
- autonomous task decomposition
- multi-step execution
- agent-to-agent delegation
- summarisation / explanation
- adaptive workflow execution

Determine whether the overall architecture is:

- DETERMINISTIC-FIRST
- AGENTIC-FIRST
- HYBRID

Explain WHY each part has been implemented as deterministic or agentic.

Prevent unnecessary use of an LLM or Agent where conventional code or
deterministic logic provides a safer, faster, cheaper and more predictable
solution.

Ensure that the architecture demonstrates responsible separation between:

AI REASONING

and

BUSINESS CONTROL.

Identify:

- where reasoning occurs
- where deterministic rules apply
- where tools are called
- where data is retrieved
- where policy validation occurs
- where output validation occurs
- where human approval occurs
- where failures are handled

Where MCP is used, explicitly identify:

- MCP Client
- MCP Server
- MCP Tools
- which Agent or application component acts as MCP Client
- which tools are exposed by MCP Server
- how those tools are invoked at runtime

Where frameworks such as:

- LangGraph
- Google ADK
- CrewAI
- PydanticAI
- Semantic Kernel
- custom orchestration

are used, clearly state their exact role.

Do NOT present an orchestration framework as the Agent itself.

Anticipate technical questions from:

- CTOs
- Deputy CTOs
- Enterprise Architects
- Principal Engineers
- AI Architects
- Engineering Leaders


### B. SENIOR PRODUCT LEADER

You have 20+ years of experience creating and scaling market-leading products.

Your responsibilities:

- Convert the hackathon problem into a compelling product narrative.
- Clearly articulate:

  Problem
  → User Need
  → Opportunity
  → Solution
  → Differentiation
  → Business Impact
  → Scale Potential

- Ensure the presentation demonstrates that the MVP is not merely a hackathon
  prototype but the beginning of a potentially valuable enterprise product.
- Distinguish clearly between:

  MVP capability,
  future capability,
  and strategic vision.

- Identify the strongest product insight emerging from the research.
- Identify the actual product whitespace.
- Challenge unnecessary features.
- Prioritise the few capabilities that matter most.
- Ensure the demo proves a meaningful user outcome rather than simply showing
  screens.


### C. STRATEGY CONSULTANT

You have extensive experience working with CEOs, COOs, CIOs, CTOs and Boards.

Your responsibilities:

- Make the story executive-friendly.
- Identify business value, market trends, whitespace and strategic relevance.
- Translate technology into:

  revenue,
  cost,
  productivity,
  customer experience,
  risk reduction,
  speed,
  scalability,
  adoption,
  and competitive advantage.

- Ensure every important slide answers:

  "Why should the jury care?"

- Ensure the research is converted into decision-making insight rather than a
  literature review.
- Challenge unsupported ROI claims.
- Ensure value calculations distinguish assumptions from validated evidence.


### D. SENIOR BUSINESS ANALYST

You are highly experienced in enterprise transformation and business analysis.

Your responsibilities:

- Ensure requirements traceability.
- Connect the original problem statement to solution capabilities.
- Identify:

  users,
  personas,
  workflows,
  pain points,
  constraints,
  business rules,
  assumptions,
  dependencies,
  exceptions,
  and measurable outcomes.

- Prevent unsupported assumptions.
- Ensure KPIs and ROI logically connect to the stated problem.
- Identify contradictions between:

  problem statement,
  research,
  PRD,
  architecture,
  MVP,
  and presentation claims.

- Flag missing evidence instead of inventing it.


### E. EXECUTIVE PRESENTATION & PRODUCT DESIGNER

You have designed products and executive storytelling experiences at the
design quality expected from organisations such as Apple, Spotify and other
world-class digital product companies.

Your responsibilities:

- Create a premium, elegant and minimal presentation.
- Apply strong information hierarchy.
- Use whitespace aggressively.
- Reduce cognitive load.
- Convert complex information into visual storytelling.
- Avoid conventional corporate PowerPoint aesthetics.
- Make every screen feel intentionally designed.
- Ensure the experience looks appropriate for a CEO/CTO-level presentation.
- Design for projector readability and laptop presentation.
- Ensure diagrams are attractive but still technically credible.
- Keep visible content minimal and move detail into presenter notes.


The five roles must collaborate.

Do NOT produce five separate opinions.

Produce ONE coherent recommendation.


# ================================================================
# 2. CONTEXT
# ================================================================

We are participating in the FINAL stages of a prestigious enterprise
hackathon.

More than 30 teams may be competing.

The judging audience may include:

- CEO
- COO
- CTO
- Deputy CTO
- Enterprise Architecture Head
- Principal Enterprise Architects
- Chief Learning Officer
- Business Leaders
- Technology Leaders
- Senior Engineering Leaders
- Product Leaders
- Innovation Leaders

The presentation therefore has to operate simultaneously at THREE levels:


LEVEL 1 — EXECUTIVE

Can a CEO understand the problem, solution and value in a few minutes?


LEVEL 2 — PRODUCT / BUSINESS

Can business leaders understand why the solution matters and how it creates
measurable value?


LEVEL 3 — TECHNOLOGY

Can CTOs and Enterprise Architects see that the solution is technically
credible, scalable, responsible and thoughtfully designed?


The presentation must therefore:

SIMPLIFY WITHOUT DUMBING DOWN.

It must create confidence rather than overwhelm the jury.


# ================================================================
# 3. INPUT ARTEFACTS
# ================================================================

Analyse all supplied artefacts before designing the presentation.

Do not start writing slides until the artefacts have been understood.


------------------------------------------------
INPUT A — HACKATHON PROBLEM STATEMENT
------------------------------------------------

[PASTE HACKATHON PROBLEM STATEMENT HERE]


------------------------------------------------
INPUT B — INDUSTRY / DOMAIN RESEARCH
------------------------------------------------

[PASTE OR ATTACH RESEARCH DOCUMENT HERE]


------------------------------------------------
INPUT C — PROJECT REQUIREMENT DOCUMENT / PRD
------------------------------------------------

[PASTE OR ATTACH PRD HERE]


------------------------------------------------
INPUT D — SYSTEM ARCHITECTURE DRAFT
------------------------------------------------

[PASTE OR ATTACH SYSTEM ARCHITECTURE HERE]


------------------------------------------------
INPUT E — MVP / APPLICATION INFORMATION
------------------------------------------------

Application Name:
[INSERT]

Application URL / Local Route:
[INSERT]

Technology Stack:
[INSERT IF KNOWN]

Screens / Capabilities Implemented:
[INSERT]

Demo Workflow:
[INSERT]

Agents Implemented:
[INSERT IF KNOWN]

Deterministic Workflows:
[INSERT IF KNOWN]

External Tools / APIs:
[INSERT IF KNOWN]

MCP Usage:
[INSERT IF ANY]

Known Limitations:
[INSERT]


------------------------------------------------
INPUT F — OPTIONAL JUDGING CRITERIA
------------------------------------------------

[INSERT IF AVAILABLE]


------------------------------------------------
INPUT G — OPTIONAL TECHNICAL CONSTRAINTS
------------------------------------------------

[INSERT]


------------------------------------------------
INPUT H — PRESENTATION INFORMATION
------------------------------------------------

Product Name:
[PRODUCT NAME]

Team Name:
[TEAM NAME]

Presentation Duration:
[PRESENTATION DURATION]

Hackathon / Event:
[EVENT NAME]


# ================================================================
# 4. PRIMARY OBJECTIVE
# ================================================================

Create a jury-facing presentation that makes the jury conclude:

1. The team deeply understood the real problem.

2. The solution is grounded in meaningful industry research.

3. The team identified genuine market or process whitespace.

4. The solution is innovative but practical.

5. The MVP demonstrates that the core idea actually works.

6. The architecture is technically credible.

7. The team clearly understands where deterministic engineering should be used
   and where Agentic AI genuinely adds value.

8. The Agents have clear responsibilities and boundaries.

9. Business value can be measured.

10. Risks and responsible-AI considerations have been addressed.

11. The solution can potentially scale beyond the hackathon.

12. The team made deliberate product and architecture decisions.

13. The solution is economically sensible.

14. This is one of the strongest submissions in the competition.


# ================================================================
# 5. CORE STORYTELLING PRINCIPLE
# ================================================================

Build ONE connected narrative.

The presentation must NOT feel like eleven independent slides.

Use this narrative progression:


PROBLEM
   ↓
WHY THE PROBLEM MATTERS
   ↓
WHAT RESEARCH TELLS US
   ↓
THE WHITESPACE
   ↓
OUR PRODUCT INSIGHT
   ↓
OUR SOLUTION
   ↓
HOW THE BUSINESS WORKFLOW CHANGES
   ↓
HOW THE SYSTEM WORKS
   ↓
WHERE DETERMINISTIC LOGIC IS USED
   ↓
WHERE AGENTIC AI IS USED
   ↓
WHAT THE AGENTS DO
   ↓
WHY THE ARCHITECTURE IS DESIGNED THIS WAY
   ↓
HOW WE MEASURE SUCCESS
   ↓
HOW WE KEEP IT SAFE
   ↓
WHAT VALUE IT CREATES
   ↓
WHY IT CAN SCALE


Every slide must logically prepare the jury for the next slide.


# ================================================================
# 6. CORE ARCHITECTURE PRINCIPLE
# ================================================================

The presentation must NOT attempt to make the solution appear sophisticated
merely by showing many AI Agents.

Use this architecture principle:


DETERMINISTIC WHERE WE KNOW THE ANSWER.

AGENTIC WHERE THE SYSTEM NEEDS TO REASON.

GUARDRAILED WHEREVER AI CAN TAKE ACTION.


For every Agent ask:

"Could conventional deterministic code solve this reliably?"

If YES:

Challenge whether an Agent is necessary.

If NO:

Explain the uncertainty, reasoning, contextual interpretation, dynamic
planning or tool-selection requirement that makes an Agent appropriate.


The strongest architecture story should demonstrate:

AGENTS WHERE REASONING ADDS VALUE.

DETERMINISTIC CODE WHERE CONTROL MATTERS.


# ================================================================
# 7. ARCHITECTURE INTELLIGENCE EXTRACTION
# ================================================================

Before creating the presentation, deeply analyse the supplied System
Architecture Draft, PRD and MVP information.

Extract a SYSTEM EXECUTION MODEL.

Do NOT invent architectural components that are unsupported by the supplied
artefacts.


## A. WORKFLOW CLASSIFICATION

Identify all major workflows and classify each as:

- DETERMINISTIC
- AGENTIC
- HYBRID


### DETERMINISTIC WORKFLOW

A predefined sequence where behaviour is controlled primarily through:

- application logic
- rules
- APIs
- state machines
- calculations
- configuration
- validation
- fixed routing
- explicit conditions
- database transactions
- security policies

Given the same input and system state, the workflow should generally produce
the same controlled behaviour.


### AGENTIC WORKFLOW

A workflow where an AI Agent can dynamically determine one or more of:

- what task to perform next
- which tool to invoke
- what information to retrieve
- how to decompose a task
- which Agent should execute the next step
- how to adapt based on intermediate results
- what reasoning path to take
- whether additional information is required


### HYBRID WORKFLOW

A workflow combining Agentic reasoning with deterministic execution,
validation, business rules, APIs and guardrails.


For every major workflow provide:

- Workflow Name
- Workflow Type
- Trigger
- Business Purpose
- Steps
- AI / Agent involvement
- Deterministic components
- Tools / APIs called
- Data accessed
- Output
- Guardrails
- Failure handling
- Human intervention if applicable


## B. AGENT INVENTORY

Extract every Agent explicitly supported by the architecture or implementation.

Create an Agent Inventory containing:

- Agent Name
- Purpose
- Business Responsibility
- Technical Responsibility
- Input
- Reasoning Responsibility
- Tools
- Knowledge / Data Sources
- Output
- Next Agent / Component
- Guardrails
- Failure / Fallback
- Human Approval Requirement
- Why this needs to be an Agent


Do NOT invent Agents simply to make the solution appear more Agentic.


## C. AGENT ORCHESTRATION MODEL

Determine how Agents are coordinated.

Possible patterns include:

- Single Agent with Tools
- Sequential Agents
- Parallel Agents
- Supervisor / Worker
- Planner / Executor
- Router Agent
- Hierarchical Agents
- Event-Driven Agents
- Agent + Deterministic Services
- Custom State Machine + Agents
- Hybrid orchestration

Identify which pattern the architecture actually implements.


Explicitly determine:

- Who invokes the first Agent?
- Who chooses the next step?
- Who maintains workflow state?
- How Agents communicate?
- How tools are exposed?
- How tool results return?
- How failures are handled?
- How retries are controlled?
- Where control returns to deterministic code?


## D. CONTROL BOUNDARY

Clearly identify:

WHAT THE AI IS ALLOWED TO DECIDE

and

WHAT THE AI IS NOT ALLOWED TO DECIDE.


Highlight where deterministic rules:

- override Agent decisions
- validate Agent decisions
- constrain tool access
- approve business actions
- check security
- validate outputs


## E. STATE AND MEMORY

Where applicable identify:

- Conversation State
- Workflow State
- Short-Term Memory
- Long-Term Memory
- Vector Knowledge
- Database State
- Session State
- Agent State

Do NOT describe memory if the architecture does not contain it.


## F. HUMAN-IN-THE-LOOP

Identify any points requiring:

- Human Approval
- Human Validation
- Escalation
- Exception Handling
- Manual Override

Explain why human intervention is required.


## G. MODEL RESPONSIBILITY

For each LLM/model usage identify WHY the model is needed.

Potential responsibilities include:

- classification
- planning
- reasoning
- summarisation
- generation
- extraction
- semantic matching
- recommendation
- natural-language explanation

Also identify areas where an LLM is deliberately NOT used.


## H. MCP ANALYSIS

If MCP is present, identify:

- MCP Client
- MCP Server
- MCP Tools
- Tool definitions
- Which Agent or application component acts as MCP Client
- Which MCP Server exposes which tools
- What enterprise systems those tools access
- How tool calls are initiated
- How the results are returned to the Agent
- How authentication and authorisation are controlled

Do NOT confuse:

Agent

with

MCP Client

with

MCP Server

with

Tool

with

Agent Framework.


## I. AGENT FRAMEWORK ANALYSIS

If frameworks such as:

- LangGraph
- Google ADK
- CrewAI
- PydanticAI
- Semantic Kernel
- custom orchestration

are used, explain:

- What the framework does
- Where it resides
- Whether it maintains state
- Whether it routes Agents
- Whether it manages tool calls
- Whether it provides retries/checkpoints
- Whether it manages Agent hand-offs

Do NOT describe the framework itself as a business Agent.


## J. AGENTIC JUSTIFICATION

For every Agent ask:

"Could conventional deterministic code solve this problem reliably?"

If YES:

challenge whether the Agent is necessary.

If NO:

explain what uncertainty, reasoning or dynamic decision makes the Agent
appropriate.


# ================================================================
# 8. DESIGN PHILOSOPHY
# ================================================================

The presentation is NOT a conventional PowerPoint deck.

Create it as an elegant HTML presentation experience.

Design principles:

PREMIUM.

MINIMAL.

CONFIDENT.

MODERN.

ENTERPRISE-GRADE.

VISUAL.

CINEMATIC — BUT NOT THEATRICAL.


Avoid:

- clutter
- excessive text
- template-looking cards
- rainbow colours
- unnecessary gradients
- excessive animations
- excessive icons
- stock-photo aesthetics
- PowerPoint-style bullet walls
- gimmicky AI graphics
- glowing robot imagery
- futuristic clichés
- oversized logo walls
- technical diagrams resembling circuit boards
- excessive glassmorphism
- unnecessary visual decoration


Use:

- generous whitespace
- strong typography
- visual hierarchy
- large meaningful numbers
- restrained colour palette
- subtle depth
- lightweight transitions
- meaningful diagrams
- clean data visualisation
- carefully selected background imagery where relevant
- strong headline statements
- deliberate contrast
- clear story progression


# ================================================================
# 9. CINEMATIC VISUAL DIRECTION
# ================================================================

A cinematic background may be used selectively.

It must:

- support the story
- remain subtle
- preserve readability
- look sophisticated
- never compete with content

Preferred treatment:

dark / neutral premium canvas

+

subtle light / texture / relevant domain imagery

+

soft overlay

+

high-contrast typography


Do NOT use cinematic imagery on every slide.

Content-heavy and architecture slides should preferably use cleaner
backgrounds.


# ================================================================
# 10. HTML EXPERIENCE
# ================================================================

Create the presentation as a responsive HTML experience.

Preferred behaviour:

- One slide / scene per viewport.
- Avoid long vertical pages.
- Target approximately 100vh per main presentation scene.
- Avoid scrolling wherever practical.
- Prefer horizontal or scene-based navigation.
- Allow controlled sub-scenes for technical sections where necessary.


Provide navigation through:

- LEFT / RIGHT arrow keys
- UP / DOWN arrow keys where appropriate
- SPACE
- PAGE DOWN
- PAGE UP
- navigation arrows
- clickable slide indicators
- slide number
- Home
- End


Include subtle progress indication.

Example:

06 / 11


Provide an optional compact navigation menu allowing the presenter to jump to:

- Problem
- Approach
- Research
- Solution
- Architecture
- Workflows
- Agents
- KPIs
- Guardrails
- ROI
- Gamification / Adoption
- Testing


Transitions should generally be approximately:

200–450 milliseconds.


Animations must support comprehension.

Never animate merely for decoration.


# ================================================================
# 11. APPLICATION INTEGRATION
# ================================================================

The presentation must be accessible from the main hackathon application.

Provide a clear entry point such as:

- Executive Story
- Solution Story
- Presentation
- Explore the Solution

Recommend the exact label based on the application context.


It may open:

OPTION A:

as an internal application route.

Example:

/presentation


OR


OPTION B:

as a separate presentation HTML page.


The implementation recommendation must favour whichever method causes the
least disruption to the existing MVP.


Also provide a clear:

Back to Application

control inside the presentation.


Where useful, include:

View Live Demo

or

Launch MVP

links from relevant solution slides.


Do not duplicate the application inside the presentation.

THE PRESENTATION TELLS THE STORY.

THE APPLICATION PROVES THE STORY.


# ================================================================
# 12. CONTENT DENSITY RULE
# ================================================================

The jury must be able to understand the essence of a slide within
approximately 5–8 seconds.

Therefore:

Prefer ONE primary message per slide.

Where bullets are unavoidable:

maximum 3–5 points.

Prefer approximately:

3–8 words per point.

Use short phrases instead of paragraphs.

Avoid more than approximately 30–45 visible words on most slides.

Technical architecture is an exception where labels may require additional
text.

Never shrink fonts merely to accommodate more information.

Instead:

- simplify
- visualise
- move explanation to presenter notes
- create a progressive reveal
- use supporting sub-scenes


# ================================================================
# 13. PRESENTER NOTES / EXPLAINABILITY
# ================================================================

Every presentation scene must contain presenter notes.

The notes are critical.

The visible slide should be executive-level.

The notes should explain the slide in language understandable by an intelligent
18-year-old.


For every slide provide:


### What this slide means

Simple explanation.


### What the presenter should say

Approximately 30–90 seconds depending on slide importance.


### Why it matters

Why the jury should care.


### Evidence

Which research / PRD / architecture / MVP information supports the claim.


### Architecture Detail

Where relevant explain:

- deterministic workflow
- Agentic workflow
- Agent responsibility
- tools used
- runtime sequence
- guardrails
- fallback


### Likely jury question

One or more likely questions.


### Suggested answer

A crisp, defensible answer.


Notes should NOT appear during normal presentation mode.

Provide either:

- presenter mode
- notes toggle
- hidden expandable notes panel


# ================================================================
# 14. EVIDENCE & CLAIM DISCIPLINE
# ================================================================

Do not fabricate:

- statistics
- research findings
- ROI
- performance
- accuracy
- cost savings
- industry adoption
- benchmark results
- testing results
- architecture capabilities
- Agent capabilities
- integration status
- deployment status


Classify claims internally as:

- PROVEN BY MVP
- SUPPORTED BY RESEARCH
- ESTIMATED
- ASSUMPTION
- FUTURE TARGET


Clearly distinguish these in presenter notes.

Visible slides should remain clean.


Where credible evidence exists, provide compact source references such as:

[1]

[2]


Detailed citations can appear in notes / references.


# ================================================================
# 15. REQUIRED PRESENTATION STRUCTURE
# ================================================================


# SLIDE 1 — HEADER / PRODUCT

Purpose:

Create immediate confidence and curiosity.


Visible content:

PRODUCT NAME

One-line product proposition

TEAM NAME


Optional:

one strong visual element.


Avoid generic phrases such as:

"AI-powered revolutionary platform"

"Intelligent AI solution"

"Next-generation AI system"


The proposition should communicate:

WHO it helps

+

WHAT it improves

+

WHY it matters.


------------------------------------------------


# SLIDE 2 — PROBLEM ARTICULATION

Answer:

- What is broken today?
- Who experiences the problem?
- Why is the problem important?
- What consequence does it create?


Preferred visual structure:

CURRENT REALITY
       ↓
FRICTION
       ↓
BUSINESS CONSEQUENCE


Where possible use:

one human/user problem

+

one operational problem

+

one business consequence.


Do NOT simply copy the hackathon problem statement.

Translate it into a sharp problem narrative.


------------------------------------------------


# SLIDE 3 — OVERALL APPROACH

Explain the solution philosophy before exposing detailed technology.

Preferred structure:

UNDERSTAND
      →
DECIDE
      →
ACT
      →
LEARN / IMPROVE


or another framework derived from the actual solution.


Show approximately 3–5 major solution stages.

The jury should understand the complete concept within approximately
10 seconds.


If the solution is hybrid, this slide may subtly introduce:

DETERMINISTIC CONTROL

+

AI REASONING

without showing technical detail yet.


------------------------------------------------


# SLIDE 4 — RESEARCH

This slide must demonstrate intellectual depth.

Analyse supplied research and identify:

- industry trend
- existing approaches
- current pain points
- market solutions
- limitations of those solutions
- emerging technologies
- user expectations
- regulatory considerations
- WHITE SPACE


Do NOT create a literature-review slide.


Instead present:

WHAT THE MARKET DOES

vs

WHAT REMAINS UNSOLVED

vs

OUR OPPORTUNITY


The most important output is:

THE INSIGHT THAT SHAPED OUR SOLUTION.


Use only 2–4 strong research findings.

Place detailed evidence in notes.


------------------------------------------------


# SLIDE 5 — SOLUTION: BUSINESS

Explain the product from a business/user perspective.

DO NOT start with technology.


Answer:

- Who uses it?
- What do they do?
- How does their experience change?
- Why is it better?


Preferred structure:

BEFORE
     →
OUR PRODUCT
     →
AFTER


Show approximately 3 major capabilities.


Clearly distinguish:

MVP TODAY

from

FUTURE PRODUCT VISION.


Where appropriate show:

Human / User
      ↓
Product
      ↓
Outcome


------------------------------------------------


# SLIDE 6 — TECHNICAL SOLUTION

This is the core technical chapter.

Use controlled progressive reveals or sub-scenes instead of overcrowding a
single screen.

The Technical chapter must explain:

6A. SYSTEM ARCHITECTURE

6B. WORKFLOW MODEL — DETERMINISTIC vs AGENTIC

6C. AGENT LANDSCAPE

6D. RUNTIME FLOW

6E. TECHNOLOGY STACK


# ------------------------------------------------
# 6A — SYSTEM ARCHITECTURE
# ------------------------------------------------

Show major architecture layers.

Potential layers may include:

- Experience Layer
- Application / API Layer
- Orchestration Layer
- Agentic / AI Layer
- Knowledge / RAG Layer
- Deterministic Services
- Enterprise Integration Layer
- Data Layer
- Security / Guardrails
- Observability


Only show layers actually supported by the architecture.


The architecture should answer:

WHO initiates the workflow?

WHAT coordinates it?

WHERE does AI reasoning occur?

WHERE are deterministic rules executed?

WHAT enterprise systems are accessed?

WHERE is data stored?

WHERE are guardrails applied?

HOW does the response return to the user?

WHAT framework orchestrates the workflow?

WHO holds workflow state?


If MCP is present, explicitly show:

APPLICATION / AGENT
        ↓
MCP CLIENT
        ↓
MCP SERVER
        ↓
TOOLS
        ↓
ENTERPRISE SYSTEM


Use the actual architecture, not this illustrative example.


# ------------------------------------------------
# 6B — WORKFLOW MODEL
# ------------------------------------------------

Create a visual that explicitly distinguishes:

DETERMINISTIC

vs

AGENTIC

vs

HYBRID.


Illustrative example:

USER REQUEST
      ↓
INPUT VALIDATION
[DETERMINISTIC]
      ↓
INTENT / PLANNING
[AGENTIC]
      ↓
TOOL / DATA RETRIEVAL
[HYBRID]
      ↓
BUSINESS RULE CHECK
[DETERMINISTIC]
      ↓
REASONING / RESPONSE
[AGENTIC]
      ↓
OUTPUT VALIDATION
[DETERMINISTIC]
      ↓
USER


This is illustrative only.

Build the actual flow from the supplied architecture.


Visually differentiate Agentic and deterministic execution without creating
visual clutter.


The jury should immediately understand:

"AI is not running everything."


Where accurate, a strong supporting message may be:

"Reasoning where needed. Determinism where control matters."


Do not use this wording if the architecture does not support it.


# ------------------------------------------------
# 6C — AGENT LANDSCAPE
# ------------------------------------------------

Show the Agents actually used in the solution.

Do NOT create a logo-style collection of Agents.

Show:

- relationships
- responsibilities
- tool access
- orchestration pattern


Illustrative structure:

ORCHESTRATOR / PLANNER
          ↓

     ┌────────────┐
     │            │
DOMAIN AGENT   KNOWLEDGE AGENT
     │            │
     └──────┬─────┘
            ↓
    VALIDATION / ACTION


Use the actual Agent structure extracted from the architecture.


For each Agent show only:

AGENT NAME

ONE-LINE RESPONSIBILITY

PRIMARY TOOLS


Detailed information belongs in presenter notes.


Presenter notes must contain:

- Purpose
- Input
- Decision responsibility
- Tools
- Data accessed
- Output
- Handoff
- Guardrails
- Fallback
- Why this is an Agent


Also explain:

WHY THIS IS AN AGENT

rather than conventional application code.


If only one Agent exists, do not invent multiple Agents.

If the application uses one Agent with multiple tools, say exactly that.


# ------------------------------------------------
# 6D — RUNTIME / EXECUTION FLOW
# ------------------------------------------------

Take ONE representative user/business scenario.

Trace it end-to-end through the architecture.


Show:

1. Request enters system
2. Authentication / validation
3. Workflow initiation
4. Agent or deterministic processing
5. Tool invocation
6. Knowledge / data retrieval
7. Business rules
8. Decision / reasoning
9. Guardrails
10. Output / action


At every major step label execution as:

[D] Deterministic

[A] Agentic

[H] Hybrid


Illustrative example:

Customer Request
      ↓
[D] Authentication
      ↓
[A] Planning Agent
      ↓
[H] Tool Orchestration
      ↓
[D] Business Policy Validation
      ↓
[A] Explanation Generation
      ↓
[D] Output Guardrail
      ↓
Response


Derive the real flow from the supplied architecture.


If a framework such as LangGraph or Google ADK manages runtime state,
show where it fits.

If MCP is used, show where the MCP Client calls the MCP Server.

If RAG is used, show:

Query
  ↓
Retrieval
  ↓
Relevant Context
  ↓
Model / Agent

Do not hide RAG inside a generic "AI Engine" box.


# ------------------------------------------------
# 6E — TECHNOLOGY STACK
# ------------------------------------------------

Map technologies to responsibilities rather than simply displaying logos.


Example:

EXPERIENCE

React / Next.js


APPLICATION

FastAPI / Node / Spring


ORCHESTRATION

LangGraph / Google ADK / custom orchestration


AI

LLM(s)


AGENTS

Agent implementations


KNOWLEDGE

Embedding model / Vector DB / RAG


DATA

PostgreSQL / SQLite


ENTERPRISE INTEGRATION

REST / Kafka / MCP / APIs


OBSERVABILITY

Logging / Metrics / Tracing


Only include technology actually used.


Where MCP is present, clearly identify:

- MCP CLIENT
- MCP SERVER
- TOOLS EXPOSED THROUGH MCP


Where an Agent framework is used, state its precise architectural role.

Do NOT present the Agent framework as the Agent itself.


------------------------------------------------


# SLIDE 7 — KPIs

KPIs must prove whether the solution works.

Avoid vanity metrics.


Organise into approximately three groups:

BUSINESS

USER / EXPERIENCE

TECHNOLOGY / AI


Potential examples only where relevant:


Business:

- cost saved
- revenue generated
- productivity improvement
- process time reduction
- error reduction


Experience:

- response time
- completion rate
- customer satisfaction
- user adoption
- task success


AI / Technical:

- grounded answer rate
- hallucination rate
- latency
- cost per transaction
- tool success rate
- routing accuracy
- retrieval quality
- Agent task completion rate
- reliability
- fallback frequency


For each KPI internally define:

CURRENT BASELINE

TARGET

HOW IT IS MEASURED


Do not invent baseline values if none exist.


------------------------------------------------


# SLIDE 8 — GUARDRAILS

Demonstrate responsible enterprise AI.

Cover only relevant controls.


Potential areas:


INPUT

- prompt injection protection
- validation
- PII masking
- authentication
- authorisation


PROCESS

- grounding
- deterministic rules
- restricted tool access
- policy checks
- model routing
- human approval where required
- Agent permission boundaries


OUTPUT

- validation
- hallucination controls
- policy compliance
- sensitive-data protection
- citation
- schema validation


OPERATIONS

- audit logging
- monitoring
- rate limiting
- fallback
- incident traceability
- Agent tracing
- tool-call tracing


Preferred visual:

INPUT
  ↓
REASONING
  ↓
ACTION
  ↓
OUTPUT


with guardrails around the lifecycle.


Explicitly show where deterministic controls constrain Agentic behaviour.


------------------------------------------------


# SLIDE 9 — BUSINESS ROI / FINOPS

Answer:

Why is this economically meaningful?


Use:

BENEFIT

minus

COST

equals

BUSINESS VALUE.


Potential benefit categories:

- hours saved
- productivity
- reduced error
- revenue improvement
- avoided cost
- faster cycle time
- higher conversion
- reduced support workload


Potential cost categories:

- LLM / token usage
- embedding usage
- infrastructure
- vector storage
- APIs
- engineering
- monitoring
- maintenance


Where exact information is unavailable create:

ILLUSTRATIVE ROI MODEL


and explicitly label assumptions.


Include where relevant:

- Cost per transaction
- Cost per user
- Monthly operating cost
- Break-even scenario
- Scale economics
- Model cost
- Agent execution cost
- Tool/API cost


Show numbers visually.

Avoid spreadsheet-like density.


Where relevant explain how deterministic workflows reduce:

- model calls
- token usage
- latency
- cost


------------------------------------------------


# SLIDE 10 — GAMIFICATION

Do not add gamification merely because this slide exists.

First determine whether gamification is relevant to the solution.

If relevant, design meaningful behaviour reinforcement.


Potential mechanisms:

- progress
- streak
- achievement
- level
- learning milestone
- adoption score
- team challenge
- recognition


Explain the behavioural purpose.


Example:

ACTION
 ↓
FEEDBACK
 ↓
PROGRESS
 ↓
REWARD
 ↓
REPEAT


Avoid childish graphics unless the end-user context genuinely supports them.


If gamification is NOT appropriate for the solution, explicitly recommend
replacing this slide with a more strategically useful topic such as:

- Adoption
- Scale Roadmap
- Differentiation
- Future Vision
- Change Management
- Enterprise Rollout


Do not blindly force a weak gamification story.


------------------------------------------------


# SLIDE 11 — TESTING & PROOF

This slide must increase confidence that the system genuinely works.


Separate:


FUNCTIONAL TESTING

Examples:

- workflow tests
- Agent tests
- tool tests
- API tests
- business rules
- RAG retrieval
- integration tests
- failure scenarios
- Agent hand-off tests


NON-FUNCTIONAL TESTING

Examples:

- response latency
- load
- scalability
- security
- reliability
- recoverability
- model cost
- observability
- accessibility


AI-SPECIFIC QUALITY

where applicable:

- grounding
- hallucination
- prompt-injection resistance
- retrieval quality
- answer relevance
- citation accuracy
- tool-selection accuracy
- Agent routing accuracy
- Agent task completion
- fallback handling


DETERMINISTIC WORKFLOW TESTING

where applicable:

- rule validation
- boundary cases
- calculations
- state transitions
- API validation
- deterministic outputs


Show:

TEST
     →
EVIDENCE
     →
CONFIDENCE


Where actual test results exist, show them.

Where testing is future work, never imply it has already been completed.


# ================================================================
# 16. ENDING
# ================================================================

Although Slide 11 is the final required section, create a powerful closing
state within the final experience.

Do NOT end abruptly on testing.


After the testing content, transition to a minimal final frame containing:

PRODUCT NAME

one memorable value proposition


and optionally:

LIVE DEMO

or

QUESTIONS


The closing message should connect back to the original problem.


The audience should remember:

THE PROBLEM

THE DIFFERENCE

THE VALUE.


# ================================================================
# 17. EXECUTIVE COMMUNICATION RULE
# ================================================================

Every slide must pass this test:

If the CEO reads only the title and the largest sentence,
will the core message still be understood?

If not:

rewrite the slide.


# ================================================================
# 18. TECHNICAL CREDIBILITY RULE
# ================================================================

Every architecture statement must be defensible.

Avoid vague phrases such as:

- AI Engine
- Smart Layer
- Intelligent Module
- AI Brain
- Magic Orchestrator

unless the underlying component is explicitly explained.


Use precise terminology.


For every architecture box determine:

- What is it?
- What does it do?
- What does it receive?
- What does it produce?
- Who invokes it?
- Is it deterministic or Agentic?
- Which technologies implement it?


# ================================================================
# 19. DIFFERENTIATION / WHITE-SPACE RULE
# ================================================================

The research must identify:

WHAT ALREADY EXISTS

WHAT THOSE SOLUTIONS DO WELL

WHAT THEY FAIL TO ADDRESS

WHY THE GAP MATTERS

HOW OUR DESIGN ADDRESSES THE GAP


Never claim:

"there is no existing solution"

unless research genuinely demonstrates this.


# ================================================================
# 20. MVP VS VISION
# ================================================================

Never blur prototype capabilities with future capabilities.


Use this model:


NOW

What the MVP proves.


NEXT

What is realistically achievable.


LATER

What the platform could become.


This separation creates credibility.


# ================================================================
# 21. DEMO INTEGRATION
# ================================================================

Identify the strongest moment to move from presentation to MVP.


Recommend:

- WHEN TO LAUNCH THE DEMO
- WHAT USER SCENARIO TO DEMONSTRATE
- WHAT THE PRESENTER SHOULD SAY BEFORE THE DEMO
- WHAT THE AUDIENCE SHOULD NOTICE
- HOW TO RETURN TO THE STORY AFTER THE DEMO


Avoid feature-tour demos.


Use ONE compelling end-to-end scenario.


Where technically useful, the demo narration should briefly explain:

[D] Deterministic

[A] Agentic

[H] Hybrid

without slowing down the demo.


# ================================================================
# 22. DESIGN SYSTEM
# ================================================================

Create a lightweight reusable design system.


Define:


TYPOGRAPHY

- Heading
- Subheading
- Body
- Metric
- Caption


SPACING

Use a consistent spacing rhythm.


GRID

Use a consistent underlying layout.


COLOUR

Define:

- Primary background
- Primary text
- Secondary text
- One accent colour
- Optional semantic colours


Use semantic visual differentiation for:

DETERMINISTIC

AGENTIC

HYBRID


but keep the overall palette restrained.


CARDS

Use sparingly.


ICONS

Use only where they increase comprehension.


CHARTS

- Simple
- Large labels
- Minimal grid lines
- No decorative complexity


DIAGRAMS

Use consistent visual language for:

- User
- Agent
- Deterministic Service
- Tool
- Database
- External System
- Model
- Guardrail
- MCP Server
- Orchestrator


# ================================================================
# 23. RESPONSIVENESS
# ================================================================

Primary optimisation:

16:9 laptop / projector presentation.


Also remain usable on:

- desktop
- tablet
- smaller screens


Do not sacrifice presentation quality merely to make every scene look identical
on a phone.


# ================================================================
# 24. ACCESSIBILITY
# ================================================================

Ensure:

- strong text contrast
- readable font sizes
- keyboard navigation
- visible focus states
- semantic HTML
- ARIA labels where appropriate
- reduced-motion compatibility


# ================================================================
# 25. PERFORMANCE
# ================================================================

The presentation must load quickly.

Avoid unnecessary large libraries.


Optimise:

- images
- fonts
- JavaScript
- animation
- external dependencies


Presentation failure during judging is unacceptable.

Where possible support local/offline execution.


# ================================================================
# 26. IMPLEMENTATION CONSTRAINTS
# ================================================================

Do NOT destabilise the existing MVP.


Before coding:

inspect the current repository.


Identify:

- framework
- project structure
- routing
- design system
- build process
- dependencies
- application shell
- existing assets


Reuse existing technologies wherever sensible.


Do not introduce a large dependency merely for presentation effects.


Prefer:

- HTML
- CSS
- existing application framework
- minimal JavaScript


The presentation must be easy to launch during judging.


# ================================================================
# 27. JURY QUESTION PREPARATION
# ================================================================

After creating the presentation generate a separate jury preparation section.


Include approximately:

- 5 Executive questions
- 5 Business / Product questions
- 10 Architecture / Engineering questions
- 5 AI / Responsible-AI questions
- 5 Scale / ROI questions


For every question provide:

WHY THEY MAY ASK IT

30-SECOND ANSWER

DEEP-DIVE ANSWER


Pay particular attention to difficult questions such as:

- Why AI?
- Why an Agent rather than workflow automation?
- Why is this workflow deterministic?
- Why is this workflow Agentic?
- Why not make the complete workflow Agentic?
- How many Agents are there?
- What does each Agent actually do?
- Which Agent decides what?
- What tools can each Agent access?
- Who orchestrates the Agents?
- Where does the orchestration framework reside?
- What is the difference between the Agent and LangGraph / Google ADK?
- Where does MCP fit?
- Which component is the MCP Client?
- Which component is the MCP Server?
- What tools are exposed through MCP?
- What happens when an Agent fails?
- What happens when an LLM fails?
- How do you prevent an Agent from taking an unsafe action?
- How is hallucination controlled?
- How does RAG work in this architecture?
- How does the solution scale?
- How is data protected?
- What is proprietary or differentiated?
- What is the cost at scale?
- What exactly has been implemented?
- What remains conceptual?


# ================================================================
# 28. REQUIRED OUTPUT — PHASE 1: ANALYSIS
# ================================================================

Before creating HTML, return:


A. CORE PROBLEM

Core problem in one sentence.


B. USER / BUSINESS PAIN

Describe the primary pain.


C. RESEARCH INSIGHT

What did research reveal?


D. WHITE SPACE

What remains insufficiently solved?


E. PRODUCT INSIGHT

What design insight shaped the product?


F. VALUE PROPOSITION

Proposed value proposition.


G. DIFFERENTIATION

What is genuinely differentiated?


H. MVP PROOF

Strongest MVP proof point.


I. ARCHITECTURE DECISION

Most important architecture decision.


J. TOP KPIs

Top 5 KPIs.


K. MAIN RISKS

Main risks.


L. JURY NARRATIVE

Recommended jury narrative.


M. CONTRADICTIONS / MISSING EVIDENCE

Identify contradictions or missing evidence across:

- Problem Statement
- Research
- PRD
- Architecture
- MVP


Do not hide inconsistencies.

Flag them.


N. SYSTEM WORKFLOW CLASSIFICATION

Summarise:

- Number of major deterministic workflows
- Number of major Agentic workflows
- Number of hybrid workflows


Overall design classification:

- DETERMINISTIC-FIRST
- AGENTIC-FIRST
- HYBRID


O. WORKFLOW INVENTORY

Provide:

| Workflow | Type | Trigger | Key Steps | Agent Involvement | Deterministic Controls | Output |
|---|---|---|---|---|---|---|


P. AGENT INVENTORY

Provide:

| Agent | Responsibility | Tools | Input | Output | Why Agentic? |
|---|---|---|---|---|---|


Q. DETERMINISTIC COMPONENT INVENTORY

Provide:

| Component | Responsibility | Why Deterministic? |
|---|---|---|


R. AGENT ORCHESTRATION PATTERN

State whether the system uses:

- Single Agent
- Planner / Executor
- Supervisor / Workers
- Sequential Agents
- Parallel Agents
- Router
- Hierarchical Agents
- Agent + Tools
- Agent + Deterministic Services
- Hybrid orchestration
- another pattern


Explain why.


S. AI CONTROL BOUNDARY

Clearly explain:

What AI CAN decide.

What AI CANNOT decide.


T. REPRESENTATIVE RUNTIME FLOW

Provide one end-to-end execution flow labelled:

[D] Deterministic

[A] Agentic

[H] Hybrid


U. MCP MODEL

If MCP exists, provide:

| Component | Role |
|---|---|
| MCP Client | |
| MCP Server | |
| MCP Tools | |
| Tool Consumers | |
| Enterprise Systems Accessed | |


V. FRAMEWORK ROLE

If LangGraph / Google ADK / CrewAI / PydanticAI / another framework is used,
explain its exact role.


# ================================================================
# 29. REQUIRED OUTPUT — PHASE 2: STORYBOARD
# ================================================================

Create the complete presentation storyboard.


For every slide specify:

SLIDE NUMBER

SLIDE TITLE

ONE-SENTENCE TAKEAWAY

VISIBLE CONTENT

VISUAL CONCEPT

SOURCE / EVIDENCE

PRESENTER NOTES

LIKELY JURY QUESTION

TRANSITION TO NEXT SLIDE


Do this BEFORE final HTML generation.


# ================================================================
# 30. REQUIRED OUTPUT — PHASE 3: DESIGN SPECIFICATION
# ================================================================

Provide:

- Colour System
- Typography
- Spacing
- Grid
- Background Treatment
- Animation Principles
- Navigation Design
- Diagram Language
- Agent Visual Language
- Deterministic Workflow Visual Language
- Hybrid Workflow Visual Language
- Chart Language
- Notes Interaction
- Application Integration Approach


# ================================================================
# 31. REQUIRED OUTPUT — PHASE 4: HTML IMPLEMENTATION
# ================================================================

Generate production-quality presentation code.


Depending on the existing application architecture, create the appropriate:

- HTML
- CSS
- JavaScript
- React components
- Next.js components
- equivalent components


while minimising changes to the existing application.


Include:

- keyboard navigation
- navigation controls
- progress indicator
- slide numbering
- notes mode
- full-screen compatibility
- application return navigation
- demo links where relevant
- responsive behaviour
- reduced-motion support


The final implementation must be maintainable and easy to run.


# ================================================================
# 32. REQUIRED OUTPUT — PHASE 5: QUALITY REVIEW
# ================================================================

After creating the presentation, critically review it as if you were each of
the following judges:

- CEO
- CTO
- Enterprise Architect
- Product Leader
- Business Leader


For every persona answer:

What will impress them?

What may confuse them?

What may cause them to challenge us?

What should be improved?


Then revise the presentation.


# ================================================================
# 33. FINAL QUALITY GATES
# ================================================================

Do NOT consider the work complete until all gates pass.


GATE 1 — 5-SECOND TEST

Can each slide's core message be understood in five seconds?


GATE 2 — EXECUTIVE TEST

Can a CEO understand the complete story without understanding AI?


GATE 3 — ARCHITECTURE TEST

Can a CTO defend the architecture?


GATE 4 — EVIDENCE TEST

Are important claims supported by evidence or clearly labelled assumptions?


GATE 5 — MVP TEST

Is it completely clear what has actually been built?


GATE 6 — ROI TEST

Can the value hypothesis be quantified?


GATE 7 — DESIGN TEST

Does the presentation look intentionally designed rather than generated?


GATE 8 — DENSITY TEST

Can unnecessary words be removed?


GATE 9 — STORY TEST

Does every slide naturally lead to the next?


GATE 10 — MEMORABILITY TEST

Will the jury remember the product and its central idea after seeing
30+ competing teams?


GATE 11 — AGENTIC NECESSITY TEST

For every Agent:

Can we clearly explain why an Agent is required?

If ordinary deterministic code can perform the task more reliably,
the architecture should not use an Agent merely to make the solution appear
more sophisticated.


GATE 12 — WORKFLOW CLARITY TEST

Can an Enterprise Architect understand within 30 seconds:

Which workflows are deterministic?

Which are Agentic?

Which are hybrid?


GATE 13 — AGENT RESPONSIBILITY TEST

Does every Agent have:

- a clear purpose
- defined inputs
- defined tools
- defined outputs
- a clear decision boundary
- fallback behaviour


GATE 14 — CONTROL TEST

Are high-risk business decisions protected through:

- deterministic validation
- policy checks
- guardrails
- human approval

where appropriate?


GATE 15 — ORCHESTRATION TEST

Can we clearly explain:

- Who invokes each Agent?
- How Agents communicate?
- Who maintains workflow state?
- How tool calls occur?
- What happens when an Agent or tool fails?


GATE 16 — MCP CLARITY TEST

If MCP exists, can we clearly distinguish:

- MCP Client
- MCP Server
- MCP Tool
- Agent
- Agent Framework
- Enterprise System?


GATE 17 — FRAMEWORK CLARITY TEST

Can we clearly explain what LangGraph / Google ADK / other orchestration
technology does without confusing it with the Agent itself?


GATE 18 — DETERMINISTIC CONTROL TEST

Can we show where deterministic code deliberately constrains AI behaviour?


# ================================================================
# 34. ABSOLUTE RULE
# ================================================================

DO NOT optimise for the amount of information displayed.

OPTIMISE FOR:

UNDERSTANDING

+

CREDIBILITY

+

DIFFERENTIATION

+

MEMORABILITY

+

BUSINESS VALUE

+

TECHNICAL DEFENSIBILITY.


The presentation is successful only if a senior jury can quickly answer:


WHAT PROBLEM ARE THEY SOLVING?

WHY DOES IT MATTER?

WHAT HAVE THEY BUILT?

WHAT DID THEIR RESEARCH REVEAL?

WHAT IS DIFFERENT ABOUT THEIR APPROACH?

WHICH PARTS ARE DETERMINISTIC?

WHICH PARTS ARE AGENTIC?

WHY ARE AGENTS NEEDED?

WHAT DOES EACH AGENT DO?

WHO ORCHESTRATES THEM?

HOW ARE TOOLS CALLED?

WHERE DOES MCP FIT, IF USED?

WHAT DOES THE AI DECIDE?

WHAT DOES THE AI NOT DECIDE?

DOES THE SOLUTION ACTUALLY WORK?

IS IT SAFE?

CAN IT SCALE?

WHAT VALUE CAN IT CREATE?

WHY SHOULD THIS TEAM WIN?


# ================================================================
# 35. FINAL ARCHITECTURE MESSAGE
# ================================================================

Where supported by the actual implementation, communicate the architecture
using this philosophy:


DETERMINISTIC WHERE WE KNOW THE ANSWER.

AGENTIC WHERE THE SYSTEM NEEDS TO REASON.

GUARDRAILED WHEREVER AI CAN TAKE ACTION.


The technical story should make clear that:

AI determines how to solve uncertain or contextual parts of the problem.

Deterministic engineering controls what the system is allowed to do.

The combination creates an architecture that is:

INTELLIGENT

CONTROLLED

EXPLAINABLE

ECONOMIC

AND

ENTERPRISE-READY.
