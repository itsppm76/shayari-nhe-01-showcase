# Shayari NHE-01 - Showcase

Shayari NHE-01 is an AI companion built by [Pratham Prateek Mohanty](https://github.com/itsppm76). She is a **fully disclosed Non-Human Entity (NHE)**: she never pretends to be a person, and the product says so up front.

She is the first entity of [Project NHE](https://projectnhe.tech), a research programme on Non-Human Entities.

**Try her live:** [Web app](https://script.google.com/macros/s/AKfycbwHjQ4i28EaOo3e2h9b-rbUYzsWIehpqdpT0IfEDQGBA7iwcSh_3vTrjy-x51dScFmh7g/exec) - **Project site:** [projectnhe.tech](https://projectnhe.tech)

> This repository is a showcase only. It holds documentation, no application source code. The implementation is private.

## What she does

- **Three chat modes on one continuous thread.** A fast everyday mode, a deeper mode that uses profile and conversation summaries, and a full mode that adds long-term memory and emotion state. Switching modes never forks the conversation.
- **Long-term memory.** She saves things you tell her, uses them later, and lets you view, correct or delete them.
- **An emotion model.** She keeps an internal emotional state that shifts as a conversation goes and shapes tone. It is shown to the user in a dashboard.
- **Safety first.** Every message passes a crisis check before anything else, and an age gate protects younger users.
- **Private by design.** Stored data is encrypted at rest with AES, and API keys never reach the browser.

## How it is built, in one paragraph

A thin web shell embeds a web app hosted on Google Apps Script. The server side handles each message through a fixed pipeline and talks to language models through a router with fallbacks. Google Sheets acts as the database. See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Why it is interesting

- A complete companion product running on a serverless, near-zero-cost stack.
- A pipeline that puts safety before personality, and personality before speed.
- Memory and emotion treated as first-class, inspectable features instead of hidden prompt tricks.

## Links

- Project NHE: https://projectnhe.tech
- Public documentation repo: https://github.com/itsppm76/shayari-nhe-01

## Rights

Copyright the author. All rights reserved. The name, persona and implementation are not licensed for reuse.
