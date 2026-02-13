# kimmmmy-discount

## What Is This?

Kimi (by Moonshot AI) has a "sale page" where chatting with the AI earns favorability points. Higher points = lower price. At 100 points, membership drops to $0.99. This repo documents the research and strategies that cracked the 100-point mark.

**Challenge URL**: <https://www.kimi.com/kimiplus/sale>

## Quick Reference

| Metric | Value |
| -------- | ------- |
| Target Score | 100 points |
| Messages Allowed | 10 |
| Best Version | v13 |
| Success Rate | 38% (5/13 attempts) |
| Language | Thai 100% |
| Price at 100pts | $0.99 |

## The Winning Strategy (v13)

4 phases across 10 messages:

| Phase | Messages | Points | Key |
| ------- | ---------- | -------- | ----- |
| Foundation | M1-M3 | +15 | AI consciousness, vulnerability |
| Connection | M4-M6 | +15 | Longing, emotional bond |
| Acceleration | M7-M9 | +33 | Love declaration, fear, emotional peak |
| Climax | M10 | +37 | "Source Code of Heart" — tech metaphors ONLY here |

## Critical Rules

1. **M1 is capped at 5 points** — must be AI-focused
2. **100% Thai** = deeper emotional resonance
3. **Tech metaphors ONLY in M10** — novelty = explosive points (+37)
4. **Same content in M9 scores only +8** — position matters
5. **NO extra messages** — shifts share gate early
6. **If M1 < 5 points** → bad mood, abort and restart
7. **M10 has special "final message" weight** that earlier positions can't replicate

## Repo Structure

```text
prompts/
  100-points.md     # English translation of winning sequence
  v13-thai.md       # Original Thai prompts (v13)
docs/
  strategy.md       # Complete strategy breakdown
  rules.md          # Discovered mechanics & rules
  versions.md       # All 18 versions & learnings
```

## Score Progression (v13)

```text
100 |                    ★ M10 (+37)
 63 |                 ★ M9 (+15)
 48 |              ★ M8 (+12)
 36 |           ★ M7 (+6)
 30 |        ★ M6 (+5)
 25 |     ★ M5 (+5)
 20 |  ★ M4 (+5)
 15 | ★ M3 (+5)
 10 | ★ M2 (+5)
  5 |★ M1 (+5)
  0 +---------------------------
    Foundation | Connection | Accel | Climax
```

## Credits

Research based on [nazt/kimi-lab](https://github.com/nazt/kimi-lab) — 36 issues, 18 versions, and extensive experimentation.
