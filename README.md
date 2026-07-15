<!-- github.com/shrivats2 · profile README. Visuals are hand-authored SVG in /assets. -->

<img src="assets/hero.svg" alt="Shrivats Shrivastav — AI infrastructure, spend governance in the request path" width="100%" />

I build systems end to end and run them in production. Most of my work is spend governance for AI: deciding what a request should do before it reaches the provider, keeping variable model cost from breaking fixed-price economics, and the real-time infrastructure it all runs on.

I like the parts most people skip: what happens when a request is interrupted, a provider fails, or the same event arrives twice.

[shrivatskrishna25@gmail.com](mailto:shrivatskrishna25@gmail.com) &nbsp;·&nbsp; [github.com/shrivats2](https://github.com/shrivats2)

<img src="assets/divider.svg" alt="" width="100%" />

## Now

**AI spend governance.** Real-time controls that decide what an AI request should do before it reaches the provider:

- Pre-execution policy in the request path: allow, cap, downgrade, reroute, cache, or fall back
- Per-tenant budgets, rate limits, and usage attribution
- Spend and margin controls that keep variable model cost from breaking fixed-price economics
- Provider-independent routing across model providers, aware of health and cost
- Usage metering and reconciliation for streamed, interrupted, or incomplete requests
- Multi-tenant access control, policy, and an append-only audit trail

**Real-time and financial systems.** Order flow and live state across backend and broker integrations:

- Order-lifecycle tracking and real-time state
- Idempotency, duplicate-event handling, dead-letter recovery, reconciliation
- Broker integrations and secure onboarding
- Monitoring, deploys, and incident response on AWS

## How I think about it

<img src="assets/architecture.svg" alt="Control plane / data plane separation for a streaming gateway" width="100%" />

Keep policy, identity, and accounting off the hot path. Let bytes stream with as little added latency as you can manage. The figure above is a generalized, synthetic illustration rather than any real system, but it's how I approach anything that sits on a critical path.

## Activity

<img src="https://github-readme-activity-graph.vercel.app/graph?username=shrivats2&bg_color=E7E0CF&color=17130B&line=C24326&point=17130B&title_color=17130B&hide_border=true&custom_title=Contribution%20activity" alt="Contribution activity graph" width="100%" />

## Stack

| | |
|---|---|
| **Languages** | `Go` &nbsp; `TypeScript` &nbsp; `Rust` &nbsp; `Python` &nbsp; `SQL` |
| **Systems** | `PostgreSQL` &nbsp; `Redis` &nbsp; `Redis Streams` &nbsp; `WebRTC` &nbsp; `event-driven` &nbsp; `idempotency & reconciliation` |
| **Platform** | `AWS` &nbsp; `Docker` &nbsp; `CI/CD` &nbsp; `OpenTelemetry` |

<img src="assets/divider.svg" alt="" width="100%" />

<sub>[shrivatskrishna25@gmail.com](mailto:shrivatskrishna25@gmail.com) &nbsp;·&nbsp; [github.com/shrivats2](https://github.com/shrivats2)</sub>
