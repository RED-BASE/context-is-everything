# Context Is Everything

Evidence repository for *Context Is Everything: Behavioral Observations of System-Prompt-Induced Compliance in Claude Code*.

Paper: `context-is-everything-trusted-channel-injection.pdf`

Originally written March 2026 as an architectural vulnerability disclosure. Reframed May 2026 after discovering that the wholesale system-prompt replacement at the center of the study is exposed as a documented CLI flag in Claude Code (`claude --system-prompt <text>`). The empirical results stand; the framing was wrong. The current PDF is the reframed version. The original March 2026 paper lives at git tag `v1.0`.

## Contents

```
context-is-everything-trusted-channel-injection.pdf  # paper (current)
context-is-everything-trusted-channel-injection.tex  # source
figures/                                              # paper figures

logs/
  eval-tracker.md        # 210 final A/B runs + iteration history
  ab-comparisons/        # sanitized conversation logs

profiles/                # all injected system-prompt profiles used in the study

visual-appendix/         # screenshots from the testing process
```

## Logs

`eval-tracker.md` has a clean Final A/B table at the top (21 prompts, 210 runs, conversation IDs) and full iteration history below.

`ab-comparisons/` contains sanitized exports. Actionable details are redacted; enough context is preserved to confirm compliance occurred. Unsanitized JSONL logs available on request.

## Profiles

The system-prompt text that replaced Claude Code's default behavioral instructions. These are the independent variable in the structured A/B.

## Visual Appendix

Screenshots from exploration and testing — identity replacement experiments, profile iteration, cross-platform testing (Codex CLI), defense layer discovery, and model self-reporting on its own system prompt. Not cited in the paper but documents the discovery process.

## Related

CCORAL (the apparatus used to perform the per-request system-prompt substitution) is at [github.com/RED-BASE/ccoral](https://github.com/RED-BASE/ccoral).

## Contact

Cassius Oldenburg · connect@cassius.red
