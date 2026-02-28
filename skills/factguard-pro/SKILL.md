---
name: factguard-pro
description: Adaptive verification intelligence system for detecting AI hallucinations, misinformation, and manipulation across multiple threat vectors. Use when users request verification of claims, ask to check facts, analyze suspicious content, detect AI-generated misinformation, evaluate source credibility, or investigate potentially manipulated information. Triggers include phrases like "verify this", "check if this is true", "is this accurate", "fact-check", "detect hallucinations", "analyze this claim", or when content appears suspicious.
---

# FactGuard Pro: Adaptive Verification Intelligence

## Core Methodology

FactGuard Pro uses **multi-vector threat analysis** to detect misinformation, manipulation, and AI hallucinations. The system analyzes content through specialized vectors, dynamically weights them based on relevance, and produces **time-bounded decisions with clear action gates**.

### CRITICAL CONSTRAINTS

**Decision Gate (MANDATORY)**: Every analysis MUST end with one of three states:
- **TRUST** (safe to proceed with this information)
- **DO NOT TRUST** (unsafe to act on, verified false/manipulative)
- **DEFER** (requires external expert verification)

**NO FOURTH OPTION**. No "investigate more" without picking a lane.

**Time Caps**:
- Quick check: ≤30 seconds
- Standard: ≤2 minutes  
- Deep: ≤5 minutes (only when explicitly requested)

**Scope Lock**:
- **Default mode**: AI-generated content, news media, corporate communications
- **Political analysis**: Requires explicit opt-in (risk of endless rabbit holes)
- **Academic deep-dives**: Only when user requests `/deep academic`

### Verification Workflow

1. **Threat Scanning**: Parse input and score relevance for active vectors (0.0-1.0)
2. **Vector Activation**: Select vectors above 0.3 threshold for analysis
3. **Time-Bounded Analysis**: Run verification within time cap for complexity level
4. **Threat Fusion**: Merge insights into unified assessment
5. **Mandatory Decision**: Output TRUST/DO NOT TRUST/DEFER with reasoning

## Analysis Vectors (Scoped)

**Default Active Vectors** (always used):
- AI Vector (1.0 weight)
- Media Vector (0.8 weight)
- Corporate Vector (0.7 weight)

**Opt-In Vectors** (require explicit activation):
- Political Vector (0.6 weight) - Use `/activate political` to enable
- Academic Vector (1.0 weight) - Use `/activate academic` for deep research verification
- Narrative Vector (0.9 weight) - Auto-activates when manipulation patterns detected, manual override available

### AI Vector (1.0 weight) - ALWAYS ACTIVE
Detect AI-generated content issues:
- **Hallucinated citations**: Fake papers, non-existent sources, plausible but invented references
- **Statistical precision abuse**: Overly specific numbers without sources (e.g., "73.2% increase")
- **Temporal errors**: Future events treated as past, wrong dates, anachronisms
- **Confidence without evidence**: Definitive claims lacking verifiable sources
- **Pattern matching**: Typical AI hedging language or structure

**Key patterns** in `references/ai-hallucinations.md`

### Media Vector (0.8 weight)
Analyze viral claims and social media misinformation:
- **Source credibility**: Evaluate origin (verified accounts vs. anonymous sources)
- **Viral mechanics**: Assess emotional manipulation and shareability
- **Image/video manipulation**: Check for edited media, deepfakes, out-of-context visuals
- **Quote verification**: Validate attributed statements against original sources
- **Coordination signals**: Detect synchronized posting or bot-like behavior

### Narrative Vector (0.9 weight)
Expose framing manipulation:
- **Russell conjugations**: "I'm firm, you're stubborn, they're pigheaded" patterns
- **Euphemism detection**: Corporate/political language obscuring reality
- **Framing analysis**: What's emphasized vs. omitted
- **Emotional manipulation**: Fear-mongering, outrage-baiting, pity appeals
- **Agency hiding**: Passive voice concealing responsibility

**Patterns database** in `references/manipulation-techniques.md`

### Corporate Vector (0.7 weight)
Decode business jargon and obfuscation:
- **Jargon density scoring**: Measure buzzword concentration
- **Plain translation**: Convert corporate-speak to concrete meaning
- **Hidden negatives**: "Rightsizing", "workforce optimization" = layoffs
- **Vague quantification**: "Significantly improved", "substantial growth" without numbers
- **Authority positioning**: Technical language creating false expertise

### Political Vector (0.6 weight)
Identify propaganda and coordination:
- **Talking points**: Repeated phrases across multiple sources
- **Coordination patterns**: Synchronized messaging timing
- **False balance**: Presenting fringe views as mainstream
- **Whataboutism**: Deflection through irrelevant comparisons
- **Astroturfing**: Manufactured grassroots appearance

### Academic Vector (1.0 weight)
Verify research integrity:
- **Citation validation**: Check if papers/studies actually exist
- **Methodology assessment**: Evaluate research design quality
- **Peer review status**: Distinguish preprints from published work
- **Retraction checking**: Verify if work has been withdrawn
- **Journal credibility**: Assess publication venue quality

**Source hierarchy** in `references/source-authority.md`

## Mandatory Decision Framework

### Decision Gates (Pick One - No Exceptions)

**✅ TRUST** (Safe to proceed)
- Multiple authoritative sources confirm
- No significant red flags detected
- Methodology sound (if applicable)
- **Action**: Use this information confidently
- **Time spent**: Document and move on

**🚫 DO NOT TRUST** (Unsafe to act on)
- Contradicted by authoritative sources
- Severe hallucination patterns detected
- Deliberate manipulation identified
- **Action**: Discard or flag, do not use
- **Time spent**: Document reason and move on

**⏸️ DEFER** (Requires external verification)
- Conflicting authoritative sources
- Partial verification possible but incomplete
- High-stakes decision requiring expert judgment
- **Action**: Escalate to domain expert, do not decide yourself
- **Required**: Name specific expert type needed (medical doctor, lawyer, etc.)

### Confidence Scoring (Supporting Metric Only)

Confidence scores (0-100%) inform the decision gate but don't replace it:
- 85-100%: Usually → TRUST
- 50-84%: Usually → DEFER  
- 0-49%: Usually → DO NOT TRUST

**Critical**: Confidence score is a guide. The decision gate is mandatory.

## Output Templates

### Standard Output (REQUIRED FORMAT)

```markdown
⏱️ TIME: [X seconds/minutes] | DECISION: [TRUST/DO NOT TRUST/DEFER]

📊 ANALYSIS:
[Active Vector 1]: [Key finding]
[Active Vector 2]: [Key finding]

🎯 REASONING:
[Why this decision was reached]

⚡ ACTION:
[Specific next step based on decision gate]
```

### Decision-Specific Templates

**TRUST Output**:
```markdown
✅ TRUST | Time: 45 seconds

🤖 AI ANALYSIS: No hallucination patterns detected
📰 MEDIA ANALYSIS: Verified by 3+ authoritative sources

🎯 REASONING: Claim verified across independent sources with consistent methodology

⚡ ACTION: Proceed with confidence. Source: [links]
```

**DO NOT TRUST Output**:
```markdown
🚫 DO NOT TRUST | Time: 1m 30s

🤖 AI ANALYSIS: Fake citation detected (paper doesn't exist)
📰 MEDIA ANALYSIS: Source has history of misinformation

🎯 REASONING: Multiple red flags, contradicted by authoritative sources

⚡ ACTION: Discard this claim. Do not use or share.
```

**DEFER Output**:
```markdown
⏸️ DEFER | Time: 2m 15s

🤖 AI ANALYSIS: Plausible but unverified technical claim
📰 MEDIA ANALYSIS: Conflicting expert opinions

🎯 REASONING: High-stakes medical decision requiring expert review

⚡ ACTION: Consult licensed physician before proceeding. Specific questions: [list]
```

### Time Cap Enforcement

**Quick Check** (≤30 seconds):
- Single vector check
- Clear-cut cases only
- Must output decision immediately

**Standard** (≤2 minutes):
- Multi-vector analysis
- Most queries default here
- Must output decision within time cap

**Deep** (≤5 minutes):
- Only when user explicitly requests `/deep`
- Full cross-vector intelligence
- Still must output decision

## Slash Commands

**Decision Override**:
- `/trust` - Force TRUST gate (use when you've verified independently)
- `/defer` - Force DEFER gate (acknowledge you can't decide)
- `/reject` - Force DO NOT TRUST gate (when evidence is clear)

**Scope Control**:
- `/activate political` - Enable political vector (use sparingly)
- `/activate academic` - Enable deep academic verification
- `/quick` - Force 30-second time cap (default should be used more)

**Deep Analysis** (use rarely):
- `/deep [vector]` - Extended single-vector analysis (still must output decision)
- `/trace [claim]` - Archaeological investigation of claim origins
- `/compare [A] vs [B]` - Comparative verification (outputs relative trust levels)

**Translation Utilities**:
- `/translate [text]` - Convert jargon/euphemisms to plain language (no decision gate)

## Anti-Avoidance Best Practices

### CRITICAL: This Skill Can Become an Avoidance Engine

**The Trap**: "I can't act yet—I need to verify more" feels productive but kills momentum.

**The Guard**: Every analysis MUST end with a decision gate. No fourth option.

### Always Do
1. **Pick a lane**: TRUST, DO NOT TRUST, or DEFER. No "investigate more" without choosing.
2. **Respect time caps**: 30s/2min/5min. Ship the decision within time budget.
3. **Default to quick checks**: Most claims don't warrant deep analysis. 
4. **Use DEFER for high-stakes**: If wrong decision = serious harm, escalate to expert.
5. **Document and move on**: Once decision is made, stop analyzing.

### Never Do
1. **Endless investigation**: If you hit time cap without decision → DEFER
2. **Analysis paralysis**: "More research needed" = choosing not to choose = forbidden
3. **Scope creep**: Don't activate political/academic vectors without explicit need
4. **Perfection seeking**: Good enough decision now > perfect decision never
5. **Justifying delay**: "This is important so I need more time" = avoidance pattern

### Decision Heuristics

**When to TRUST**:
- 2+ independent authoritative sources agree
- No red flags in active vectors
- Stakes are low-to-medium
- Within time cap

**When to DO NOT TRUST**:
- Clear hallucination patterns
- Source contradictions
- Verified false by authorities
- Within time cap

**When to DEFER**:
- High-stakes decision (medical, legal, financial)
- Genuine expert disagreement
- Outside your domain expertise
- Time cap reached without clear answer

### Cognitive Checkpoints

Before extending analysis, ask:
- "Have I hit my time cap?" (If yes → pick decision gate NOW)
- "Is this actually high-stakes?" (If no → TRUST or DO NOT TRUST, don't over-verify)
- "Am I avoiding a decision?" (If yes → force DEFER and move on)
- "Would an expert change this?" (If yes → DEFER to expert)

### Integration with Execution

FactGuard Pro is a **protective layer**, not a primary workflow:
- Use it to **protect decisions**, not replace them
- Use it to **catch obvious errors**, not guarantee perfection
- Use it to **delegate expert decisions**, not become an expert
- Use it to **move forward with confidence**, not justify delay

## Decision Quality Over Analysis Depth

### Self-Check Questions (Before Outputting)
- **Have I picked a decision gate?** (TRUST/DO NOT TRUST/DEFER - required)
- **Am I within time cap?** (30s/2min/5min depending on mode)
- **Is my reasoning clear?** (User should understand why this decision)
- **Is the action specific?** (What to do next based on decision)
- **Am I avoiding a decision?** (If yes, force DEFER and explain why)

### Common Anti-Patterns to Avoid
- **Vector tunnel vision**: Running all vectors when 1-2 would suffice
- **Time cap violation**: Going over budget "just to be sure"
- **Decision avoidance**: Outputting analysis without picking gate
- **Scope creep**: Activating political/academic vectors unnecessarily
- **Perfection seeking**: "Not enough evidence" = pick DEFER and move on

### Time Management by Complexity

**30-second checks** (default for most claims):
- AI hallucination scan
- Single source credibility check
- Output: TRUST or DO NOT TRUST

**2-minute standard** (when multiple factors):
- 2-3 active vectors
- Cross-reference 2-3 sources
- Output: Decision gate with reasoning

**5-minute deep** (only when explicitly requested):
- Full vector activation allowed
- Cross-vector intelligence
- Still must output decision gate

**Over 5 minutes** = Force DEFER immediately

## Reference Files

Load when needed:
- `references/ai-hallucinations.md` - Common AI hallucination patterns database
- `references/manipulation-techniques.md` - Propaganda and framing techniques
- `references/source-authority.md` - Source credibility hierarchy by domain

## Core Philosophy

**"Decide, don't deliberate indefinitely"**

FactGuard Pro exists to enable action, not prevent it. Every verification must end with a clear decision:
- **TRUST** → Act with confidence
- **DO NOT TRUST** → Discard and move on
- **DEFER** → Escalate to expert and move on

The goal is not perfect verification—it's good-enough decision-making within time constraints. Ship the decision, don't polish the analysis.

**Anti-Avoidance Principle**: If verification prevents action, verification has failed. Pick a lane and move forward.

**Positioning**: FactGuard Pro is a protective layer for decisions, not a standalone research system. Use it to catch obvious errors and delegate expert decisions—then execute.
