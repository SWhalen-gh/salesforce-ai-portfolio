# Salesforce &amp; Agentforce AI Portfolio

<!-- Replace with your name and contact line -->
Sean Whalen— Salesforce engineering leader, ~10 years on the platform

Four independent projects showing hands-on work across the building blocks of enterprise conversational AI on Salesforce: **Agentforce**, **Data Cloud / Data 360**, **Model Context Protocol (MCP)**, and **Retrieval-Augmented Generation (RAG)**. Each pairs a deterministic engine with an LLM at the natural-language edge — the architecture pattern behind reliable enterprise AI.

**Selected certifications** · Salesforce Platform Developer I · Agentforce Specialist · Agentforce Associate

> These are independent, self-built projects in a Salesforce developer org — not client deliverables. They exist to demonstrate capability across the platform's AI stack.

---

## Polymarket narrative — RAG over Data Cloud

An Apex scheduled job polls the Polymarket API hourly and posts each batch into Data 360 as a time-series of text records annotated with numeric metrics. When prompted by a user via Agentforce, the records matching a date filter are retrieved and handed to the Prompt Template as RAG context; the model reads the deltas between metric snapshots to decide which parts of the story to foreground, producing a narrative summary weighted by what actually moved. It's an example of RAG from a Data Cloud store, with retrieval scoped by a time window.

![Agentforce delivering a metric-weighted economic narrative summary](assets/polymarket-narrative.png)

**Demonstrates** · Agentforce · Data Cloud / Data 360 · RAG · scheduled Apex · REST integration

<!-- Write-up: add LinkedIn URL here -->

---

## Crossword generator (LWC) — procedural engine + Prompt Template clues

A Lightning Web Component fills a crossword grid using a classic backtracking search: placing words, detecting conflicts, and unwinding when a branch fails. Alongside the grid, a Salesforce Prompt Template generates clues for the placed words, tuned to characteristics the user selects, so the same answer can be clued plain or cryptic, easy or whimsical. One LWC with two technologies: the procedural engine does the puzzle and the LLM does the language.

![Crossword LWC: solved grid on the left, generated clues and difficulty/whimsy controls on the right](assets/crossword-lwc.png)

**Demonstrates** · Lightning Web Components · Prompt Builder / Prompt Templates · generative AI · deterministic-vs-LLM design

<!-- Write-up: add LinkedIn URL here -->

---

## MCP Escape Room — agentic tool use on Salesforce

A custom Apex-hosted MCP server exposes seven single-object tools, deliberately scoped so the LLM has to discover each tool and leverage them to get out of the room. State is threaded between calls as an encrypted token, so the server holds no session and the reasoning lives entirely in the model (here, Claude as the MCP client). Because the tool descriptions can be made more or less guiding, the project doubles as an instrument for observing how a model copes with rising ambiguity — and for contrasting that probabilistic behavior against a strictly deterministic client running a fixed script.

![The path Claude reasons through to escape the room](assets/escape-room-path.svg)

![Architecture: one Apex MCP server exposing seven single-object tools, with encrypted state threaded back to the client each call](assets/escape-room-architecture.svg)

**Demonstrates** · Model Context Protocol · Apex-hosted tools (Headless-360-style exposure) · agentic orchestration · Anthropic Claude

<!-- Write-up: add LinkedIn URL here -->

---

## Letter Boxed solver — Agentforce over a SQL solver

Agentforce sits between the player and a large SQL query that solves the NYT Letter Boxed puzzle against a ~300,000-word dictionary held in Data 360. The agent turns the player's input into the query, returns a solution, and then stays in the conversation — once solved, the user can ask for definitions or usage and get them back in natural language. The division of labor is the point: Agentforce owns the natural-language edge while the heavy combinatorial work stays in deterministic SQL.

![Agentforce solving a Letter Boxed puzzle, then defining a word from the solution](assets/letterboxed-solver.png)

**Demonstrates** · Agentforce · Data Cloud / Data 360 · conversational AI · deterministic business logic

<!-- Write-up: add LinkedIn URL here -->

---

<!-- Optional: contact / LinkedIn / email line -->
