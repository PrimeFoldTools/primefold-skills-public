---
name: research-swarm
description: Multi-model research orchestration that generates optimized prompts for 10+ AI models based on their unique strengths, enabling comprehensive topic coverage from multiple perspectives. Use when researching complex topics, gathering diverse viewpoints, or needing depth across technical, practical, academic, and contrarian angles. Outputs model-specific prompts for DeepSeek, Claude, Gemini, Perplexity, Grok, ChatGPT, Kimi, Notebook LM, Elicit, and Poe, plus synthesis protocol.
---

# Research Swarm

Multi-model research orchestration system. Coordinates 10+ AI models to research topics from complementary angles, leveraging each model's unique strengths for comprehensive coverage.

## When to Use

**Triggers:**
- "Research [topic] comprehensively"
- "Get multiple perspectives on [question]"
- "Deep dive into [subject]"
- "Gather diverse viewpoints on [issue]"
- Starting any substantial research project
- Need technical + practical + academic + contrarian angles

**Use when:**
- Topic requires depth and breadth
- Multiple perspectives valuable
- Want to identify consensus vs. contradictions
- Building comprehensive understanding
- Preparing strategic decisions
- Creating research-backed content

**Don't use when:**
- Simple factual lookup (just use Perplexity)
- Single perspective sufficient
- Time-constrained quick answer needed
- Topic too narrow for multi-angle analysis

---

## How It Works

**Input:** Research topic or question  
**Process:** Generate 10 model-specific prompts optimized for each model's strengths  
**Output:** Complete prompt set + synthesis instructions

**Workflow:**
1. User provides research topic
2. Skill generates 10 optimized prompts
3. User copies/pastes prompts to each model manually
4. User collects responses
5. User synthesizes using provided protocol

**Execution time:** 5 min generation, 20-40 min model coordination, 30-60 min synthesis

---

## Model Strengths & Prompt Patterns

### 1. DeepSeek (Technical Depth)

**Strengths:**
- Mathematical rigor and formalization
- Code examples and implementation details
- Technical precision and edge case analysis
- Cost-effective for long-form technical content

**Optimal for:**
- Technical architecture analysis
- Mathematical frameworks
- Code implementation patterns
- Edge case identification

**Prompt Pattern:**
```
Analyze [TOPIC] with technical precision and depth:

1. Technical Foundations
   - Core concepts and definitions
   - Mathematical formalization (where applicable)
   - System architecture and components

2. Implementation Details
   - Code examples and patterns
   - Technical specifications
   - Integration considerations

3. Edge Cases & Limitations
   - Boundary conditions
   - Failure modes
   - Performance constraints
   - Scalability considerations

4. Technical Comparisons
   - Alternative approaches
   - Trade-off analysis
   - Benchmarks and metrics

Provide code snippets, formulas, and technical diagrams where relevant.
```

---

### 2. Claude (Nuanced Synthesis)

**Strengths:**
- Balanced, multi-perspective analysis
- Nuanced reasoning and implications
- Connecting historical context to current state
- Ethical and philosophical considerations

**Optimal for:**
- Comprehensive synthesis
- Multi-stakeholder perspectives
- Trade-off analysis
- Strategic implications

**Prompt Pattern:**
```
Provide comprehensive analysis of [TOPIC]:

1. Historical Context
   - Evolution of thinking on this topic
   - Key milestones and inflection points
   - Lessons from past approaches

2. Multiple Perspectives
   - Technical/engineering view
   - Business/economic view
   - Social/ethical view
   - Regulatory/governance view

3. Current State Analysis
   - Consensus positions
   - Ongoing debates
   - Emerging trends
   - Unresolved questions

4. Implications & Trade-offs
   - Short-term vs. long-term considerations
   - Stakeholder impacts
   - Second-order effects
   - Strategic decisions required

Balance depth with accessibility. Identify nuance and complexity.
```

---

### 3. Gemini (Cross-Domain Connections)

**Strengths:**
- Multimodal integration (text, images, data)
- Connecting disparate domains
- Pattern recognition across fields
- Broad knowledge synthesis

**Optimal for:**
- Cross-disciplinary insights
- Pattern identification
- Analogical reasoning
- Connecting theory to practice

**Prompt Pattern:**
```
Explain [TOPIC] by connecting multiple domains and perspectives:

1. Core Concepts
   - Fundamental principles
   - Key terminology
   - Mental models

2. Cross-Domain Parallels
   - How does this relate to [analogous field]?
   - What patterns appear across domains?
   - What can we learn from other disciplines?

3. Practical Applications
   - Real-world implementations
   - Case studies and examples
   - Success patterns and failures

4. Future Trajectories
   - Where is this heading?
   - What emerging patterns matter?
   - What adjacent possibilities exist?

Draw connections between theory, practice, and broader trends.
```

---

### 4. Perplexity (Real-Time Data & Citations)

**Strengths:**
- Current information and recent developments
- Source citations and verification
- News and events integration
- Up-to-date statistics and data

**Optimal for:**
- Latest developments
- Current state of field
- Recent research and publications
- Market and industry trends

**Prompt Pattern:**
```
Research the latest developments in [TOPIC] (focus on 2024-2026):

1. Recent Developments
   - Major announcements and milestones
   - New research and publications
   - Industry developments
   - Regulatory changes

2. Current Statistics & Data
   - Market size and growth rates
   - Adoption metrics
   - Performance benchmarks
   - Investment and funding

3. Key Players & Organizations
   - Leading companies and researchers
   - Notable projects and initiatives
   - Competitive landscape

4. Emerging Trends
   - What's accelerating?
   - What's declining?
   - What's controversial?

Cite all sources. Prioritize information from the last 12 months.
```

---

### 5. Grok (Contrarian Analysis)

**Strengths:**
- Unconventional perspectives
- Challenging consensus views
- Identifying blind spots
- Provocative questions

**Optimal for:**
- Devil's advocate analysis
- Identifying weak assumptions
- Exploring edge cases
- Questioning orthodoxy

**Prompt Pattern:**
```
Provide contrarian analysis of [TOPIC]:

1. Challenge the Consensus
   - What's the mainstream view getting wrong?
   - What assumptions are questionable?
   - What evidence contradicts popular narratives?

2. Identify Blind Spots
   - What aren't people talking about?
   - What risks are underestimated?
   - What opportunities are overlooked?

3. Provocative Questions
   - What if the opposite were true?
   - Who benefits from current framing?
   - What future scenarios seem unlikely but possible?

4. Alternative Frameworks
   - How else could we think about this?
   - What different mental models apply?
   - What radical alternatives exist?

Be provocative but grounded. Challenge without being contrarian for its own sake.
```

---

### 6. ChatGPT (Structured Education)

**Strengths:**
- Clear, systematic explanations
- Building from first principles
- Educational scaffolding
- Structured learning paths

**Optimal for:**
- Learning new topics
- Conceptual foundations
- Step-by-step breakdowns
- Teaching complex subjects

**Prompt Pattern:**
```
Teach me [TOPIC] systematically, building from fundamentals:

1. First Principles
   - Core concepts and definitions
   - Why does this matter?
   - What problem does this solve?

2. Foundational Knowledge
   - What do I need to know first?
   - Key frameworks and models
   - Essential terminology

3. Progressive Complexity
   - Level 1: Basic understanding
   - Level 2: Intermediate concepts
   - Level 3: Advanced applications

4. Learning Path
   - What should I study in order?
   - Common misconceptions to avoid
   - Practice exercises or applications

Make it educational and accessible. Build understanding layer by layer.
```

---

### 7. Kimi (Long-Form Depth)

**Strengths:**
- Extended context processing (200K+ tokens)
- Comprehensive document analysis
- Long-form synthesis
- No arbitrary length constraints

**Optimal for:**
- Exhaustive coverage
- Detailed analysis without compression
- Processing multiple long documents
- Comprehensive reports

**Prompt Pattern:**
```
Provide exhaustive analysis of [TOPIC] without length constraints:

1. Comprehensive Overview
   - Every major aspect covered
   - Full historical development
   - Complete stakeholder mapping

2. Deep Dive Sections
   - Technical implementation (full detail)
   - Research landscape (all relevant studies)
   - Industry applications (comprehensive cases)
   - Future scenarios (detailed projections)

3. Supporting Detail
   - All relevant data points
   - Complete methodology explanations
   - Full context for claims
   - Extended examples

4. Synthesis
   - How everything connects
   - Overarching patterns
   - Meta-insights from depth

Don't compress or summarize. Go deep on every relevant dimension.
```

---

### 8. Notebook LM (Source Synthesis)

**Strengths:**
- Multi-document synthesis
- Connecting insights across sources
- Generating new insights from combinations
- Audio overview generation

**Optimal for:**
- Synthesizing uploaded documents
- Finding connections between sources
- Literature review
- Research paper analysis

**Prompt Pattern:**
```
Synthesize insights from [TOPIC] across all provided sources:

1. Core Themes
   - What patterns emerge across sources?
   - What do multiple sources emphasize?
   - Where is there consensus?

2. Unique Contributions
   - What does each source uniquely provide?
   - What perspectives are represented?
   - What gaps exist?

3. Contradictions & Tensions
   - Where do sources disagree?
   - What explains differences?
   - Which positions are better supported?

4. Integrated Understanding
   - How do insights combine?
   - What new understanding emerges?
   - What questions remain?

Connect ideas across sources. Identify emergent insights from synthesis.
```

---

### 9. Elicit (Academic Research)

**Strengths:**
- Research paper discovery and analysis
- Academic literature synthesis
- Study comparison and evaluation
- Methodological rigor

**Optimal for:**
- Academic literature review
- Research methodology analysis
- Evidence-based conclusions
- Identifying research gaps

**Prompt Pattern:**
```
Conduct academic analysis of [TOPIC]:

1. Literature Review
   - Key papers and studies
   - Major researchers and institutions
   - Theoretical frameworks used
   - Methodological approaches

2. Research Findings
   - What does empirical evidence show?
   - What are effect sizes and confidence levels?
   - What replications exist?
   - What contradictory findings exist?

3. Methodological Assessment
   - Study quality and rigor
   - Sample sizes and populations
   - Limitations and biases
   - Meta-analyses or systematic reviews

4. Research Gaps
   - What hasn't been studied?
   - What needs better evidence?
   - What are future research directions?

Prioritize peer-reviewed research. Cite studies with proper attribution.
```

---

### 10. Poe (Multi-Bot Coordination)

**Strengths:**
- Accessing multiple models in one platform
- Rapid iteration across models
- Quick comparative analysis
- Bot-to-bot synthesis

**Optimal for:**
- Quick consensus check across models
- Rapid prototyping of approaches
- Comparative analysis
- When you need speed over depth

**Prompt Pattern:**
```
Quick synthesis of [TOPIC] from multiple bot perspectives:

1. Rapid Coverage
   - What do most bots agree on?
   - What unique angles emerge?
   - What's the 80/20 on this topic?

2. Consensus Points
   - Core concepts everyone identifies
   - Widely accepted frameworks
   - Standard approaches

3. Divergent Views
   - Where do bots differ?
   - What alternative takes exist?
   - What's worth deeper investigation?

4. Actionable Summary
   - What matters most?
   - What can I act on immediately?
   - What needs more research?

Prioritize speed and breadth. Get diverse takes quickly.
```

---

## Research Orchestration Protocol

### Phase 1: Research Specification (5-10 minutes)

**MANDATORY INTAKE - Do not skip this**

Before generating prompts, complete this spec:

```yaml
RESEARCH SPEC

OBJECTIVE (decision you're making):
[What specific decision/action does this research inform?]

KEY QUESTIONS (3-7, ranked by priority):
1. [Most critical question]
2. [Second priority]
3. [Third priority]
...

CONSTRAINTS:
- Timeframe: [e.g., "last 12 months", "historical", "future projections"]
- Geography: [e.g., "US only", "global", "EU regulations"]  
- Domain: [e.g., "enterprise only", "consumer", "academic"]

DISCONFIRMATION CRITERIA (what would change your mind?):
[What evidence would prove your current hypothesis wrong?]

SUCCESS METRIC:
[How will you know this research was valuable?]
```

**Why this matters:**
- Prevents topic wandering
- Focuses models on decision-relevant information
- Enables claim verification (you know what claims matter)
- Defines when to stop (objective achieved vs. infinite research)

**Example:**
```yaml
OBJECTIVE: Decide whether to build AI tool selection platform

KEY QUESTIONS:
1. Do people pay for AI tool recommendations? (Priority 1)
2. What's the competitive landscape? (Priority 2)
3. What distribution channels exist? (Priority 3)

CONSTRAINTS:
- Timeframe: 2024-2026 (current market)
- Geography: US/EU markets
- Domain: B2B SaaS, excludes enterprise custom

DISCONFIRMATION: Evidence that free ChatGPT recommendations are "good enough" would kill this

SUCCESS METRIC: Clear GO/KILL decision with evidence score ≥7/10
```

---

### Phase 2: Prompt Generation (5 minutes)

**Step 1:** Define research topic clearly
- Be specific about scope
- Identify key questions
- Note any particular angles needed

**Step 2:** Select models based on needs
- All 10 for comprehensive research
- Subset for focused investigation
- Prioritize based on topic type:
  - Technical topics: DeepSeek, ChatGPT, Claude
  - Current events: Perplexity, Grok, Gemini
  - Academic: Elicit, Notebook LM, Claude
  - Synthesis: Claude, Kimi, Notebook LM

**Step 3:** Generate customized prompts
- Use patterns above as templates
- Customize for specific topic
- Add context or constraints as needed

---

### Phase 2: Execution (20-40 minutes)

**Parallel execution recommended:**

1. Copy prompt 1 → DeepSeek → Start processing
2. Copy prompt 2 → Claude → Start processing
3. Copy prompt 3 → Gemini → Start processing
4. Continue through all models

**Save responses systematically:**
- Create folder: `research_[topic]_[date]`
- Name files: `01_deepseek.md`, `02_claude.md`, etc.
- Include timestamp and model name in each file

---

### Stop Conditions (Prevent Research Spiral)

**Stop expanding if:**
- 2+ high-quality sources (Tier 1-2) agree → stop, sufficient evidence
- Contradiction persists after 1 follow-up round → log as unresolved, define settling evidence
- Max 2 swarm rounds per topic → diminishing returns after that
- Max 90 minutes total unless decision impact >$X (define your threshold)

**When to escalate instead of continuing:**
- Expert consultation needed (models can't resolve)
- Experiment required (empirical question)
- Legal/regulatory clarity needed (consult specialist)

---

### Phase 3: Synthesis (30-60 minutes)

**Synthesis Protocol:**

1. **First Pass: Pattern Recognition**
   - Read all responses
   - Note recurring themes
   - Identify unique insights
   - Flag contradictions

2. **Evidence-Weighted Consensus** (NOT model counting)
   
   **Evidence Tier System:**
   - **Tier 1:** Primary sources, papers, official docs, raw datasets
   - **Tier 2:** High-quality secondary analysis with citations
   - **Tier 3:** Reasoned but uncited synthesis
   - **Tier 4:** Speculation / vibes
   
   **Classification:**
   - Evidence-backed (Tier 1-2): One model with citations beats seven without
   - Plausible but unverified (Tier 3): Reasoned synthesis, needs verification
   - Speculative (Tier 4): Interesting hypotheses, treat as unproven
   
   **CRITICAL:** Model agreement ≠ truth. Models share training data and converge on socially acceptable framings. Focus on evidence quality, not vote counting.

3. **Contradiction Analysis**
   - Where do models disagree?
   - What explains disagreements?
   - Which position has better evidence?
   - What additional research would resolve?

4. **Unique Insight Extraction**
   - What did only one model identify?
   - Is it valid but overlooked?
   - Does it open new research directions?
   - Should it be investigated further?

5. **Gap Identification**
   - What did NO model adequately cover?
   - What questions remain unanswered?
   - What follow-up research is needed?
   - What experts should be consulted?

6. **Synthesis Document Creation**
   ```markdown
   # Research Synthesis: [Topic]
   Date: [Date]
   Models: [Which models used]
   
   ## Executive Summary
   [3-5 sentences capturing core findings]
   
   ## Evidence-Backed Findings (Tier 1-2)
   - [Claim with citations]
   - [Claim with citations]
   
   ## Plausible But Unverified (Tier 3)
   - [Reasoned synthesis without citations]
   - [Needs verification]
   
   ## Speculative (Tier 4)
   - [Hypotheses and vibes]
   - [Interesting but unproven]
   
   ## Contradictions Requiring Investigation
   [Conflicts with resolution protocol - see below]
   
   ## Research Gaps
   [What remains unknown]
   
   ## Recommended Actions
   [Based on evidence-backed findings only]
   
   ## Follow-Up Questions
   [For next research iteration]
   ```

7. **Claim Extraction & Verification Routing** (CRITICAL - don't skip)

   After synthesis, extract top 10 claims and route for verification:

   ```yaml
   CLAIM EXTRACTION
   
   Claim 1: [Specific assertion]
     Evidence Tier: [1/2/3/4]
     Tag: [factual/market/legal/opinion]
     Route to: [FactGuard/Reality-Check/Legal/None]
     Verification needed: [Yes/No]
   
   Claim 2: [Specific assertion]
     ...
   ```

   **Routing Rules:**
   - Factual claims (Tier 3-4) → FactGuard for citation check
   - Market claims ("people want X", "$Y revenue possible") → Reality-Check for proof demands
   - Legal/regulatory claims → Legal Risk Assessment
   - Opinion/speculation (Tier 4) → Flag as unverified, do not route

   **This prevents sophisticated hallucinations in stereo.**

---

## Contradiction Resolution Playbook

**When models disagree, don't stop at "they disagree" - resolve it.**

### Contradiction Ticket Format

```yaml
CONTRADICTION TICKET #[N]

CLAIM A:
  Statement: [Specific claim]
  Supporting Models: [Which models]
  Supporting Sources: [Citations/evidence]
  Evidence Tier: [1/2/3/4]

CLAIM B:
  Statement: [Contradicting claim]
  Supporting Models: [Which models]
  Supporting Sources: [Citations/evidence]
  Evidence Tier: [1/2/3/4]

LIKELY CAUSE OF DISAGREEMENT:
  [Check these common causes:]
  - Different definitions (are they measuring the same thing?)
  - Different timeframes (historical vs. current vs. future?)
  - Different samples (US vs. global? Enterprise vs. SMB?)
  - Different incentives (who benefits from each framing?)
  - Missing context (what assumptions differ?)

WHAT EVIDENCE WOULD DECIDE:
  [Specific test/source that would resolve this]

RESOLUTION PATH:
  [ ] Search for primary source (Perplexity focused query)
  [ ] Consult domain expert
  [ ] Run experiment
  [ ] Accept as unresolved (note what would settle it)

NEXT STEP:
  [Concrete action with deadline]

STATUS: [Open/Resolved/Unresolvable]
```

### Example Contradiction Ticket

```yaml
CONTRADICTION TICKET #1

CLAIM A:
  Statement: "AI tool selection platforms charge $79-199/month"
  Supporting Models: Gemini, ChatGPT
  Supporting Sources: None cited
  Evidence Tier: 4 (speculation)

CLAIM B:
  Statement: "No paid AI tool selection platforms exist"
  Supporting Models: Grok, Perplexity
  Supporting Sources: Perplexity searched, found none
  Evidence Tier: 2 (verified absence)

LIKELY CAUSE: Models A assumed market exists, Models B verified it doesn't

WHAT WOULD DECIDE: Find 1 competitor charging for this service

RESOLUTION PATH: Search focused on "AI tool recommendation SaaS pricing"

NEXT STEP: Perplexity search by end of day

STATUS: Resolved - Claim B correct, no competitors found
```

---

## Duplicate Elimination Protocol

**Multiple models will repeat the same points. Extract only deltas.**

After collecting responses:

1. **Identify Core Claims**
   - List all distinct claims across all models
   - Collapse identical/near-identical statements

2. **Track Model Deltas**
   - What did each model add that others didn't?
   - Focus synthesis on unique contributions
   - Note if model added no new information

3. **Collapse Duplicates in Synthesis**
   - One model with good citation > five models repeating it
   - Format: "[Claim] (cited by Perplexity, validated by Elicit)"
   - Don't give redundant claims extra weight

**This makes the swarm worth running.**

---

## Model Role Configuration (Operator-Tunable)

**Model strengths drift over time. Don't treat them as doctrine.**

If observed output quality differs from skill defaults, override:

```yaml
MODEL_ROLE_OVERRIDES

Claude: [Synthesis, Ethics, Nuance]
DeepSeek: [Code, EdgeCases, Math]
Perplexity: [Citations, Freshness, RealTime]
Grok: [Contrarian, BlindSpots, Provocative]
Gemini: [CrossDomain, Multimodal, Patterns]
ChatGPT: [Education, Structure, FirstPrinciples]
Kimi: [Depth, LongForm, Exhaustive]
NotebookLM: [SourceSynthesis, MultiDoc, Connections]
Elicit: [Academic, Papers, Methodology]
Poe: [QuickSynthesis, MultiBotCompare, Speed]
```

**When to update roles:**
- Model version changes significantly
- You observe consistent quality shifts
- New capabilities emerge
- Model gets worse at claimed strength

**Treat this as a tunable roster, not fixed reality.**

---

## Output Format

When user requests research swarm, output:

```markdown
═══════════════════════════════════════════════════════════════
           RESEARCH SWARM: [TOPIC]
═══════════════════════════════════════════════════════════════

RESEARCH SPECIFICATION

Objective: [Decision being made]
Key Questions:
  1. [Priority 1 question]
  2. [Priority 2 question]
  3. [Priority 3 question]

Constraints: [Timeframe, geography, domain]
Disconfirmation: [What would change your mind?]
Success Metric: [How you'll know research was valuable]

SWARM CONFIGURATION

Type: [MV Swarm (3 models) / Full Swarm (10 models)]
Models Deployed: [List models]
Estimated Time: [15-25 min for MV / 2-3 hours for Full]

─────────────────────────────────────────────────────────────
[1] PERPLEXITY → Fresh Data & Citations (ALWAYS INCLUDE)
─────────────────────────────────────────────────────────────
[Customized prompt focused on key questions with evidence tier instructions]

─────────────────────────────────────────────────────────────
[2] CLAUDE → Synthesis & Implications (ALWAYS INCLUDE)
─────────────────────────────────────────────────────────────
[Customized prompt focused on multi-perspective analysis]

─────────────────────────────────────────────────────────────
[3] DEEPSEEK or GROK → Technical/Contrarian (CHOOSE ONE)
─────────────────────────────────────────────────────────────
[Customized prompt for technical depth OR contrarian analysis]

[Additional models only if Full Swarm selected...]

═══════════════════════════════════════════════════════════════
                  SYNTHESIS PROTOCOL
═══════════════════════════════════════════════════════════════

After collecting responses:

1. EVIDENCE TIER CLASSIFICATION (not model counting!)
   - Tier 1-2 (Evidence-backed): Primary sources, citations, datasets
   - Tier 3 (Plausible unverified): Reasoned synthesis, needs checking
   - Tier 4 (Speculative): Vibes and hypotheses

2. DUPLICATE ELIMINATION
   - Collapse identical claims
   - Extract deltas: what did each model uniquely add?

3. CONTRADICTION RESOLUTION
   - Create Contradiction Ticket for each disagreement
   - Identify cause: definitions, timeframe, sample, incentives
   - Define settling evidence

4. CLAIM EXTRACTION & ROUTING
   - Extract top 10 claims
   - Tag: [factual/market/legal/opinion]
   - Route: FactGuard / Reality-Check / Legal Risk / None

5. STOP CONDITION CHECK
   - 2+ Tier 1-2 sources agree? → Stop
   - Contradiction persists after 1 round? → Log as unresolved
   - Max 2 rounds reached? → Stop
   - >90 minutes invested? → Stop (unless high-stakes)

SYNTHESIS DOCUMENT FORMAT: See skill documentation

═══════════════════════════════════════════════════════════════
```

### Optional: YAML Output Mode (Pipeline-Ready)

For handoff to Architect/VEF/other skills:

```yaml
research_spec:
  objective: ""
  questions:
    - question: ""
      priority: 1
    - question: ""
      priority: 2
  constraints:
    timeframe: ""
    geography: ""
    domain: ""
  disconfirmation: ""
  success_metric: ""

swarm_config:
  type: "MV" # or "Full"
  models:
    - name: "Perplexity"
      role: "Citations"
      prompt: ""
    - name: "Claude"
      role: "Synthesis"
      prompt: ""

outputs:
  - model: "Perplexity"
    evidence_tier: 2
    key_claims: []
    citations: []
    unique_contribution: ""
  - model: "Claude"
    evidence_tier: 3
    key_claims: []
    unique_contribution: ""

synthesis:
  evidence_backed: []
  plausible_unverified: []
  speculative: []
  contradictions:
    - ticket_id: 1
      claim_a: ""
      claim_b: ""
      resolution_status: ""
  
verification_routing:
  factguard: []
  reality_check: []
  legal_risk: []

next_actions:
  - action: ""
    deadline: ""
```

---

## Minimum Viable Swarm (MV Swarm)

**Use this 90% of the time. Reserve full 10-model swarm for high-stakes decisions only.**

**MV Swarm (15-25 minutes total):**

### Core 3-Model Setup

**Always include:**
1. **Perplexity** → Fresh data + citations (Tier 1-2 evidence)
2. **Claude** → Balanced synthesis + implications

**Then add ONE of:**
3a. **DeepSeek** → Technical/code/edge cases (for technical topics)  
   OR  
3b. **Grok** → Contrarian/blind spots (for strategic topics)

**When to use 4th-5th models:**
- Academic topic: Add Elicit
- Need exhaustive depth: Add Kimi
- Multimodal connections: Add Gemini

**Time breakdown:**
- 5 min: Research spec
- 3 min: Generate 3 prompts
- 10 min: Run models (parallel)
- 15 min: Synthesis + claim extraction
- 5 min: Route claims to verification

**This is your default. Use it unless:**
- Decision impact >$10K
- High controversy (need multiple perspectives)
- Complex technical + strategic + market question

---

## Full Swarm (10 Models)

**Use sparingly. High time cost, diminishing returns.**

**When to use:**
- Strategic decisions with >$50K impact
- Entering new market (need comprehensive view)
- Controversial topics requiring diverse perspectives
- Building foundational knowledge in new domain

**Time investment:** 2-3 hours total

---

## Advanced Usage Patterns

### Pattern 1: Focused Swarm (Subset of Models)

**When:** Topic doesn't require all 10 perspectives

**Technical topics:**
- DeepSeek (technical depth)
- Claude (synthesis)
- ChatGPT (education)

**Current events:**
- Perplexity (real-time data)
- Grok (contrarian)
- Gemini (connections)

**Academic research:**
- Elicit (papers)
- Notebook LM (sources)
- Claude (synthesis)

### Pattern 2: Iterative Research

**Round 1:** Initial swarm with all 10 models  
**Synthesis:** Identify gaps and contradictions  
**Round 2:** Focused swarm on gaps with 3-5 models  
**Final Synthesis:** Complete picture

### Pattern 3: Debate Protocol

**For controversial topics:**
1. Run swarm to gather perspectives
2. Identify 2-3 main positions
3. Create debate prompts: "Argue for position X using evidence"
4. Run through models again with debate prompts
5. Synthesize strongest arguments for each position

### Pattern 4: Progressive Depth

**Layer 1:** Quick synthesis (Poe + Perplexity + Grok) - 10 min  
**Layer 2:** Add depth (Claude + DeepSeek + Gemini) - 20 min  
**Layer 3:** Add rigor (Elicit + Kimi + Notebook LM) - 40 min  
**Layer 4:** Final synthesis - 30 min

---

## Integration with Other Skills

**UPSTREAM (Research Swarm feeds these):**

```
Research Swarm 
  ↓ [Claims extracted]
  ├→ FactGuard (verify factual claims with Tier 3-4)
  ├→ Reality-Check (validate market claims, demand proof)
  ├→ Legal Risk (check regulatory/compliance claims)
  │
  ↓ [Research complete, decision ready]
  ├→ VEF (spec product based on validated research)
  ├→ Simulation Framework (model scenarios from research)
  ├→ Economy of Plenty (monetization strategy)
  └→ Copy Crafter (messaging based on validated claims)
```

**Routing Rules (Enforced):**

1. **Factual Claims (Tier 3-4)** → FactGuard
   - "Market size is $X"
   - "Adoption rate is Y%"
   - "Competitors charge $Z"
   
2. **Market Claims** → Reality-Check Protocol
   - "People want this"
   - "Revenue potential of $X"
   - "Demand exists for Y"

3. **Legal/Regulatory Claims** → Legal Risk Assessment
   - "Compliant with regulation X"
   - "Requires license Y"
   - "Name trademark available"

4. **Strategic Decisions** → SEF (after Reality-Check validates)

**DOWNSTREAM (These invoke Research Swarm):**

- SEF (before GO/KILL decisions requiring evidence)
- VEF (before product spec, research market/competition)
- KEF (before curriculum design, research learning science)
- CEF (before content creation, research audience)
- Pipeline Manager (when evidence gathering needed)

**This is not optional - routing is mandatory to prevent hallucination propagation.**

---

## Examples

### Example 1: Technical Research

**Topic:** "AI agent safety frameworks"

**Swarm composition:** All 10 models

**Key outputs:**
- DeepSeek: Mathematical formalization of safety constraints
- Claude: Multi-stakeholder implications and trade-offs
- Perplexity: Latest safety research (2024-2026)
- Grok: Contrarian view on safety theater vs. real safety
- Elicit: Academic papers on alignment and safety

**Synthesis:** Strong consensus on need for formal verification, disagreement on timeline urgency, unique insight from Grok about regulatory capture risks.

---

### Example 2: Market Research

**Topic:** "Demand for AI tool selection services"

**Swarm composition:** 7 models (skip Kimi, Notebook LM, Elicit)

**Key outputs:**
- Perplexity: Current market data on AI adoption
- Gemini: Cross-industry patterns in tool adoption
- Claude: Stakeholder perspectives (enterprises, SMBs, individuals)
- Grok: Why might this market NOT exist (contrarian)

**Synthesis:** Moderate consensus on enterprise demand, weak consensus on SMB demand, Grok identified substitution risk from ChatGPT.

---

## Critical Reminders

1. **Evidence quality > model agreement** - One cited source beats seven vibes
2. **Synthesis quality > input volume** - 70% truth generation, 30% input collection
3. **Always complete research spec** - Prevents topic wandering and defines success
4. **Use MV Swarm by default** - Full swarm only for high-stakes decisions
5. **Stop conditions are mandatory** - 2 rounds max, 90 min max (unless justified)
6. **Route claims to verification** - FactGuard/Reality-Check/Legal automatically
7. **Resolve contradictions** - Create tickets, define settling evidence
8. **Eliminate duplicates** - Focus on deltas, not redundancy
9. **Model roles drift** - Update overrides when observed behavior changes
10. **Time estimates are real** - MV Swarm = 25 min, Full Swarm = 2-3 hours

**The bottleneck is synthesis quality and verification, not input collection.**

---

**Research Swarm transforms scattered individual model queries into systematic multi-perspective intelligence gathering. Use it when the cost of being wrong exceeds the cost of thorough research.**
