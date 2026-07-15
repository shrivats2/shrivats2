<!-- ────────────────────────────────────────────────────────────────── -->
<!--  Profile README · github.com/shrivats2                              -->
<!--  Assets are hand-authored SVG in /assets — edit those, not this.    -->
<!-- ────────────────────────────────────────────────────────────────── -->

<div align="center">

<img src="assets/hero.svg" alt="Shrivats Krishna Shrivastav — founder-engineer building systems that sit on critical paths" width="100%" />

</div>

<p align="center">
  I build products from an ambiguous problem to a system running in production &mdash; discovery,
  architecture, frontend, backend, infrastructure, integrations, observability, and recovery.
  <br/>
  Currently building production <strong>AI inference infrastructure</strong> in stealth, and operating real-money <strong>financial execution</strong> systems.
</p>

<p align="center">
  <a href="#-what-ive-worked-on">What I've worked on</a> &nbsp;·&nbsp;
  <a href="#-selected-outcomes">Selected outcomes</a> &nbsp;·&nbsp;
  <a href="#-selected-systems">Selected systems</a> &nbsp;·&nbsp;
  <a href="#-how-i-build">How I build</a> &nbsp;·&nbsp;
  <a href="#-engineering-notes">Notes</a> &nbsp;·&nbsp;
  <a href="mailto:shrivatskrishna25@gmail.com">Email</a>
</p>

<img src="assets/divider.svg" alt="" width="100%" />

## ▚ What I've worked on

I have built and operated systems in two unforgiving environments: **production AI infrastructure**
and **real-money financial execution**. Both share the same property &mdash; when they break, someone
notices immediately, and the failure is expensive. That is the kind of problem I do my best work on.

### ◇ Stealth AI infrastructure &nbsp;·&nbsp; *founder-engineer*

I work across the entire product and engineering loop &mdash; from understanding design-partner problems
and defining scope, to building the product, deploying it, onboarding users, and operating it in
production. The work has spanned:

- Low-overhead controls sitting **in the critical path of streamed AI requests**.
- Multi-tenant authentication, access control, budgets, and usage limits.
- Provider-independent request and streaming abstractions.
- Usage metering and reconciliation around **incomplete or interrupted** requests.
- Billing-linked product access and an operational audit history.
- Reliability controls around provider failures, latency, and unexpected cost.
- Customer-facing workflows and the internal operational tooling behind them.
- Deployment, observability, incident response, and recovery.

> The company and its production implementation stay private while we operate in stealth. My public
> work focuses on independently implemented patterns, synthetic demonstrations, and engineering
> lessons from this problem space &mdash; never company code, customer data, or proprietary architecture.

### ◆ Financial execution systems

I have owned trader-facing products and live order workflows across desktop, web, mobile, backend
services, broker integrations, infrastructure, and production support:

- Reliable order-lifecycle tracking and real-time position, order, and risk state.
- Broker routing and integration workflows; secure brokerage onboarding and credential exchange.
- Idempotency and duplicate-event handling; dead-letter recovery and reconciliation.
- Execution-quality and portfolio analytics.
- Monitoring, deployments, incident response, and production recovery.

<img src="assets/divider.svg" alt="" width="100%" />

## ▚ Selected outcomes

<table>
<tr>
<td width="50%" valign="top">

**AI infrastructure**

- Took a production AI infrastructure product from early partner discovery to live usage **within one quarter**.
- Built controls for streamed AI requests while keeping added request-path latency in the **low single-digit milliseconds**.
- Operated request lifecycle, usage accounting, access control, and provider-reliability workflows across **tens of thousands** of production requests.

</td>
<td width="50%" valign="top">

**Financial execution**

- Stabilized a live execution lifecycle handling **millions of dollars** in real-money flow.
- Reduced missed-order incidents from a recurring production problem to **near zero** via lifecycle tracking, recovery workflows, and real-time alerts.
- Built and operated products across web, desktop, mobile, backend services, and **AWS** infrastructure.

</td>
</tr>
</table>

<img src="assets/divider.svg" alt="" width="100%" />

## ▚ How I think about the problem

<div align="center">
<img src="assets/architecture.svg" alt="Separating the control plane from the request data plane in a streaming AI gateway" width="100%" />
</div>

The pattern above is the one idea I keep returning to: **keep policy, identity, and accounting off
the hot path, and let bytes stream with as little added latency as possible.** It's a generalized,
synthetic illustration &mdash; not any specific production system &mdash; but it captures how I reason about
systems that sit on a critical path.

<img src="assets/divider.svg" alt="" width="100%" />

## ▚ Selected systems

> Independent, educational implementations built with synthetic workloads. None contain private
> company code, customer data, or production configuration.

### ⟠ Streaming AI Systems Lab &nbsp; <sub>`building in public`</sub>

Reference implementations and failure simulations for the hard parts of production AI request
infrastructure &mdash; streaming lifecycles, client cancellation and incomplete responses,
provider-independent event formats, usage reservation and reconciliation, safe retry boundaries,
budget and rate-limit enforcement, and health-aware routing.

<sub>`Go` · `TypeScript` · `PostgreSQL` · `Redis` · `OpenTelemetry`</sub>

### ⟠ Reliable Order Engine &nbsp; <sub>`planned flagship`</sub>

A broker-agnostic execution simulator built around the ugly realities of live order flow: duplicate
delivery, partial fills, timeouts, dead-letter recovery, and post-outage reconciliation &mdash; with
explicit state machines, idempotent command handling, and auditable operator actions.

<sub>`Go` · `Rust` · `TypeScript` · `PostgreSQL` · `Redis Streams`</sub>

### ⟠ [Zapstream](https://github.com/shrivats2/zapstream) &nbsp; <sub>`rebuild in progress`</sub>

A live-streaming application being rebuilt as a production-oriented case study: secure token and
room-access workflows, participant state synchronization, reconnection and degraded-state handling,
webhook lifecycle management, and measured recovery behaviour.

<sub>`TypeScript` · `WebRTC` · `Node.js`</sub>

### ⟠ Shipcheck &nbsp; <sub>`planned tool`</sub>

A production-readiness CLI that finds the operational gaps before a service is launched &mdash; health
and readiness endpoints, graceful shutdown, migrations, secret hygiene, structured logging and
tracing, CI coverage, and runbooks.

<sub>`Go` · `CLI` · `Static analysis` · `GitHub Actions`</sub>

<img src="assets/divider.svg" alt="" width="100%" />

## ▚ How I build

<table>
<tr>
<td valign="top" width="33%">

**Start from the failure**

I design backwards from what happens when the request is interrupted, the provider is down, or the
same event arrives twice &mdash; then make the happy path fall out of that.

</td>
<td valign="top" width="33%">

**Own the whole loop**

Discovery, architecture, build, deploy, onboard, operate. I don't hand a system off at the boundary
I find inconvenient; the boundary is usually where the real problem lives.

</td>
<td valign="top" width="33%">

**Latency is a feature**

Controls belong in the critical path only if they're cheap. Everything else moves off the hot path.
Measured, not assumed.

</td>
</tr>
</table>

<img src="assets/divider.svg" alt="" width="100%" />

## ▚ Engineering notes

Writing I'm working on &mdash; general patterns from these problem spaces, with no company specifics:

- Metering streamed LLM requests when the client disconnects
- Why AI usage accounting needs reservation *and* reconciliation
- Designing provider-independent streaming interfaces
- Why retries become dangerous after streaming begins
- Separating the AI control plane from the request data plane

<sub>Each note discusses general engineering patterns using simplified, synthetic examples. None describe the architecture or implementation of any specific private production system.</sub>

<img src="assets/divider.svg" alt="" width="100%" />

## ▚ Stack

<div align="center">
<sub>

**Languages** &nbsp; `Go` · `TypeScript` · `Rust` · `Python` · `SQL`

**Systems** &nbsp; `PostgreSQL` · `Redis` · `Redis Streams` · `WebRTC / streaming` · `event-driven` · `idempotency & reconciliation`

**Platform** &nbsp; `AWS` · `Docker` · `CI/CD` · `OpenTelemetry` · `observability & incident response`

</sub>
</div>

<img src="assets/divider.svg" alt="" width="100%" />

<div align="center">

**Building AI infrastructure and financial execution systems that have to be right the first time.**

<a href="mailto:shrivatskrishna25@gmail.com">Email</a> &nbsp;·&nbsp;
<a href="https://github.com/shrivats2">GitHub</a>

<sub>No company names, customer data, or proprietary architecture is published here &mdash; only independently built patterns and the thinking behind them.</sub>

</div>
