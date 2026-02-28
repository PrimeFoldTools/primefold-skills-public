# Open-Source Claude Skills

Modular AI skills for decision-making, analysis, and content strategy — built for Claude Code and adaptable to any LLM agent workflow.

## What Are Skills?

Skills are modular instruction sets that give AI agents specialized capabilities. Each skill contains a `SKILL.md` file (and optional `references/` directory) that loads domain expertise, decision frameworks, and execution patterns into your AI workflow.

These skills work natively with **Claude Cowork** and can be adapted for any LLM-based agent system.

## Included Skills

| Skill | Description |
|-------|-------------|
| **8020-analysis** | Pareto principle analyzer — finds the vital few from the trivial many across products, features, channels, and time allocation |
| **copy-crafter** | Diagnostic-first copywriting engine using Ogilvy, Schwartz, and Halbert frameworks. Two modes: FAST (iteration) and FULL (new offers) |
| **doc-coauthoring** | Structured 3-stage workflow for collaborative document creation: Context Gathering → Refinement → Reader Testing |
| **factguard-pro** | Adaptive verification system for detecting AI hallucinations, misinformation, and manipulation across multiple threat vectors |
| **forge** | Content intelligence system that transforms ideas into platform-native content strategies with intent-based distribution |
| **hormozi-offers** | Grand Slam Offer construction using the Hormozi value equation: Dream Outcome, Perceived Likelihood, Time Delay, and Effort |
| **reddit-risk-evaluator** | Mechanical risk scorer for Reddit posts and comments. Quantitative assessment with structured YAML output |
| **research-swarm** | Multi-model research orchestration — generates optimized prompts for 10+ AI models based on their unique strengths |

## Installation (Claude Cowork)

Drop any skill folder into your Cowork skills directory:

```
~/.skills/skills/your-skill-name/SKILL.md
```

Skills auto-load when their trigger conditions are met during conversation.

## Structure

```
skills/
├── skill-name/
│   ├── SKILL.md              # Core skill instructions
│   └── references/           # Supporting knowledge (optional)
│       ├── examples.md
│       └── framework.md
```

## License

MIT — use freely, build on top, ship what works.
