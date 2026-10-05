# Specification Coverage Map

_Last updated: 2026-10-04_

This document tracks where the interview requirements have landed so the project maintains balanced coverage rather than over-investing in player-facing UX while under-specifying platform, security, and operations.

## Coverage levels

- **Deep** — substantial decisions and controls exist.
- **Strong** — robust direction exists; implementation detail may still deepen.
- **Moderate** — core intent exists but more precision is useful.
- **Deferred/Excluded** — explicitly out of initial scope.

| Domain | Coverage | Current scope |
|---|---|---|
| Product vision & positioning | Deep | 21+, U.S.-first, multi-game, premium gaming + modern fintech, single umbrella brand |
| Player experience / features | Deep | Home, discovery, Play Now, profile, notifications, history, challenges, rewards, event calendar |
| UI/UX interaction model | Deep | High-fidelity, responsive web + native-feeling mobile, controller support, immersion-first gameplay |
| Gameplay model | Deep | Skill/chance/hybrid; synchronous/asynchronous; real-time multiplayer |
| Matchmaking | Deep | Preferences, transparent relaxation, ranking/MMR, crossplay, latency, queue controls |
| Competitive integrity | Deep | Server authority, RNG/result integrity, rank rules, post-match review |
| Rooms / parties / lobbies | Deep | Ephemeral rooms, approved host rules, temporary parties, host migration |
| Tournaments / seasons | Deep | Platform/player-hosted, registration, check-in, seeding, adjudication, seasonal resets |
| Social | Deep | Tenant-specific friends, recent players, contextual presence, text chat only |
| Spectating / replays | Strong | Passive spectators, delays, player-perspective replay, authoritative operational replay |
| Identity / authentication | Deep | Global identity, tenant display identities, passwordless/pluggable auth, guest conversion |
| Multi-tenancy / white label | Deep | Logical isolation, independent branding, shared catalog + exclusives |
| Compliance / eligibility | Strong | 21+, policy engine, state rules, assurance tiers, promotion terms/versioning |
| Security architecture | Deep | Zero trust, service identity, KMS, privileged MFA, supply chain, environment isolation |
| Trust / fraud / abuse | Deep | Device/network risk, account sharing, fraud signals, case management |
| Anti-cheat / anti-collusion | Deep | Post-match detection, logs/replays, relationship analysis, prize holds |
| Reputation | Strong | Public summary, internal deep scoring, host/player reputation |
| Case management / support | Deep | Unified cases, evidence, notes, SLAs, no impersonation |
| Game economies | Deep | Separate game economies, sources/sinks, issuance budgets, circuit breakers |
| Loyalty / rewards | Strong | Cross-game umbrella loyalty, tenant programs, challenges/streaks/referrals |
| Inventory / entitlements | Deep | Consumables, time-limited, account-bound, tradable, tenant-specific |
| Marketplace / trading | Strong | Listings, fees, price history, provenance, wash-trade detection |
| Blockchain / digital assets | Strong / Optional | NFT/on-chain ownership, tokenized rewards, wallets, smart-contract hooks |
| Money movement boundary | Strong | External providers only; platform tracks status/entitlements/reconciliation |
| Provider integration layer | Deep | Provider-agnostic adapters across payments/KYC/fraud/moderation/messaging/AI |
| Notifications / communications | Deep | In-app, push, email, SMS; priority/channel preferences; no voice |
| AI features / governance | Strong | Bots, coaching, fraud, moderation, personalization, AI registry and kill switches |
| Analytics / telemetry | Strong | Shared taxonomy, OpenTelemetry correlation, canonical metrics, data-quality SLOs |
| Privacy / data governance | Strong | Retention, export/deletion, minimization, privacy request orchestration |
| Game SDK / plugin model | Deep | Lifecycle contract, capabilities, browser isolation, Unity/Unreal parity |
| Developer / certification | Strong | Private partner model, conformance tests, certification evidence |
| Live ops / experimentation | Deep | Feature flags, remote config, A/B tests, policy/economy guardrails |
| Admin / operations console | Deep | Player/account, compliance, fraud, moderation, tournaments, economy |
| Real-time command center | Deep | Live health + controlled operational actions |
| Reliability / resilience | Deep | Multi-region, failover, backups, chaos, backpressure, degraded modes |
| Scale / performance | Strong | Tens of thousands normal, hundreds of thousands peak, fast real-time |
| Tenant governance | Strong | Tenant RBAC, scoped roles, promotions/config sandbox |
| Prototype | Deep | Production-seed coded web/mobile prototype with deterministic seeded scenarios |
| Business / commercial model | Strong | Hybrid pricing, MAU + costly usage, white label, partner economics |
| Brand strategy | Strong | Independent abstract brand; premium gaming + fintech positioning |
| Design system | Strong | Token layers, component governance, tenant theming, protected critical states |
| Testing / certification quality | Deep | Unit through resilience/security, state-model tests, property-based economy tests |
| FinOps / cost governance | Strong | Cost allocation, unit economics, tenant profitability, cost anomaly alerts |

## Cross-cutting principles

1. **Best practice is the default.**
2. **Adversarial thinking is mandatory.**
3. **Adversarial thinking runs in both directions**: prevent harm without sanitizing fun, retention or commercial performance.
4. **Simplicity at the surface, complexity underneath.**
5. **Coordination before play; authority during play; transparency after play.**
6. **Player identity may be flexible; accountability must remain durable.**
7. **Economic value gets stronger controls than ordinary gameplay.**
8. **Tenants are isolated experiences on a shared platform.**
9. **Anything configurable has bounds; anything powerful has scope; anything consequential is reproducible.**
10. **Authoritative truth is narrow and hard to bypass; derived views may be distributed/cached/personalized.**
11. **Extensibility is safe only when extension points are narrower than the platform they extend.**
12. **A requirement is complete only when ownership, enforcement, failure mode and verification are known.**

## Remaining depth opportunities

### 1. Concrete game SDK artifacts
- exact interface definitions;
- message schemas;
- browser bridge API;
- Unity/Unreal adapter contracts;
- certification fixtures.

### 2. Canonical data model
- entity/relationship model;
- authoritative store choices;
- keys/indexes;
- event schemas;
- state-transition tables.

### 3. Policy/compliance implementation research
- state-by-state U.S. rules;
- exact disclosure/geolocation/verification requirements;
- retention/legal evidence requirements.

### 4. High-fidelity visual system
- concrete token values;
- typography scale;
- component inventory;
- gameplay overlays;
- responsive layouts;
- motion/haptic system;
- tenant theme examples.

### 5. Quantitative commercial model
- actual price levels;
- usage thresholds;
- cost-to-serve benchmarks;
- partner/studio economics;
- marketplace fee ranges.

### 6. Prototype implementation
- production-seed repo structure;
- mock adapters;
- seeded scenarios;
- web/mobile flows;
- command-center simulator.

## Explicitly deferred/excluded

- accessibility as a primary requirement;
- localization initially;
- voice chat;
- linked household accounts;
- social login;
- direct challenges initially;
- persistent rooms;
- automatic human backfill;
- general-purpose social feed;
- on-prem/private cloud;
- public developer portal;
- generic asset lending/rental;
- detailed cap-table/fundraising model.
