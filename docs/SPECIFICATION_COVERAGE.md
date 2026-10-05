# Specification Coverage Map

> Checkpoint through Q569 plus the post-Q569 engagement-design correction.

This document groups the discovery decisions by specification domain so coverage gaps are visible before analysis/design begins.

| Domain | Coverage | Current specification depth |
|---|---|---|
| Product vision & positioning | Deep | 21+ U.S.-first, multi-game, premium gaming + fintech, one umbrella brand, social/prize/sweepstakes focus |
| Player experience & core features | Deep | Home, Play Now, discovery, search, favorites, recent play, events, profiles, notifications, post-match, loyalty |
| UI/UX & interaction design | Deep | High-fidelity redesign, responsive web + native-feeling mobile, immersion-first play, standardized post-match, design tokens |
| Gameplay model | Deep | Skill/chance/hybrid, sync/async, real-time, single active session, practice, pause/reconnect/AFK rules |
| Matchmaking | Deep | Soft preferences, transparent relaxation, crossplay, ranked/MMR, placements, latency, anti-smurf |
| Competitive integrity | Deep | Server-authoritative outcomes/RNG/timing, replay logs, hidden pre-commit opponent identity, post-match enforcement |
| Rooms / parties / lobbies | Deep | Ephemeral rooms, approved rulesets, visibility, invites/codes, host migration, temporary parties |
| Tournaments & seasons | Deep | Platform/player-hosted, registration/check-in, seeding, bracket lock, disputes, prize review, seasonal resets |
| Social features | Deep | Tenant-specific friends, pseudonyms, DMs/room/party/team chat, presence, recent players, block/mute/report |
| Spectating / replay / broadcast | Strong | Passive spectators, delayed competitive feed, player/full replay separation, highlights |
| Identity & authentication | Deep | Global identity + tenant profile, passwordless/pluggable auth, guest flow, device sessions, re-verification |
| Multi-tenancy & white label | Deep | Logical isolation, tenant branding/config/catalog/rules/admin/social/economics, explicit tenant transition |
| Compliance / eligibility / policy | Deep | 21+, U.S., jurisdiction matrix, versioned policy engine, sweepstakes/AMOE model, precedence, fail-closed prize eligibility |
| Security architecture | Deep | Zero trust, service identity, KMS/secrets, encryption, privileged MFA, supply chain, threat modeling |
| Trust / fraud / abuse | Deep | Device/network risk, alt accounts, smurfing, reputation, sanctions/appeals, explainable risk decisions |
| Anti-cheat / anti-collusion | Deep | Post-match model, relationship graphs, suspicious outcomes/transfers, prize holds, authoritative replays |
| Reputation | Strong | Public simple signals, internal deep scoring, host/player reliability, abandonment and moderation history |
| Case management / support | Deep | Unified cases, evidence, SLA/escalation, human override, support observation, no impersonation |
| Game economies | Deep | Separate economies, currencies, source/sink, budgets, conversion controls, reward tables, circuit breakers |
| Loyalty & rewards | Strong | Platform-wide layer, tenant-specific default, streaks/referrals/challenges/VIP, corrected engagement design |
| Inventory & entitlements | Deep | Cosmetics, passes, tickets, consumables, time-limited, bound, tradable, provenance |
| Marketplace / trading | Strong | Listings, explicit fees, price history, anti-wash trading, trade confirmation, review holds |
| Blockchain / digital assets | Strong/optional | Native ownership primary, optional NFT/on-chain/token/smart contract support |
| Money movement boundary | Strong | External providers only; platform tracks status/entitlements/reconciliation, no custody |
| Provider integration layer | Deep | Provider agnostic KYC, geolocation, fraud, messaging, analytics, moderation, AI, payout |
| Notifications & communications | Deep | In-app, push, email, SMS; channel preferences, gameplay suppression, marketing separation |
| AI features & governance | Deep | Bots, coaching, moderation, fraud, personalization, AI registry/evaluation/drift/gateway/kill switches |
| Analytics & telemetry | Deep | Common taxonomy, metric governance, OpenTelemetry correlation, data quality and experimentation controls |
| Privacy & data governance | Deep | Retention classes, delete/export, minimization, privacy orchestration, protected verified identity |
| Game SDK / plugin model | Deep | Standard lifecycle, capability manifest, semver, browser isolation, Unity/Unreal parity |
| Developer certification | Deep | Private managed onboarding, sandbox, conformance, performance/security/integrity evidence, recertification |
| Live ops / experimentation | Deep | Flags, remote config, A/B, cohorts, event scheduling, approval/rollback, experiment guardrails |
| Admin / operations console | Deep | Account/compliance/fraud/moderation/tournament/economy/support/config/analytics |
| Real-time command center | Deep | Live health + guarded controls, kill switches, blast-radius previews |
| Reliability / resilience | Deep | Multi-region, backups/restore, chaos, degraded mode, backpressure/load shed, SLO/error budget |
| Scale & performance | Strong | Tens of thousands normal, hundreds of thousands peak, real-time latency-sensitive design |
| Tenant governance | Strong | Tenant-scoped RBAC, promotions templates, config sandbox, derived trust signals only |
| Prototype / simulation | Deep | Production-seed code, web/mobile, realistic seeded data, deterministic scenarios |
| Testing / quality engineering | Deep | Layered tests, state/property testing, load/soak/network, replay determinism, certification evidence |
| FinOps / cost governance | Strong | Tenant/game/service allocation, unit economics, provider/observability/storage cost controls |
| Search & recommendations | Strong | Tenant-scoped search, privacy constraints, trust-weighted ranking, exploration and sponsored-label separation |
| Business / commercial model | Strong | Hybrid subscription+usage, MAU core metric, tenant/studio economics, explicit marketplace fees |
| Brand strategy | Strong | Independent abstract/ownable brand, premium gaming + fintech, white-label architecture |
| High-fidelity design system | Strong | Hierarchy, typography/numeric treatment, protected semantic status, HUD/overlay, token governance |
| Requirements traceability | Strong | Domain/risk/owner/design/API/test/certification links, Specified→Designed→Implemented→Verified |

## Cross-cutting principles

1. **Best practice is the default.** Deviation requires a concrete reason.
2. **Adversarial review is two-sided.** Prevent abuse and deception without unnecessarily reducing fun or conversion.
3. **Simple surface, complex underside.** Players should not need to understand orchestration, policy engines or reconciliation.
4. **Coordination before play; authority during play; transparency after play.**
5. **Player identity can be flexible; authority and accountability remain durable.**
6. **Anything configurable has bounds; anything powerful has scope; anything consequential is reproducible.**
7. **Authoritative truth is narrow and hard to bypass; derived views may be cached/personalized/eventually consistent.**
8. **Design for maximum legitimate engagement. Truthfulness—not emotional intensity—is the boundary.**

## Remaining thin areas

Coverage is now broad and deep. Remaining work is less about missing platform categories and more about turning the specification into concrete design/implementation artifacts after **go**:

- Exact technical-stack recommendation derived from Figma/competitor/workload research.
- Exact data schemas and API definitions, beyond the contract principles already established.
- Detailed state diagrams for each consequential workflow.
- Quantitative state-by-state U.S. sweepstakes/prize legal matrix based on dedicated legal research.
- Final SLO/RTO/RPO values calibrated against selected cloud/runtime architecture and cost targets.
- High-fidelity screen-by-screen Figma concepts and responsive interaction specifications.
- Concrete design-token values, component library and motion system.
- Coded responsive web/mobile prototype implementation.
- Quantified tenant pricing and unit-economics scenarios.
- Competitive teardown and best-in-class comparison.

These items should be executed after the user explicitly says **go**; they are not reasons to start design prematurely.
