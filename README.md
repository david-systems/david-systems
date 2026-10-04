# David — LLM Evaluation & AI Engineering

I design production-style evaluations that measure where **LLM agents succeed, fail, and behave unpredictably**.

I bring 15+ years of experience building and operating e-commerce systems to **LLM evaluation, coding agents, deterministic behavioral grading, and agent reliability**.

## Featured Project — LLM Coding Agent Evaluation 2.0

**Can an AI coding agent safely add a complex feature to an unfamiliar application without breaking existing behavior?**

I built a production-style evaluation around **Northstar Outdoor Living**, a fictional commerce application. A coding agent must implement a complex promotion system while a held-out evaluator measures business correctness, regressions, concurrency, payment behavior, interoperability, and other observable outcomes.

**335 deterministic assertions · 17 grader families · reproducible sealed trials**

| Candidate | PASS | FAIL | BLOCKED |
|---|---:|---:|---:|
| GPT-5.6 Luna / Codex | 168 | 104 | 63 |
| GPT-5.6 Sol High / Codex | 334 | 1 | 0 |
| Claude Sonnet 5.5 High / Claude Code | **335** | **0** | **0** |
| Claude Haiku 4.5 / Claude Code | 58 | 64 | 213 |

**Repository:** [LLM Coding Agent Evaluation](https://github.com/david-systems/llm-eval-coding-agent)

## How This Project Evolved

This project began with a smaller **[Promotion Evaluation 1 pilot](https://github.com/david-systems/llm-eval-promotions-pilot)**, based on promotion problems I encountered in real e-commerce systems.
The pilot caught genuine coding failures, but it exposed a harder evaluation problem: **how do you know the grader itself is fair?**

I rebuilt the evaluation as 2.0 around several lessons:

- **Requirements traceability** — graded behavior must trace to candidate-visible requirements.
- **Solution-independent grading** — evaluate outcomes, not a preferred schema, algorithm, or code structure.
- **Grader validation** — test the evaluator against valid, invalid, and alternative-valid solutions.
- **Failure attribution** — distinguish candidate FAILs from BLOCKED scenarios and evaluator ERRORs.
- **Reproducibility** — verify the starting environment, isolate trials, seal submissions, and preserve provenance.

I also audited the new evaluator itself and removed assumptions that depended on candidate-owned database structures and implementation details.

The result wasn't just a harder benchmark; it was a much stronger **evaluation methodology**.

## What the Experiments Taught Me

Four independent candidate trials produced sharply different outcomes. GPT-5.6 Luna passed **168 of 335** assertions, while Claude Haiku 4.5 passed **58**, with many downstream checks blocked by unmet prerequisites. At the other end, GPT-5.6 Sol High passed **334 of 335**, and Claude Sonnet 5.5 High passed **335 of 335**.

The spread shows that the evaluation can distinguish substantial differences in candidate performance, while the near-perfect and perfect results show that **this particular task is reaching saturation for the strongest candidates tested**.

Rather than manufacture increasingly obscure promotion edge cases, I'm using that finding to move the next evaluation toward a harder capability: determining the correct action when evidence is distributed across systems, documentation, organizational conventions, and partially conflicting information.

## Next — MCP & Organizational Reasoning Evaluation

The next project expands Northstar into a larger organizational environment and evaluates agents working across company systems and information sources:

- **Model Context Protocol (MCP)** tools and resources;
- company standards and conventions distributed across documentation and systems;
- stale, conflicting, and incomplete information;
- evidence reconciliation and grounded decisions;
- permissions and authorization;
- cross-system, longer-horizon agent behavior.

*This evaluation is currently in development.*

## Evaluation Approach

**Capability → Requirements → Success Properties → Graders → Assertions → Results**

I prefer deterministic behavioral grading where outcomes can be objectively verified, keep measurement solution-independent, preserve observable evidence and traces, and treat the evaluator itself as software that must be **tested, validated, versioned, and corrected**.

## Background

I spent 15+ years building and operating e-commerce systems, including application architecture, databases, integrations, checkout systems, production troubleshooting, and business operations. I'm now applying that production experience to **LLM evaluation and AI agent engineering**.

I use coding agents extensively for implementation and iteration. My role centers on evaluation design, requirements and success criteria, experimental boundaries, grading methodology, validation, technical review, and failure analysis.
