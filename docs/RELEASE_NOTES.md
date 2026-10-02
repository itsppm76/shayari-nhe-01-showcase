# Release notes

## v134 - 2 October 2026

Latency and security release. Architecture-level summary.

### Performance
- Reworked the model router. At 14 concurrent users, client-side latency dominated, so per-turn work was reduced.
- Fewer repeated data reads per message; shared context is read once and reused.
- Independent outbound requests run in parallel with a serial fallback.
- Lightning mode does less bookkeeping per turn.
- Per-mode time budgets and cooldowns keep one slow provider from stalling a turn.
- Embeddings moved to a currently supported model.

### Reliability
- New gateway fallback tier at the end of the router. If direct providers are limited or down, the turn can still be answered.
- Gateway failures are classified so the router moves on instead of aborting.

### Security
- A privileged decision that previously relied on a browser-supplied flag is now decided on the server only.

### Quality
- Priority fixes P0 to P2 from the investigation are done.
- 39 of 39 automated checks passing, per the developer report.

### Not included
Source code, prompts, configuration and credentials stay private.
