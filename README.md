<!-- github.com/shrivats2 · profile README. Visuals are hand-authored SVG in /assets. -->

<img src="assets/hero.svg" alt="Shrivats Krishna Shrivastav — founder-engineer, systems on the critical path" width="100%" />

I take systems from an unclear problem to running in production: discovery, architecture, backend, infrastructure, and the operational work most people skip. I work where failure is immediate and expensive &mdash; AI inference infrastructure (currently, in stealth) and real-money financial execution.

<sub>`AI infrastructure` · `fintech execution` · `real-time systems` · `reliability`  &nbsp;|&nbsp;  [email](mailto:shrivatskrishna25@gmail.com) · [github](https://github.com/shrivats2)</sub>

<img src="assets/divider.svg" alt="" width="100%" />

### 01 · Now

**Stealth AI infrastructure** — founder-engineer. Controls that sit in the critical path of streamed model requests, and the product around them:

- Multi-tenant auth, access control, budgets, usage limits
- Provider-independent request and streaming abstractions
- Usage metering and reconciliation for interrupted / incomplete requests
- Health- and failure-aware routing; controls against latency and unexpected cost
- Billing-linked access, append-only audit history
- Discovery → build → deploy → onboard → operate → recover

**Financial execution systems.** Trader-facing order workflows across web, desktop, mobile, backend, and broker integrations:

- Order-lifecycle tracking; real-time position, order, and risk state
- Broker routing; secure brokerage onboarding and credential exchange
- Idempotency and duplicate-event handling; dead-letter recovery and reconciliation
- Monitoring, deployments, incident response, production recovery, on AWS

<sub>Company code, customer data, and proprietary architecture stay private. What's public here is independently built patterns and the reasoning behind them.</sub>

<img src="assets/divider.svg" alt="" width="100%" />

### 02 · Selected outcomes

- Took a production AI infrastructure product from early partner discovery to live usage **within one quarter**
- Kept added request-path latency in the **low single-digit milliseconds** while enforcing controls on streamed requests
- Ran request lifecycle, usage accounting, access control, and provider-reliability workflows across **tens of thousands** of production requests
- Stabilised a live execution lifecycle moving **millions of dollars** in real-money flow
- Cut missed-order incidents from a recurring production problem to **near zero** with lifecycle tracking, recovery, and real-time alerts

<img src="assets/divider.svg" alt="" width="100%" />

### 03 · The idea I keep returning to

<img src="assets/architecture.svg" alt="Control plane / data plane separation for a streaming gateway" width="100%" />

Keep policy, identity, and accounting off the hot path. Let bytes stream with as little added latency as possible. Generalised, synthetic illustration &mdash; not any specific production system &mdash; but it's how I reason about anything sitting on a critical path.

<img src="assets/divider.svg" alt="" width="100%" />

### 04 · Selected systems

Independent, educational builds on synthetic workloads. No company code, customer data, or production config.

| System | What it is | Stack | Status |
|---|---|---|---|
| **Streaming AI Systems Lab** | Reference implementations + failure simulations for streaming gateways: lifecycles, cancellation, usage reservation/reconciliation, retry boundaries, health-aware routing | `Go` `TS` `Postgres` `Redis` | building in public |
| **Reliable Order Engine** | Broker-agnostic execution simulator: duplicate delivery, partial fills, timeouts, dead-letter recovery, post-outage reconciliation, explicit state machines | `Go` `Rust` `Postgres` `Redis Streams` | planned flagship |
| **[Zapstream](https://github.com/shrivats2/zapstream)** | Live-streaming app rebuilt as a production case study: token/room access, reconnection, webhook lifecycle, measured recovery | `TS` `WebRTC` `Node` | rebuild in progress |
| **Shipcheck** | Production-readiness CLI: health/readiness, graceful shutdown, migrations, secret hygiene, logging/tracing, CI, runbooks | `Go` `CLI` `Actions` | planned |

<img src="assets/divider.svg" alt="" width="100%" />

### 05 · Stack

<sub>

`Go` · `TypeScript` · `Rust` · `Python` · `SQL` &nbsp; // &nbsp; `PostgreSQL` · `Redis` · `Redis Streams` · `WebRTC` · `event-driven` · `idempotency & reconciliation` &nbsp; // &nbsp; `AWS` · `Docker` · `CI/CD` · `OpenTelemetry`

</sub>

<img src="assets/divider.svg" alt="" width="100%" />

<sub>Reach me at [shrivatskrishna25@gmail.com](mailto:shrivatskrishna25@gmail.com). No company names, customer data, or proprietary architecture is published here &mdash; only independently built patterns and the thinking behind them.</sub>
