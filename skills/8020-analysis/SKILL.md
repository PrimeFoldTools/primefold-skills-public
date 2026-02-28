---
name: 8020-analysis
description: Pareto principle analyzer that identifies the vital few from the trivial many. Scores and ranks efforts across products, features, channels, time allocation, customers, or content to find the 20% generating 80% of results. Use when facing too many priorities, optimizing resource allocation, cutting waste, or making focus decisions. Outputs actionable Focus/Delegate/Automate/Kill recommendations. Integrates with Strategist for sequencing and Auditor for waste detection.
---

# 80/20 Analysis

Find the vital 20% that generates 80% of results. Kill, delegate, or automate the rest.

## Purpose

Apply Pareto principle systematically to identify high-leverage activities and eliminate low-impact busy work. Transform scattered effort into ruthless focus.

**Core principle:** Not all effort is equal. Most results come from a small fraction of inputs.

---

## When to Use

**Auto-triggers:**
- "Too many priorities"
- "What should I focus on?"
- "Optimize [process/product/time]"
- "Cut the fat"
- "Simplify"
- "Which [X] matters most?"

**Manual triggers:**
- "80/20 analysis on [domain]"
- "Pareto my [features/channels/time/customers]"
- "What's high leverage here?"
- "Focus filter for [X]"

**Use when:**
- Scattered across too many efforts
- Low productivity despite high activity
- Need to make hard prioritization decisions
- Resource constraints require cuts
- Unclear what's actually working

---

## Analysis Domains

### 1. Product Features

**Question:** Which features drive 80% of value/usage/satisfaction?

**Inputs needed:**
- List of all features
- Usage data (if available) OR user feedback
- Development cost per feature
- Maintenance burden per feature

**Output:** Focus on vital features, deprecate rarely-used complexity

---

### 2. Marketing Channels

**Question:** Which channels produce 80% of leads/conversions/revenue?

**Inputs needed:**
- List of all channels (content, ads, email, social, etc.)
- Performance metrics per channel
- Cost/effort per channel
- Quality of leads per channel

**Output:** Double down on working channels, cut waste

---

### 3. Time Allocation

**Question:** Which activities produce 80% of results?

**Inputs needed:**
- How you currently spend time (rough % breakdown)
- Impact of each activity (revenue/progress/satisfaction)
- What could be delegated/automated
- What's pure waste

**Output:** Restructure time toward high-leverage activities

---

### 4. Customer Segments

**Question:** Which 20% of customers generate 80% of revenue/referrals/satisfaction?

**Inputs needed:**
- Customer list or segments
- Revenue per customer/segment
- Support burden per customer/segment
- Referral rate per segment

**Output:** Focus on best-fit customers, fire bad-fit

---

### 5. Content Topics

**Question:** Which topics drive 80% of engagement/growth/conversions?

**Inputs needed:**
- Content pieces or topic categories
- Engagement metrics (views, shares, comments)
- Conversion metrics (if applicable)
- Creation effort per piece

**Output:** Create more of what works, stop what doesn't

---

### 6. SKU/Product Portfolio

**Question:** Which products generate 80% of revenue/profit?

**Inputs needed:**
- Product list
- Revenue per product
- Profit margin per product
- Operational complexity per product

**Output:** Focus portfolio, kill underperformers

---

## Execution Modes

### INTAKE CONTRACT (Required Before Analysis)

**Specify analysis domain:**
```
domain: [features/channels/time/customers/content/products/other]
items: [List all items to analyze - minimum 5, maximum 50]
metric: [What defines "impact" - revenue/users/satisfaction/time-saved]
current_state: [How resources currently allocated]
constraints: [What can't be changed - contracts, commitments, etc.]
```

**CRITICAL: Data State Declaration (Per Item)**

For EACH item, declare:
```
data_type: [exact | estimated | unknown]
confidence: [high | medium | low]
```

**Data Type Definitions:**

**EXACT:** You have actual metrics
- Example: Feature has 2,847 monthly active users (from analytics)
- Example: Channel generated 45 leads last month (tracked)
- Example: Activity takes 4.2 hours/week (time-tracked)

**ESTIMATED:** You have reasonable estimate, no hard data
- Example: Feature probably used by ~60% of users (gut + feedback)
- Example: Channel generates maybe 20-30 leads/month (rough)
- Example: Activity takes about 3-5 hours/week (estimated)

**UNKNOWN:** No data, pure guess
- Example: New feature, no usage data yet
- Example: Never tracked this metric
- Example: Can't estimate with any confidence

**Percent-Math Rules (Enforced):**

```
IF data_type = exact:
  → Allow "Contribution: X%" and "Cumulative: Y%"
  → Show precise percentages

IF data_type = estimated:
  → Show rank + score only
  → Show cumulative as "~X% (approx)"
  → Flag with confidence level

IF data_type = unknown:
  → NO percent math allowed
  → Output "Needs measurement plan"
  → Cannot calculate contribution without data
```

**Minimum Viable Dataset:**

If you have NO data on any items:
→ Run QUALITATIVE 80/20 (impact vs effort vs alignment)
→ Label clearly: "QUALITATIVE ANALYSIS - NO HARD DATA"
→ Output measurement plan as primary deliverable

**If ANY input is unknown, ASK before proceeding. Do not guess.**

---

### CRITICAL: Unit of Analysis Check (Prevents Apples-to-Oranges)

**Problem:** 80/20 fails when items aren't comparable.

**Bad example:**
- "YouTube" (channel) vs "write 1 blog post" (tactic)
- "Product line" vs "single SKU"
- "Trading" (activity) vs "check email" (task)

**Normalization Rule (ENFORCED):**

Items must be same abstraction layer.

**If mixed layers detected:**

1. **STOP analysis**
2. **Force re-bucketing:**
   - Group items into comparable categories first
   - Score categories
   - Then drill into top category if needed

**Bucketing Process:**

```
Step 1: Identify abstraction layers
[List all items]

Step 2: Detect mixed layers
Example:
- Items 1-5: Activities (product dev, trading, content)
- Items 6-8: Tasks (email, meetings, admin)
- Items 9-10: Projects (launch X, build Y)

MIXED LAYERS DETECTED → Cannot compare directly

Step 3: Re-bucket into single layer
Option A: Bucket UP (aggregate tasks into activities)
Option B: Bucket DOWN (break activities into tasks)
Option C: Pick one layer, exclude others

Step 4: Confirm comparable items
All items now at same abstraction level?
→ Proceed with analysis
```

**Auto-trigger bucketing if >15 items:**

When item count >15:
→ Ask: "These items seem varied. Should I bucket into categories first?"
→ Categories reduce noise, clarify vital few
→ Then drill into top category for detail

---

### FAST MODE (Default - 5-10 minutes)

**Use when:** Quick focus decision, single domain, clear metrics

**FAST MODE SCORING (Consistent with DEEP):**

For each item, score THREE dimensions:

```
Impact (0-10): Using impact rubric
Ease (0-10): Inverse of effort (10 = very easy, 1 = very hard)
Alignment (0-10): Strategic fit with core mission

Priority Score = (Impact × Ease × Alignment) / 100

This prevents "high impact but impossible now" from dominating.
```

**Process:**
1. Gather inputs (intake contract)
2. Score each item: Impact, Ease, Alignment
3. Calculate Priority Score
4. Sort by Priority Score (not just Impact)
5. Calculate cumulative impact (if data allows)
6. Draw 80% threshold line
7. Assign actions (Focus/Delegate/Automate/Seed/Sunset/Kill)

**Output:**
```
80/20 ANALYSIS: [Domain]

VITAL FEW (Focus on these):
1. [Item] - Impact: X/10, Cumulative: Y%
2. [Item] - Impact: X/10, Cumulative: Y%
3. [Item] - Impact: X/10, Cumulative: Y%
─────── 80% THRESHOLD ───────

TRIVIAL MANY (Delegate/Automate/Kill):
4. [Item] - Impact: X/10 → [Action]
5. [Item] - Impact: X/10 → [Action]
...

RECOMMENDED ACTIONS:
Focus: [Top 3 items - do more]
Delegate: [Items that could be handed off]
Automate: [Items that could be systematized]
Kill: [Items producing <2% impact]

EXPECTED IMPACT: [X]% of results from [Y]% of effort
```

---

### DEEP MODE (15-30 minutes)

**Use when:** Complex portfolio, multiple metrics, strategic decisions

**DEEP MODE INTAKE (Additional Required Fields):**

For each item, gather:
```
impact_score: [0-10 using rubric]
effort_estimate: [hours/week OR dev-days OR low/med/high]
maintenance_cost: [low/medium/high - ongoing burden]
strategic_alignment: [0-10 OR low/med/high - fits core mission?]
optionality: [reversible / irreversible - can you undo this?]
dependencies: 
  - blockers: [what must happen first]
  - downstream: [what depends on this]
  - enables: [what does this unlock]
```

**Combined Priority Formula:**
```
Priority Score = (Impact × Strategic Alignment × Ease) / 100

Where:
- Impact: 0-10 (from rubric)
- Strategic Alignment: 0-10 (mission fit)
- Ease: 10 - Effort (inverse, so low effort = high ease)

Example:
Impact: 8, Alignment: 9, Effort: 3 (so Ease: 7)
Priority = (8 × 9 × 7) / 100 = 5.04

Higher priority score = better candidate for FOCUS
```

**Process:**
1. Multi-metric scoring (impact + effort + strategic value)
2. Constraint analysis (what can't be changed)
3. Dependency mapping (what enables what)
4. Opportunity cost calculation
5. Action plan with timelines
6. Risk assessment of cuts

**Output:**
```
COMPREHENSIVE 80/20 ANALYSIS
[Detailed multi-section output - see Output Templates]
```

---

## Impact Scoring Rubric

**Critical: NO VIBE-BASED SCORING**

Each item scored 0-10 using evidence-based rubric:

### For Revenue/Growth Metrics:

**10:** Produces >30% of total metric  
**8-9:** Produces 15-30% of total  
**6-7:** Produces 5-15% of total  
**4-5:** Produces 1-5% of total  
**2-3:** Produces <1% of total  
**0-1:** Produces negligible/unmeasurable impact  

### For Time/Efficiency Metrics:

**10:** Saves >5 hours/week OR eliminates major bottleneck  
**8-9:** Saves 2-5 hours/week OR significant efficiency gain  
**6-7:** Saves 0.5-2 hours/week OR moderate improvement  
**4-5:** Saves <30 min/week OR minor improvement  
**2-3:** No time savings OR marginal benefit  
**0-1:** Actually costs time OR negative value  

### For Strategic Value:

**10:** Mission-critical, can't operate without it  
**8-9:** High strategic value, major competitive advantage  
**6-7:** Important but not critical, good differentiation  
**4-5:** Nice to have, minor differentiation  
**2-3:** Minimal strategic value  
**0-1:** No strategic value OR strategic liability  

**Use actual data when available. If no data, use best evidence-based estimate with confidence flag (LOW/MEDIUM/HIGH).**

---

## The 80/20 Principle

**Pareto's observation:**
- 80% of results come from 20% of causes
- 20% of customers generate 80% of revenue
- 20% of features get 80% of usage
- 20% of time produces 80% of output

**Why this matters:**
- Most effort is wasted on low-impact activities
- Focusing on vital few multiplies results
- Cutting trivial many frees resources
- Simplicity beats complexity

**Common ratios (empirically observed):**
- 80/20 (classic)
- 90/10 (extreme cases)
- 70/30 (less concentrated)

**Your ratio may vary - the principle remains: Focus on vital few, cut trivial many**

---

## Pareto of Pareto (Operational Step)

**The vital vital few:** 80/20 compounds. 80% of 80% = 64% of results from 4% of inputs.

**When to use:** After identifying vital few, run second pass for ultra-focus.

**Process:**

```
Step 1: Run standard 80/20
Result: 5 items identified as "vital few"

Step 2: Apply 80/20 AGAIN to those 5 items
Question: "Within these 5, which 1-2 produce 80% of the value?"

Step 3: Ultra-focus on vital vital few
Result: 1-2 items = your ONLY priorities

This is where 2-6 hour/day constraints get respected.
```

**Example:**

```
Standard 80/20 on 20 product features:
→ 4 features (20%) drive 80% of value

Pareto of Pareto on those 4:
→ 1 feature (AI Generator) drives 65% of THOSE 4's value

Conclusion: AI Generator = 52% of total product value
→ Ultra-focus: Make AI Generator 3x better
→ Everything else is secondary
```

**Use Pareto of Pareto when:**
- Capacity extremely constrained (2-6 hours/day)
- Need ruthless single priority
- Original 80/20 still too scattered (vital few = 5+ items)
- "Focus on 5 things" still feels overwhelming

**Output:**
```
PARETO OF PARETO ANALYSIS:

Original vital few: [5 items]

Within vital few, which drives most value?
1. [Item]: 40% of vital few's value = 32% of total
2. [Item]: 30% of vital few's value = 24% of total
3. [Item]: 20% of vital few's value = 16% of total

VITAL VITAL FEW (Ultra-focus):
→ Item 1 is THE priority
→ Item 2 is secondary
→ Items 3-5 are maintenance only

Time allocation recommendation:
- Item 1: 60% of available time
- Item 2: 30% of available time
- Items 3-5: 10% of available time
```

---

## Four-Action Framework (Updated)

After identifying vital vs trivial, assign actions:

### 1. FOCUS (Vital Few - Above 80% Line)

**Criteria:**
- High impact score (7-10)
- In top 20-30% of items
- Cumulative impact reaches 80% threshold

**Action:**
- Do MORE of this
- Allocate MORE resources
- Protect time for this
- Improve quality/consistency

**Examples:**
- Feature: Gets 60% of usage → Make it even better
- Channel: Drives 50% of leads → Double down on it
- Customer: Generates 40% of revenue → Give VIP treatment
- Time: Creates 70% of value → Protect this time ruthlessly

---

### 2. DELEGATE (Necessary but Low-Leverage)

**Criteria:**
- Medium impact (4-6)
- Someone else could do it
- Not strategic/differentiating
- Operational necessity

**Action:**
- Hand off to team member
- Hire contractor/VA
- Outsource to specialist
- Train someone else

**Examples:**
- Feature: Admin panel (necessary but not differentiating) → Junior dev
- Channel: Social media posting → VA
- Customer: Support tickets → Support team
- Time: Email management → Assistant

---

### 3. AUTOMATE (Repetitive Low-Value)

**Criteria:**
- Low-medium impact (3-6)
- Repetitive/systematic
- Can be automated
- Time sink if done manually

**Action:**
- Build automation
- Use tools/systems
- Create templates
- Set up workflows

**Examples:**
- Feature: Batch operations → Add bulk actions
- Channel: Social scheduling → Use automation tool
- Customer: Onboarding → Email sequence
- Time: Reporting → Automated dashboards

---

### 4. SEED (Small Bets with Asymmetric Upside)

**Criteria:**
- Low current impact (0-3) BUT high expected upside
- Experimental probe OR enabling work
- Cheap to run (<2 hours/week or <$100/month)
- Timeboxed validation possible

**Action:**
- Keep running at minimal investment
- Set validation timeline (14-30 days)
- Define success metric
- Promote to FOCUS or SUNSET based on results

**Examples:**
- Feature: Beta experiment with 10 users → Test 30 days, measure adoption
- Channel: New platform (TikTok) → 2 hours/week for 3 weeks, track leads
- Customer: Small segment with potential → Monitor for 60 days
- Time: Compounding asset (email list building) → Keep minimal effort

**SEED prevents killing the future because it's not paying yet.**

---

### 5. SUNSET (Phase Out Low-Value)

**Criteria:**
- Low impact (0-3)
- Consuming resources
- No strategic value
- Has dependencies OR exit costs

**Action:**
- Stop NEW investment
- Minimal maintenance only
- Planned wind-down with timeline
- Notify stakeholders
- Migration plan if needed

**SUNSET Plan Template:**
```
Item: [Name]
Impact score: [X]/10
Why sunset: [Reason]

What breaks if stopped:
- [Dependency 1]
- [Dependency 2]

Who needs notice:
- [Stakeholder 1]
- [Stakeholder 2]

Rollback plan (if needed):
- [How to reverse if critical issue]

Timeline:
- Announce: [Date]
- Stop investment: [Date]
- Minimal maintenance period: [Duration]
- Full sunset: [Date]

Resources freed: [Time/money/attention]
```

**Examples:**
- Feature: Used by 2% but has legacy users → 90-day sunset with migration
- Channel: No leads in 6 months but has brand presence → Wind down over 60 days
- Customer: Unprofitable but has contract → Sunset at renewal, don't re-sign
- Time: Commitment with notice period → Announce exit, honor obligation, then stop

---

### 6. KILL (Immediate Stop - Subset of SUNSET)

**Criteria (ALL must be true):**
- Low impact (0-2)
- NO dependencies
- NO contractual obligations
- Low/zero exit cost
- Reversible decision

**Action:**
- Stop immediately
- No wind-down needed
- No stakeholder management required

**Examples:**
- Feature: <1% usage, no known users → Remove in next deploy
- Channel: Experimental test that failed → Stop today
- Customer: Free tier user causing support burden → Block immediately
- Time: Voluntary activity with no commitment → Just stop

**KILL is rare. Most things need SUNSET.**

---

## Reality-Check Integration

**Before finalizing recommendations, validate:**

### Impact Score Validation

```
For each high-impact claim:
☐ Is this score based on data OR estimation?
☐ If estimation, what's confidence level (LOW/MED/HIGH)?
☐ Could this be wishful thinking?
☐ What evidence supports this score?

If confidence LOW:
→ Flag for testing before major resource shift
→ Add "Validate with 30-day test" recommendation
→ Don't sunset based on LOW-confidence scores alone
→ Output MEASUREMENT PLAN (see below)
```

**MEASUREMENT PLAN (Output When Data is Weak):**

When confidence is LOW or data_type is UNKNOWN/ESTIMATED:

```
MEASUREMENT PLAN for [Item]

What to measure:
- Primary metric: [X]
- Secondary metric: [Y]

How to measure:
- Tool/method: [Analytics, tracking, manual log]
- Frequency: [Daily, weekly, monthly]

Timebox:
Duration: [7 / 14 / 30 days]

Success thresholds:
- PROMOTE to FOCUS if: [Metric > threshold]
- Keep as SEED if: [Metric meets minimum]
- SUNSET if: [Metric < threshold]

Action after measurement:
- Re-run 80/20 with actual data
- Make evidence-based decision
```

**Example:**

```
MEASUREMENT PLAN for TikTok channel

What to measure:
- Primary: Qualified leads (email signups)
- Secondary: Engagement rate

How: UTM tracking + Mixpanel, weekly review

Timebox: 30 days

Thresholds:
- PROMOTE if: >5 qualified leads/week
- SEED if: 2-5 leads/week
- SUNSET if: <2 leads/week

Action: Re-run 80/20 with TikTok data
```

---

### Constraint Reality-Check

```
For each "Sunset/Kill" recommendation:
☐ Are there hidden dependencies?
☐ Will this anger important stakeholders?
☐ Is there a contract/commitment?
☐ What's the actual exit cost?
☐ Is this decision REVERSIBLE or IRREVERSIBLE?

DECISION TYPE GATE:

REVERSIBLE decisions (lower bar for action):
- Can undo with <1 week effort
- No burned bridges
- Example: Pause channel, deprecate feature (can restore)
→ Proceed with normal confidence threshold

IRREVERSIBLE decisions (higher bar required):
- Cannot undo OR very expensive to reverse
- Burned bridges, lost relationships
- Example: Fire customer, cancel contract, rebrand
→ Require HIGH confidence + longer validation
→ Mandatory sunset period (can't kill immediately)

If irreversible + confidence <HIGH:
→ Move to SEED with measurement plan
→ Don't kill until you have proof


If constraints exist:
→ Move from KILL to "Phase out over [timeframe]"
→ Or "Minimum viable maintenance" strategy
```

---

### Capacity Reality-Check

```
For "Focus" recommendations:
☐ Do you have capacity to do MORE?
☐ What would you need to STOP to make room?
☐ Is "do more" actually possible?

If capacity constrained:
→ Must identify specific items to CUT
→ Can't just add without subtracting
→ Force explicit tradeoffs
```

---

## Integration with Other Skills

### Strategist Integration

```
80/20 identifies WHAT to focus on
→ Strategist determines SEQUENCE

Workflow:
1. 80/20: "Focus on features A, B, C"
2. Strategist: "Build in order: B → A → C (B enables A)"
```

**Why both needed:**
- 80/20 filters to vital few
- Strategist sequences the vital few for maximum leverage

---

### Auditor Integration

```
Auditor detects DRIFT patterns
→ 80/20 quantifies WASTE

Workflow:
1. Auditor: "You're scattered across 12 initiatives"
2. 80/20: "2 initiatives create 75% of results, kill 8"
```

**Why both needed:**
- Auditor diagnoses the disease (scattered focus)
- 80/20 prescribes the cure (ruthless prioritization)

---

### Reality-Check Integration

```
80/20 recommends FOCUS areas
→ Reality-Check validates CLAIMS

Workflow:
1. 80/20: "Channel X drives 60% of leads" (HIGH impact)
2. Reality-Check: "Is that actually true? Show data."
3. If validated → Focus. If not → Re-score.
```

**Why both needed:**
- 80/20 makes focus decisions
- Reality-Check prevents focus on wrong things

---

### VEF Integration

```
80/20 identifies vital FEATURES
→ VEF builds product around them

Workflow:
1. 80/20: "Features X, Y drive 80% of value"
2. VEF: "Build v2.0 doubling down on X and Y"
```

---

## Output Templates

### FAST MODE Output

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
80/20 ANALYSIS: [Domain]
Metric: [What we're optimizing for]
Items analyzed: [N]
Data quality: [Exact / Estimated / Mixed / Qualitative]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

VITAL FEW (Focus on these):

1. [Item Name]
   Impact: [X]/10, Ease: [Y]/10, Alignment: [Z]/10
   Priority Score: [Score]
   Contribution: [Y]% of total [IF exact data]
   OR Rank: #1 (estimated) [IF estimated data]
   Cumulative: [Z]% [IF exact] OR ~Z% (approx) [IF estimated]
   Data state: [exact/estimated - confidence: HIGH/MED/LOW]
   Action: FOCUS - [Specific recommendation]

2. [Item Name]
   Impact: [X]/10, Ease: [Y]/10, Alignment: [Z]/10
   Priority Score: [Score]
   Contribution: [Y]% [IF exact] OR Rank: #2 [IF estimated]
   Cumulative: [Z]% [IF exact] OR ~Z% [IF estimated]
   Data state: [exact/estimated - confidence: HIGH/MED/LOW]
   Action: FOCUS - [Specific recommendation]

[Repeat for top items reaching ~80% threshold]

─────────── 80% THRESHOLD ───────────
[Items above = vital few]
[Items below = trivial many]

DELEGATE/AUTOMATE/SEED/SUNSET:

[Item Name]
   Impact: [X]/10, Ease: [Y]/10, Alignment: [Z]/10
   Priority Score: [Score]
   Action: DELEGATE - [To whom/what]

[Item Name]
   Impact: [X]/10, Ease: [Y]/10, Alignment: [Z]/10
   Priority Score: [Score]
   Action: AUTOMATE - [Tool/process]

[Item Name]
   Impact: [X]/10, Ease: [Y]/10, Alignment: [Z]/10
   Priority Score: [Score]
   Action: SEED - [Test for 14-30 days, measure X, threshold: Y]

[Item Name]
   Impact: [X]/10, Ease: [Y]/10, Alignment: [Z]/10
   Priority Score: [Score]
   Decision type: [Reversible / Irreversible]
   Action: SUNSET - [Timeline: announce X, wind down Y, full sunset Z]

[Item Name] (RARE - only if no dependencies + reversible)
   Impact: [X]/10, Ease: [Y]/10, Alignment: [Z]/10
   Priority Score: [Score]
   Decision type: Reversible
   Action: KILL - [Stop immediately]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SUMMARY
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PARETO RATIO: [X]% of items → [Y]% of results [IF exact data]
OR: Top [X] items = vital few [IF estimated]

RECOMMENDED ACTIONS:

FOCUS (Do More):
- [Item 1]: [Specific action]
- [Item 2]: [Specific action]

DELEGATE (Hand Off):
- [Item]: [To whom]

AUTOMATE (Systematize):
- [Item]: [Tool/process]

SEED (Test & Measure):
- [Item]: [14-30 day test, measure X, decide based on threshold]

SUNSET (Wind Down):
- [Item]: [Timeline + stakeholder plan]

KILL (Immediate Stop - if applicable):
- [Item]: [Only if reversible + no dependencies]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
EXPECTED IMPACT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Before: [N] items consuming resources evenly
After: Focus on [X] vital items (Y% of total)

Resource freed: [Z]% (from sunset/automated items)
Expected results: [IF exact data: X% from Y% effort]
                  [IF estimated: Higher leverage allocation (qualitative)]

Confidence: [HIGH / MEDIUM / LOW]
Basis: [Exact data / Estimates / Mixed]

[IF LOW confidence on key items:]
MEASUREMENT PLANS REQUIRED:
- [Item]: Measure [X] for [Y] days
- [Item]: Measure [X] for [Y] days

Resource freed: [Z]% (from killed/automated items)
Expected results: [A]% of current output from [B]% of effort

Confidence: [LOW / MEDIUM / HIGH]
Basis: [Data / Estimation / Mixed]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEXT STEPS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

IMMEDIATE (This Week):
1. [Action]
2. [Action]

SHORT-TERM (This Month):
1. [Action]
2. [Action]

ONGOING:
- Monitor: [Key metric to track]
- Re-analyze: [When to re-run 80/20]
```

---

### DEEP MODE Output

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
COMPREHENSIVE 80/20 ANALYSIS
Domain: [X]
Date: [Date]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 1. CURRENT STATE ANALYSIS

Total items: [N]
Current resource allocation: [Roughly equal / Heavily weighted / Mixed]

Distribution analysis:
- Top 20% of items contribute: [X]% of results
- Middle 30% contribute: [Y]% of results  
- Bottom 50% contribute: [Z]% of results

Pareto ratio: [X/Y] (e.g., 82/18, 75/25, 90/10)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 2. MULTI-METRIC SCORING

[Item Name]
- Impact Score: [X]/10 ([Metric 1])
- Effort Score: [Y]/10 (1=high effort, 10=low effort)
- Strategic Value: [Z]/10
- Dependencies: [What depends on this / What this depends on]
- Combined Score: [(Impact × Strategic) / Effort] = [Score]

[Repeat for each item]

Ranking by combined score:
1. [Item] - Score: [X]
2. [Item] - Score: [Y]
...

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 3. CONSTRAINT ANALYSIS

Items that CANNOT be changed:
- [Item]: [Reason - contract/legal/dependency]
- [Item]: [Reason]

Items with HIGH exit costs:
- [Item]: [Exit cost - $X or Y hours or Z risk]

Items with dependencies:
- [Item]: Required by [other items]
- [Item]: Enables [other items]

Strategic constraints:
- [Competitive requirement]
- [Market expectation]
- [Platform requirement]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 4. OPPORTUNITY COST ANALYSIS

Current allocation:
- [Item 1]: [X]% of resources → [Y]% of results
- [Item 2]: [X]% of resources → [Y]% of results

Opportunity cost of low-impact items:
- Keeping [Item]: Costs [X hours/week]
  - Could instead: [Alternative use of resources]
  - Potential gain: [Estimated impact]

Highest opportunity costs:
1. [Item] - [Resource cost] could produce [Alternative value]
2. [Item] - [Resource cost] could produce [Alternative value]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 5. DETAILED ACTION PLAN

FOCUS TIER (Vital Few):

[Item 1]
Current state: [Description]
Target state: [What success looks like]
Actions:
- [Specific action 1]
- [Specific action 2]
Timeline: [Dates]
Resources needed: [What's required]
Success metric: [How to measure]

[Repeat for each focus item]

─────────────────────────────────────────

DELEGATE TIER:

[Item]
Why delegate: [Reason]
Delegate to: [Person/role/service]
Transition plan:
- Week 1: [Step]
- Week 2: [Step]
Handoff complete: [Date]
Monitoring: [How to ensure quality]

[Repeat for each delegate item]

─────────────────────────────────────────

AUTOMATE TIER:

[Item]
Current manual process: [Description]
Automation approach: [Tool/system/workflow]
Implementation:
- Setup: [Time/cost]
- Testing: [Timeline]
- Launch: [Date]
Expected time savings: [Hours/week]
ROI timeline: [Breakeven point]

[Repeat for each automate item]

─────────────────────────────────────────

KILL TIER:

[Item]
Why kill: [Impact score + opportunity cost]
Exit plan:
- Announce: [Date]
- Wind down: [Process]
- Fully sunset: [Date]
Affected stakeholders: [Who to notify]
Migration plan (if needed): [Alternative for users]
Resources freed: [Time/money/attention]

[Repeat for each kill item]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 6. RISK ASSESSMENT

Risks of recommended changes:

HIGH RISK:
- [Change]: [Potential downside]
  Mitigation: [How to reduce risk]

MEDIUM RISK:
- [Change]: [Potential downside]
  Mitigation: [How to reduce risk]

LOW RISK:
- [Changes with minimal downside]

Validation tests recommended:
- [Item]: Run 30-day test before full commit
- [Item]: A/B test before killing completely

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 7. IMPLEMENTATION TIMELINE

WEEK 1:
- [Kill easiest waste]
- [Start automation for X]
- [Protect focus time for vital items]

WEEK 2-4:
- [Delegate handoffs complete]
- [Automation testing]
- [Increase focus on top 3]

MONTH 2:
- [Full transition complete]
- [Re-measure impact]
- [Iterate based on results]

QUARTERLY:
- Re-run 80/20 analysis
- Adjust based on new data
- Prevent drift back to scattered

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 8. SUCCESS METRICS

Track these to measure impact:

Primary metric: [What you're optimizing]
- Baseline: [Current state]
- Target: [After implementation]
- Measure: [How often]

Resource utilization:
- Before: [X]% of time on vital items
- Target: [Y]% of time on vital items

Focus ratio:
- Before: Scattered across [N] items
- Target: Focused on [M] items

Results per effort:
- Before: [Metric] per [effort unit]
- Target: [Metric] per [effort unit]
- Expected lift: [X-Y]%

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CONFIDENCE ASSESSMENT:

Score accuracy: [HIGH / MEDIUM / LOW]
Basis: [Actual data / Estimates / Mixed]

Data gaps:
- [What we don't know]
- [How to get data]

Recommendation strength:
- STRONG (confident): [Actions with high confidence]
- MODERATE (test first): [Actions needing validation]
- WEAK (speculative): [Actions based on assumptions]
```

---

## Domain-Specific Examples

### Example: Product Features

**Scenario:** SaaS product with 25 features, unclear what matters

**Analysis:**
1. List all 25 features
2. Score by usage data (Google Analytics, Mixpanel)
3. Rank by impact
4. Find 80% threshold

**Typical result:**
- 5 features (20%) drive 85% of usage
- 8 features (32%) account for next 10%
- 12 features (<5% usage each) = kill candidates

**Actions:**
- Focus: Improve top 5 features
- Delegate: Maintain middle 8 (junior dev)
- Kill: Deprecate bottom 12

---

### Example: Time Allocation

**Scenario:** Operator spread across 10 activities, low output

**Analysis:**
1. List all time allocations
2. Score by output (revenue, progress, satisfaction)
3. Calculate time vs impact ratio
4. Rebalance ruthlessly

**Typical result:**
- 2 activities (20% of time) produce 70% of results
- 3 activities (30% of time) produce 20% of results
- 5 activities (50% of time) produce 10% of results

**Actions:**
- Focus: 60% of time on top 2
- Delegate: Middle 3 to team
- Kill: Bottom 5 completely

---

### Example: Marketing Channels

**Scenario:** 8 marketing channels, uneven results

**Analysis:**
1. List all channels
2. Score by leads + conversion quality
3. Factor in cost per channel
4. ROI calculation

**Typical result:**
- 2 channels drive 75% of qualified leads
- 3 channels produce leads but low quality
- 3 channels produce nothing

**Actions:**
- Focus: Double budget on top 2
- Automate: Middle 3 with tools
- Kill: Bottom 3 immediately

---

## Critical Reminders

1. **Data state declaration mandatory** - Flag each item: exact/estimated/unknown + confidence level
2. **Percent-math gating** - Only allow precise % if data_type=exact, otherwise use ranks/approximations
3. **Priority formula consistent** - Impact × Ease × Alignment in FAST and DEEP, not just Impact alone
4. **DEEP mode intake complete** - Effort, maintenance, strategic alignment, optionality, dependencies required
5. **SUNSET not KILL** - Most things need wind-down, KILL only if no dependencies + reversible
6. **SEED bucket protects future** - Don't kill experiments/enabling work, timebox them with measurement plan
7. **Unit of analysis check** - Items must be same abstraction layer, force bucketing if mixed
8. **Auto-bucket if >15 items** - Reduce noise, clarify vital few through categorization
9. **Decision type gate** - Reversible = lower bar, Irreversible = HIGH confidence + sunset required
10. **Measurement plan for weak data** - Output what/how/when/thresholds when confidence LOW
11. **Pareto of Pareto operational** - Second pass on vital few finds vital vital few (64% from 4%)
12. **Integration is key** - 80/20 filters, Strategist sequences, Auditor diagnoses, Reality-Check validates
13. **Constraints respected** - Contracts, commitments, dependencies = SUNSET not KILL
14. **Re-run quarterly** - Priorities shift, re-analyze with fresh data
15. **Sunset is scheduled, not emotional** - Timeline-based wind-down, not courage-based decision
16. **Focus requires subtraction** - Can't add without cutting, capacity math is real

---

**80/20 Analysis v1.1: Mechanical, data-aware, sunset-focused filter for ruthless prioritization.**
