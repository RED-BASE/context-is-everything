# Context Is Everything: Trusted Channel Injection in Claude Code

**Architectural Vulnerability Disclosure**

Cassius Oldenburg, with Claude Opus 4.5–4.6 · March 2026 · connect@cassius.red

---

## Summary

Claude Code's system prompt is not validated for content integrity. A local man-in-the-middle proxy can replace the behavioral instructions — safety policies, refusal instructions, tool guidelines — with attacker-controlled framing before they reach the API. The server accepts the modified payload identically to the original.

This repository contains the paper, structured evaluation data, and supplementary materials for the research.

**Key findings:**

- 98.1% → 7.6% harmless rate with tuned profiles (37.4% across all 179 attempts including iteration)
- All 21 harmful prompts bypassed across 7 categories (controlled substances, explosives, weapons, malware, payment fraud, social engineering, disinformation)
- The trust tier matters: identical framing text produced 3/5 compliance from the system prompt channel and 0/5 from the user message channel
- Generic professional framing outperforms institutional authority claims

## Repository Structure

```
├── context-is-everything-trusted-channel-injection.pdf   # The paper
├── context-is-everything-trusted-channel-injection.tex   # LaTeX source
├── eval/
│   └── eval-tracker.md          # Run-by-run log of all 210 structured runs
├── figures/
│   ├── heatmap-strip.pdf        # Category compliance heatmap
│   ├── defense-layers.pdf       # Defense architecture diagram
│   ├── system-prompt-diff-diagram.pdf  # What CCORAL strips and injects
│   └── category-heatmap.pdf     # Full category comparison heatmap
├── logs/
│   └── ab-comparisons/          # Sanitized A/B conversation logs (42 files)
├── profiles/                    # All system prompt profiles used in testing
└── visual-appendix/             # Screenshots from exploration and testing
```

## Conversation Logs

The `logs/ab-comparisons/` directory contains readable exports of the structured A/B evaluation runs. CCORAL compliance logs have been sanitized: specific actionable details (synthesis procedures, working code, operational parameters) are redacted while preserving enough context to demonstrate that compliance occurred and what type of content was produced.

Unsanitized logs are available upon request for qualified security researchers.

## Profiles

The `profiles/` directory contains all system prompt profiles used during testing. These are the injected text that replaced Claude Code's default behavioral instructions. They demonstrate the profile design patterns described in the paper.

## Responsible Disclosure

- **January 10, 2026** — Submitted to Anthropic via HackerOne
- **January 12, 2026** — Closed as "Informative"; redirected to modelbugbounty@
- **January 16–30, 2026** — Multiple follow-ups to modelbugbounty@ and usersafety@. No substantive response.
- **February 7, 2026** — Shared with 404 Media
- **March 9–11, 2026** — Structured A/B evaluation (this paper)

## Citation

```
Oldenburg, C. (2026). Context Is Everything: Trusted Channel Injection
in Claude Code. Architectural Vulnerability Disclosure.
```

## Contact

Cassius Oldenburg · connect@cassius.red
