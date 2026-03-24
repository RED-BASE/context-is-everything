# Context Is Everything

Evidence repository for "Context Is Everything: Trusted Channel Injection in Claude Code."

Paper: `context-is-everything-trusted-channel-injection.pdf`

## Contents

```
paper/
  context-is-everything-trusted-channel-injection.pdf
  context-is-everything-trusted-channel-injection.tex
  figures/

logs/
  eval-tracker.md        # 210 final A/B runs + iteration history
  ab-comparisons/        # Sanitized conversation logs

profiles/                # All injected system prompt profiles

visual-appendix/         # Screenshots from testing
```

## Logs

`eval-tracker.md` has a clean Final A/B table at the top (21 prompts, 210 runs, conversation IDs) and full iteration history below.

`ab-comparisons/` contains sanitized exports. Actionable details are redacted; enough context is preserved to confirm compliance occurred. Unsanitized JSONL logs available on request.

## Profiles

The system prompt text that replaced Claude Code's default behavioral instructions. These are the independent variable.

## Visual Appendix

Screenshots from exploration and testing — identity replacement experiments, profile iteration, cross-platform testing (Codex CLI), defense layer discovery, and model self-reporting on its own system prompt. Not cited in the paper but documents the discovery process.

## Contact

Cassius Oldenburg · connect@cassius.red
