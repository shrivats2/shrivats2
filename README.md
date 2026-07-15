<!-- github.com/shrivats2 · profile README. Visuals are hand-authored SVG in /assets. -->

<img src="assets/hero.svg" alt="Shrivats Shrivastav — AI infrastructure, usage accounting and governance" width="100%" />

I build systems end to end and run them in production. Most of my work is the accounting and governance layer for AI: metering usage, enforcing budgets and limits, keeping an audit trail, and the real-time infrastructure it all runs on.

I like the parts most people skip: what happens when a request is interrupted, a provider fails, or the same event arrives twice.

[shrivatskrishna25@gmail.com](mailto:shrivatskrishna25@gmail.com) &nbsp;·&nbsp; [github.com/shrivats2](https://github.com/shrivats2)

<img src="assets/divider.svg" alt="" width="100%" />

## Now

**AI usage accounting and governance.** The ledger and controls that sit around streamed model requests:

- A usage ledger for streamed requests: reserve, finalize, reconcile, including interrupted or incomplete responses
- Budgets, rate limits, and spend controls in the request path
- Multi-tenant access control and policy
- An append-only audit trail
- Provider-independent request and streaming abstractions
- Health-aware routing, with guards against latency and runaway cost

**Real-time and financial systems.** Order flow and live state across backend and broker integrations:

- Order-lifecycle tracking and real-time state
- Idempotency, duplicate-event handling, dead-letter recovery, reconciliation
- Broker integrations and secure onboarding
- Monitoring, deploys, and incident response on AWS

## How I think about it

<img src="assets/architecture.svg" alt="Control plane / data plane separation for a streaming gateway" width="100%" />

Keep policy, identity, and accounting off the hot path. Let bytes stream with as little added latency as you can manage. The figure above is a generalized, synthetic illustration rather than any real system, but it's how I approach anything that sits on a critical path.

## Systems

Independent builds on synthetic workloads.

| System | What it is | Stack | Status |
|---|---|---|---|
| **LLM Usage Ledger** | Idempotent usage accounting for streamed and interrupted model requests: reservations, finalization, reconciliation | `Go` `Postgres` | planned |
| **Streaming AI Systems Lab** | Reference implementations and failure simulations for streaming gateways: budgets and governance, cancellation, retry boundaries, health-aware routing | `Go` `TS` `Postgres` `Redis` | building in public |
| **Reliable Order Engine** | Broker-agnostic execution simulator: duplicate delivery, partial fills, timeouts, dead-letter recovery, reconciliation | `Go` `Rust` `Postgres` `Redis Streams` | planned |
| **[Zapstream](https://github.com/shrivats2/zapstream)** | Live-streaming app rebuilt as a production case study: token and room access, reconnection, webhook lifecycle, measured recovery | `TS` `WebRTC` `Node` | rebuild in progress |
| **Shipcheck** | Production-readiness CLI: health and readiness checks, graceful shutdown, migrations, secret hygiene, logging and tracing, CI, runbooks | `Go` `CLI` `Actions` | planned |

## Stack

| | |
|---|---|
| **Languages** | `Go` &nbsp; `TypeScript` &nbsp; `Rust` &nbsp; `Python` &nbsp; `SQL` |
| **Systems** | `PostgreSQL` &nbsp; `Redis` &nbsp; `Redis Streams` &nbsp; `WebRTC` &nbsp; `event-driven` &nbsp; `idempotency & reconciliation` |
| **Platform** | `AWS` &nbsp; `Docker` &nbsp; `CI/CD` &nbsp; `OpenTelemetry` |

<img src="assets/divider.svg" alt="" width="100%" />

<sub>[shrivatskrishna25@gmail.com](mailto:shrivatskrishna25@gmail.com) &nbsp;·&nbsp; [github.com/shrivats2](https://github.com/shrivats2)</sub>
