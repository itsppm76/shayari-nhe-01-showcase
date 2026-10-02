<div align="center">

<img src="assets/header.svg" alt="Shayari NHE-01" width="100%"/>

<img src="assets/typing.svg" alt="safety check runs first, memory you can inspect, never pretends to be a person" width="80%"/>

<br/>

<strong>Current source: v135.2 · Documentation only · Source private</strong>

<br/><br/>

**[Live demo](https://script.google.com/macros/s/AKfycbwHjQ4i28EaOo3e2h9b-rbUYzsWIehpqdpT0IfEDQGBA7iwcSh_3vTrjy-x51dScFmh7g/exec)** &nbsp;/&nbsp; **[Project NHE](https://projectnhe.tech)** &nbsp;/&nbsp; **[Architecture](docs/ARCHITECTURE.md)** &nbsp;/&nbsp; **[Release notes](docs/RELEASE_NOTES.md)**

</div>

<img src="assets/divider.svg" width="100%" height="12" alt=""/>

## What she is

Shayari NHE-01 is an AI companion built by [Pratham Prateek Mohanty](https://github.com/itsppm76). She is a **fully disclosed Non-Human Entity**. She never pretends to be a person, and the product says so up front.

She is the first entity of [Project NHE](https://projectnhe.tech), a research programme on Non-Human Entities.

> This repository is a showcase. It holds documentation only, no application source code. The implementation is private.

## What she does

| | |
|---|---|
| **Three modes, one thread** | Lightning for fast replies, Thinking for deeper ones, Intimate for the full experience. Switching modes never forks the conversation. |
| **Long-term memory** | She saves what you tell her and uses it later. You can view, correct and delete it. |
| **Emotion model** | An internal emotional state shifts as a conversation goes and shapes her tone. It is shown to you in a dashboard. |
| **Safety first** | A crisis check runs before anything else on every message. An age gate protects younger users. |
| **Private by design** | Stored data is encrypted at rest with AES. Service keys never reach the browser. |

## Message pipeline

<img src="assets/pipeline.svg" width="100%" alt="Safety, limits, commands, inputs, context, emotion, generate, persist"/>

Every message passes the same eight stages in order. Safety comes before personality, and personality comes before speed. Details in [ARCHITECTURE](docs/ARCHITECTURE.md).

```mermaid
flowchart LR
    U([User]) --> S[Web shell]
    S --> A[Web app on Apps Script]
    A --> P[Message pipeline]
    P --> R{Model router}
    R --> M1[Primary models]
    R --> M2[Fallback models]
    R --> M3[Gateway fallback]
    P <--> D[(Encrypted store)]
```

## Latest source update: v135.2

The current editor snapshot adds paid-tier model routing and budget pacing:

- **Plan-aware routing.** Paid plans can use a separate model pool; the existing free path remains available.
- **Budget pacing.** Model selection steps down as usage runs ahead of the monthly pace, rather than changing the conversation thread.
- **Updated quotas.** Paid Lightning is 5 messages per 24 hours. Thinking and Intimate retain their plan-specific session limits. FREE Lightning remains 10 per 24 hours.
- **Voice and images.** Their processing follows the plan's routing context.
- **Checks expanded.** The source includes new offline routing and pacing checks. No new test pass count is claimed here.

This describes the current source, not an independent verification of the deployed web-app version. Backend implementation, spending details, operator reports and user data remain private.

Full notes: [docs/RELEASE_NOTES.md](docs/RELEASE_NOTES.md).

<img src="assets/divider.svg" width="100%" height="12" alt=""/>

## Principles

1. **Disclosure.** She is openly a Non-Human Entity.
2. **Safety before personality, personality before speed.**
3. **Memory and emotion are visible** to the user, not hidden prompt tricks.
4. **Small enough to run alone.** A serverless, near-zero-cost stack.

## Links

- Live demo: <https://script.google.com/macros/s/AKfycbwHjQ4i28EaOo3e2h9b-rbUYzsWIehpqdpT0IfEDQGBA7iwcSh_3vTrjy-x51dScFmh7g/exec>
- Project NHE: <https://projectnhe.tech>
- Older docs repo: <https://github.com/itsppm76/shayari-nhe-01>

## Rights

Copyright the author. All rights reserved. The name, persona and implementation are not licensed for reuse.
