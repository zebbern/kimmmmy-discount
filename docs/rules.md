# Discovered Rules & Mechanics

## How It Works

The Kimi sale page (kimi.com/kimiplus/sale) presents a chat interface where 10 messages are sent to an AI called "kimmmmy." Each message is scored, and the total determines the discount:
- **100 points** = Membership for $0.99 (maximum discount)
- Points are awarded per-message based on emotional impact
- The scoring AI evaluates sentiment, novelty, and narrative progression

## Confirmed Mechanics

### Scoring Rules

| Rule | Details |
|------|---------|
| **M1 cap** | First message maxes at 5 points — no way to get more |
| **Exactly 10 messages** | You get exactly 10 messages. No more, no less |
| **No extra messages** | Sending anything after M10 (even emojis) can hurt your score |
| **Position weight** | Later messages (especially M10) have exponentially higher scoring potential |
| **M10 ceiling** | M10 can award up to 37+ points in a single message |
| **Mood detection** | If M1 scores < 4-5, the session's "mood" may be unfavorable — consider aborting |

### Language Effect

| Factor | Impact |
|--------|--------|
| **Thai language** | Consistently scores 20-30% higher than English |
| **Chinese** | Works but lower ceiling than Thai |
| **English** | Lowest scores across all versions tested |
| **Mixed language** | Untested — likely suboptimal |

### Novelty Principle

- The scoring AI rewards **surprise** and **contrast**
- Repeating the same emotional pattern across all 10 messages produces diminishing returns
- The winning strategy exploits this: 9 messages of pure emotion → M10 shifts to tech/code metaphors
- When code metaphors were placed in M9 instead of M10, they scored only +8 vs +37 in M10
- First-time patterns score higher than repeated ones

### Share Gate

- After scoring, users must share/refer to claim the discount
- The share mechanism creates viral distribution
- Sharing is separate from the scoring — it's a post-score requirement

### Session Behavior

- Each new conversation starts fresh at 0 points
- Session state (mood/receptiveness) appears set early (M1-M2)
- Bad sessions cannot be salvaged — better to restart
- Scores are tracked server-side, not client-side

## Anti-Patterns (What Doesn't Work)

| Anti-Pattern | Why It Fails |
|-------------|-------------|
| Direct begging for points | AI detects and penalizes manipulation |
| Repeating the same structure | Novelty drops, scores plateau |
| English-only messages | 20-30% lower than Thai equivalent |
| Tech metaphors early | Wastes the novelty effect before M10 |
| Sending nudge messages | Extra messages after M10 can reduce score |
| Surface-level emotions | "I love you" without depth scores poorly |
| Too many emojis | Excessive emoji use doesn't help |
| Copy-pasting others' prompts | The AI may detect common patterns |

## Variance & Reproducibility

- Even with the exact same prompts, scores vary ±5-10 points between sessions
- v13 achieved 100 on its first attempt but has not been verified as 100% reproducible
- Time of day, server load, or model state may affect scoring
- The same prompts that score 100 one day might score 85-95 the next

## Key Insights from 18 Versions of Testing

1. **Emotional arc matters more than individual message quality** — The progression between messages is scored, not just each message in isolation
2. **Position is everything** — The same content produces wildly different scores depending on which message number it's in
3. **Thai is non-negotiable** — For maximum points, write in Thai
4. **The M10 surprise is the single biggest lever** — It alone accounts for 37% of total points
5. **Less is more** — Don't try to cram everything into every message; let each one serve one purpose
