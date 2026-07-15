<!-- github.com/shrivats2 · profile README. Visuals are hand-authored SVG in /assets. -->

<img src="assets/hero.svg" alt="Shrivats Shrivastav — founder-engineer, systems on the critical path" width="100%" />

I build production systems end to end and run them once they're live. That means the whole loop: talking to users, architecture, backend, infrastructure, and the operational parts most people would rather skip.

Right now that's AI inference infrastructure (in stealth) and real-money financial execution. Both break loudly and cost money when they do, which is the kind of work I'm good at.

[shrivatskrishna25@gmail.com](mailto:shrivatskrishna25@gmail.com) &nbsp;·&nbsp; [github.com/shrivats2](https://github.com/shrivats2)

<img src="assets/divider.svg" alt="" width="100%" />

## Now

**AI infrastructure, stealth.** Founder-engineer on the controls that sit in the critical path of streamed model requests, and the product around them:

- Multi-tenant auth, access control, budgets, and usage limits
- Provider-independent request and streaming abstractions
- Usage metering and reconciliation for interrupted or incomplete requests
- Health-aware routing, plus guards against latency and runaway cost
- Billing-linked access and an append-only audit trail

**Financial execution.** Trader-facing order flow across web, desktop, mobile, backend, and broker integrations:

- Order-lifecycle tracking, and real-time position, order, and risk state
- Broker routing, secure brokerage onboarding, and credential exchange
- Idempotency, duplicate-event handling, dead-letter recovery, reconciliation
- Monitoring, deploys, incident response, and recovery on AWS

<sub>Company code, customer data, and internal architecture stay private. What's here is patterns I've rebuilt independently, and the reasoning behind them.</sub>

## A few results

- Took a production AI infra product from the first design-partner conversations to live usage in a single quarter.
- Held added request-path latency to low single-digit milliseconds while enforcing those controls on streamed requests.
- Ran request lifecycle, usage accounting, and provider-reliability workflows across tens of thousands of production requests.
- Kept a live execution lifecycle moving millions of dollars stable in production.
- Took missed-order incidents from a recurring problem down to near zero.

## How I think about it

<img src="assets/architecture.svg" alt="Control plane / data plane separation for a streaming gateway" width="100%" />

Keep policy, identity, and accounting off the hot path. Let bytes stream with as little added latency as you can manage. The figure above is a generalized, synthetic illustration rather than any real system, but it's how I approach anything that sits on a critical path.

## Systems

Independent builds on synthetic workloads. No company code, customer data, or production config.

| System | What it is | Stack | Status |
|---|---|---|---|
| **Streaming AI Systems Lab** | Reference implementations and failure simulations for streaming gateways: lifecycles, cancellation, usage reservation and reconciliation, retry boundaries, health-aware routing | `Go` `TS` `Postgres` `Redis` | building in public |
| **Reliable Order Engine** | Broker-agnostic execution simulator: duplicate delivery, partial fills, timeouts, dead-letter recovery, post-outage reconciliation, explicit state machines | `Go` `Rust` `Postgres` `Redis Streams` | planned flagship |
| **[Zapstream](https://github.com/shrivats2/zapstream)** | Live-streaming app rebuilt as a production case study: token and room access, reconnection, webhook lifecycle, measured recovery | `TS` `WebRTC` `Node` | rebuild in progress |
| **Shipcheck** | Production-readiness CLI: health and readiness checks, graceful shutdown, migrations, secret hygiene, logging and tracing, CI, runbooks | `Go` `CLI` `Actions` | planned |

## Stack

| | |
|---|---|
| **Languages** | `Go` &nbsp; `TypeScript` &nbsp; `Rust` &nbsp; `Python` &nbsp; `SQL` |
| **Systems** | `PostgreSQL` &nbsp; `Redis` &nbsp; `Redis Streams` &nbsp; `WebRTC` &nbsp; `event-driven` &nbsp; `idempotency & reconciliation` |
| **Platform** | `AWS` &nbsp; `Docker` &nbsp; `CI/CD` &nbsp; `OpenTelemetry` |

<img src="assets/divider.svg" alt="" width="100%" />

<sub>Reach me at [shrivatskrishna25@gmail.com](mailto:shrivatskrishna25@gmail.com). Nothing here names a company or exposes customer data or proprietary architecture. It's independently built patterns and the thinking behind them.</sub>
