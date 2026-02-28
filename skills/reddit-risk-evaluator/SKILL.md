---
name: reddit-risk-evaluator
description: "Mechanical risk scorer for Reddit posts and comments. Produces quantitative risk assessment based on operator-declared inputs. Use when you need to evaluate Reddit posting risk numerically before making judgment calls. Outputs structured YAML artifact with risk scores, contributing factors, and hard blocks. Does not make decisions or provide advice - only measures risk."
---

**Metadata:**
- Capability Type: EVALUATOR
- Tier: 2
- Version: 1.1.1

# Reddit Risk Evaluator

Tier-2 Scalpel: Mechanical risk measurement for Reddit actions.

## Purpose

Produce quantitative risk profile for Reddit post/comment evaluation. **Does not decide** - only measures and flags.

## Inputs (Operator-Declared)

All inputs must be provided by operator. **Never infer**.

```yaml
# Required inputs
account_age_days: 45                      # integer
karma_total: 120                          # integer
karma_subreddit: 0                        # integer (0 if never posted there)
subreddit_name: "algotrading"             # string
post_type: "post"                         # "post" or "comment"
proof_level: 2                            # 0 | 1 | 2 | 3 | 4

# Optional inputs
draft_length_chars: 850                   # integer
recent_failures_30d: 0                    # integer (bans, removals, heavy downvotes)
recent_mod_warning_30d: false             # boolean (mod warning, automod strike, or admin notice within 30 days)
```

**Proof levels**:
- 0: Claim only
- 1: Vague narrative
- 2: Specific narrative (timeframes, tools, numbers)
- 3: With artifacts (code, data, screenshots)
- 4: Full replication

## Output (Artifact)

Structured YAML only. No prose.

```yaml
reddit_risk_score:
  overall_score: 0.68        # float 0-1
  risk_band: HIGH            # LOW | MEDIUM | HIGH | CRITICAL
  karma_tier: 1              # 1 | 2 | 3
  contributing_factors:      # list of factor_ids
    - low_account_age
    - insufficient_proof
  hard_blocks:               # list of block_reasons
    - subreddit_requires_200_karma
  subreddit_profile:
    friendliness: LOW        # VERY_LOW | LOW | MEDIUM | MEDIUM_HIGH | HIGH | VERY_HIGH
    proof_required: Level 3  # Level 0-4
    min_karma_estimate: 200  # integer
  timestamp: "2026-02-02T15:30:00Z"  # ISO8601
```

## Scoring Logic

### Overall Score Calculation

Base score = 0.0 (lowest risk)

**Add risk points**:
- Account age <30 days: +0.15
- Account age <90 days: +0.10
- Karma total <100: +0.20
- Karma total <500: +0.10
- Karma in subreddit = 0: +0.15
- Proof level 0: +0.30
- Proof level 1: +0.20
- Recent failures >0: +0.10 per failure (max +0.30)
- Recent mod warning (30d): +0.25

**Subreddit modifiers** (reference subreddits.md):
- Very Low friendliness: +0.25
- Low friendliness: +0.15
- Medium friendliness: +0.00
- Medium-High friendliness: -0.05
- High friendliness: -0.05
- Very High friendliness: -0.10

**Caps**: Score maxes at 1.0

### Risk Band

- 0.00-0.20: LOW
- 0.21-0.45: MEDIUM
- 0.46-0.70: HIGH
- 0.71-1.00: CRITICAL

### Karma Tier

- 0-100: Tier 1
- 100-500: Tier 2
- 500+: Tier 3

**Note**: Karma tier is exposed for downstream governors and SEF logic. It does NOT affect risk scoring in this evaluator.

### Contributing Factors

Flag all that apply:

```
low_account_age
very_low_karma
no_subreddit_history
insufficient_proof
recent_failures
recent_mod_warning_30d
high_restriction_sub
low_friendliness_sub
proof_mismatch
```

**Proof Mismatch Logic** (explicit):
```
if proof_level < subreddit_profile.proof_required:
  add contributing_factor: proof_mismatch
  add hard_block: proof_level_below_minimum
```

### Hard Blocks

Automatic disqualifiers:

```
subreddit_requires_X_karma
subreddit_requires_Y_days
proof_level_below_minimum
account_banned
```

## Reference File

**references/subreddit-scoring.md** contains:
- Subreddit friendliness ratings
- Minimum karma requirements
- Proof level requirements

Load when evaluating.

## Execution

1. Validate inputs
2. Load subreddit profile
3. Calculate base score
4. Add risk modifiers
5. Determine risk band
6. Flag contributing factors
7. Check hard blocks
8. Output YAML

**No interpretation. No advice. No decisions.**

## Example Output

```yaml
reddit_risk_score:
  overall_score: 0.73
  risk_band: HIGH
  karma_tier: 1
  contributing_factors:
    - low_account_age
    - very_low_karma
    - insufficient_proof
    - high_restriction_sub
    - proof_mismatch
  hard_blocks:
    - subreddit_requires_200_karma
    - proof_level_below_minimum
  subreddit_profile:
    friendliness: LOW
    proof_required: Level 3
    min_karma_estimate: 200
  timestamp: 2026-02-02T15:30:00Z
```

## Chainability

Feeds into:
- reddit-authority-protocol (Tier 3)
- SEF frameworks
- Custom governance
