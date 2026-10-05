# Discovery Interview — Normalized Record

> Checkpoint through Question 569, plus the engagement-design correction that followed.
>
> Status: discovery interview is still in progress. **Do not begin the Cryptan/competitor teardown, architecture selection, high-fidelity redesign, or coded prototype until the user explicitly says go.**

## Primary reference

- Cryptan Figma: https://www.figma.com/design/X273k80M4Lz72W4K692dtN/Cryptan-Design?node-id=6002-1168&t=xTNZdXl8gn6zG2z0-0

## Interview operating rules

1. **Research note with every design question.** Each question should be accompanied by a concise industry/best-practice note.
2. **Best practice is the default.** Do not push ordinary UX/product decisions back to the user when a clear industry norm exists. Make the call and continue.
3. **Alternatives are strategic only when there is a concrete reason not to use best practice.** Examples: compliance, economics, game integrity, tenant isolation, performance, security, or deliberate differentiation.
4. **Adversarial thinking is mandatory.** Test every design against abuse, exploitation, cheating/collusion, incentive gaming, fraud, privacy/security failures, operator or tenant misuse, edge cases, and failure modes.
5. **Adversarial thinking runs in both directions.** Also ask whether safeguards are unnecessarily damaging fun, retention, excitement, competition, conversion, or commercial performance.
6. **Decision format:** research note → best-practice call → adversarial check → concrete decision.
7. **Do not start analysis/design until go.** This interview is requirements discovery.

## Product thesis

Design a new, independent, 21+ U.S.-first, multi-game, cross-platform gaming platform. Cryptan is a reference for improvement, not a visual or product template. The target experience combines premium gaming energy with modern fintech-grade clarity at consequential decision points.

The platform should support social play, prize/sweepstakes play, configurable rooms, tournaments, ranked competition, spectator/replay systems, separate per-game economies, a global underlying identity with tenant-specific pseudonymous profiles, white-label multi-tenancy, provider-agnostic integrations, and a formal game SDK for internal and approved external studios.

## Foundational decisions

### Audience and market

- Minimum audience: **21+**.
- Initial geography: **United States**.
- Core proposed modes: **sweepstakes, prize-based play, and non-wagering social play**.
- Real-money wagering is not a default platform requirement; analyze it only if it already appears in the reference design.
- Skill-based, chance/RNG-based, and hybrid skill + chance games are all supported.
- Both synchronous real-time and asynchronous play are supported.
- Normal scale: tens of thousands of users; peak events may reach **hundreds of thousands**.
- Fast real-time multiplayer is a first-class requirement.

### Brand and presentation

- One umbrella platform brand, completely independent of Cryptan.
- Brand direction: abstract, ownable, broad, premium. Avoid explicit casino, gambling, crypto, or fintech terminology in the name itself.
- Visual direction: **premium gaming + modern fintech**, with serious/credible foundations and enough energy/social intensity to feel alive.
- Tenants may present a fully independent white-label experience; umbrella-brand attribution is optional/configurable unless legally or operationally required.

### Cross-platform surfaces

- Web-first responsive coded prototype.
- Separate mobile coded prototype with native-feeling interaction/lifecycle.
- Desktop/web and mobile are independently optimized rather than one layout stretched everywhere.
- Touch, mouse, keyboard, and gamepad are supported.
- Browser-native games are the primary integration target; Unity and Unreal adapters are also supported.

## Player experience and UX decisions

### Home and discovery

- Home uses an **intent-led hierarchy**, not an equal-weight dashboard.
- Primary emphasis: Continue Playing / recommended next activity / Play Now.
- Secondary emphasis: live events/tournaments.
- Tertiary emphasis: friends/social activity, rankings, rewards, and recent activity.
- One dominant action per major screen; avoid dashboard clutter.
- Game discovery uses both game title and intent/mode (Play Now, Competitive, With Friends, Tournaments, Prize Eligible, Quick Games, etc.).
- Persistent **Play Now** action uses saved global preferences as soft constraints.
- Players can edit preferences in settings and inline before matchmaking.
- Matchmaking preference relaxation is transparent; players are told what is changing and retain control.
- Home structure remains stable while content modules personalize.
- Search is tenant-scoped and permission-aware across games, tournaments, rooms, players, and help content.
- Recommendations combine editorial quality/popularity and personalization; identifiable cross-tenant behavior is not exposed. Aggregated/anonymized cross-tenant signals may improve ranking.
- No general-purpose social feed. Use contextual social presence instead.

### Navigation and immersion

- Games are **launchable experiences inside a platform shell**, not separate mini-products with their own full hubs.
- Platform chrome recedes during active gameplay; only essential protected controls remain.
- Post-match experience is standardized at the platform level.
- One active gameplay session per player at a time.
- Spectating is a separate activity, not something done while matchmaking or actively playing.

### Onboarding and permissions

- Progressive onboarding; guests may browse and play eligible non-prize/social modes.
- Account creation occurs when persistent identity/value is needed.
- Guest progress can be claimed/merged into a created account.
- Passwordless authentication is the prototype default; authentication remains pluggable.
- Platform-native identity; no Apple/Google/Microsoft social-login dependency.
- Just-in-time permission prompts rather than front-loading permission requests.

## Gameplay, matchmaking, rooms and tournaments

### Matchmaking

- Crossplay on by default.
- Input-based pools only when input materially affects fairness.
- Ranked competitive matchmaking supports MMR/skill ratings, placements, tiers/divisions, soft seasonal resets, decay where appropriate, and anti-smurf controls.
- Match-found confirmation hides opponent identity until commitment in ranked/prize contexts.
- Queue cancellation is free before commitment; abandonment rules apply after commitment.
- Matchmaking UI shows elapsed time, current conditions, relaxation status and cancellation. Avoid fake countdown precision.
- Competitive modes enforce game-defined latency/jitter thresholds before launch.

### Rooms and parties

- Rooms are **ephemeral** by default.
- Hosts may choose only platform/game-approved rules and bounded parameters.
- Material rule changes after players join require visible reconfirmation/Ready.
- Parties are lightweight, opt-in coordination objects; they do not force synchronized navigation or prevent solo play.
- Party leader coordinates shared activity; members may leave freely; leadership migrates automatically.
- No automatic human backfill into existing matches. AI substitution exists only where a game explicitly defines it.
- Private, friends-visible, and public room visibility are supported; private/invite-only is the conservative default for player-created rooms.
- Join codes/links are temporary, scoped, revocable and rate-limited.
- Room hosts have pre-match coordination powers but no gameplay authority once a server-authoritative match starts.

### Match lifecycle

- Competitive/ranked/prize matches normally lock once play begins, except reconnect of the same participant.
- Casual/social modes may allow join-in-progress where the game explicitly supports safe entry.
- Reconnect is authoritative: reconnecting players regain their existing seat/session only.
- AFK handling escalates from warning/grace to game-defined timeout/forfeit/turn skip.
- Voluntary departure from consequential competitive play uses explicit game-defined forfeit/abandonment outcomes.

### Tournaments and seasons

- Both platform-run and player-hosted tournaments.
- Lifecycle: registration → eligibility check → reminders → check-in → bracket/seeding lock → play → adjudication → outcome/prize finalization.
- Seeding method is declared before bracket lock and is deterministic from the selected method.
- Organizers configure events but cannot rewrite authoritative match outcomes, locked seeding, risk review, or finalized prize rules.
- No-show, forfeit, restart/resume and technical-failure behavior is predefined.
- Seasonal ranked systems use soft resets while preserving long-term history.
- Seasonal rewards are automatically granted by the authoritative system; UI may still provide a compelling reveal/claim ritual.

## Social identity and community

- Public identity is **pseudonymous**.
- One global platform identity exists underneath, but display identity is tenant-specific.
- Friends/social graph is tenant-specific.
- Public achievements and tournament history are tenant-specific; global/private trust remains platform-level.
- Friendship is reciprocal, not a follower model.
- Text communication only: friend DMs, room chat, party chat, team chat. No voice stack.
- No public global chat and no spectator chat.
- Mute, block and report are separate controls.
- Recent-player history supports friendship, reporting, blocking and permitted profile review.
- Presence is friends-only by default and can be hidden.
- Public competitive profile shows rank/tier, selected achievements, tournament history and canonical game stats; deep analytics remain private.
- Curated avatars/frames/badges/titles initially; no arbitrary profile image uploads.

## Spectating, replay and integrity

- Spectating is completely passive. No spectator-to-player communication.
- Competitive/prize matches may use delayed spectator feeds and hidden sensitive state.
- Authoritative match event logs and replays support disputes, anti-cheat, tournament adjudication, spectator replay and highlight generation.
- Player-facing replay defaults to information legitimately visible from that player’s perspective.
- Full authoritative replay is operationally available and may be released only when safe.
- Replays/highlights for prize/competitive matches wait for applicable integrity review before external sharing.

## Identity, trust, fraud and moderation

### Identity model

- Global account + TenantPlayerProfile model.
- Different tenant display identities map privately to the same underlying global identity.
- Tenant transitions are explicit and operationally isolated; active gameplay blocks tenant switching.
- No household/linked-account model.
- Risk-based re-verification for prize redemption, recovery, suspicious activity, major profile changes, etc.

### Trust and risk

- Device trust/risk scoring, known-device recognition, emulator/root/jailbreak signals where appropriate.
- Network risk: VPN/proxy/Tor, datacenter IP reputation, impossible travel, account sharing patterns, coordinated multi-account behavior.
- Anti-smurf detection and accelerated rating correction.
- Related-account detection prevents alt accounts from bypassing sanctions, prize limits, promotions, eligibility or anti-collusion controls.
- Cross-tenant raw player history is internal to platform trust/compliance. Tenants receive only approved derived signals.
- Trust decisions are explainable and auditable to authorized operators.

### Anti-cheat and anti-collusion

- Server-authoritative match outcomes, timing, RNG, scoring and prize eligibility.
- Anti-cheat/collusion intervention is primarily **post-match** to avoid destabilizing live gameplay.
- Suspicious matches may enter configurable prize hold/review states.
- Signals include repeated pairing, relationship graphs, suspicious transfers, shared device/network clusters, abnormal outcomes, coordinated timing and tournament manipulation.
- Risk score may trigger review/step-up/holds, but serious sanctions follow a policy-governed decision path rather than raw model score alone.

### Case management and support

- Unified cases for fraud, moderation, compliance, disputes and appeals.
- Cases support assignments, evidence, notes, escalation, SLA tracking, disposition and audit history.
- Human override of automated decisions is allowed only via controlled, reason-coded, auditable workflows.
- Support operators may never impersonate players.
- Real-time support uses admin observation/state inspection and controlled actions only.

## Economies, rewards, entitlements and marketplace

### Economy model

- Each game has its own economy and progression.
- Platform-wide loyalty/rewards is separate from game economies.
- Support both redeemable prize/sweepstakes currencies and non-redeemable virtual currencies.
- Distinct names, icons, purposes, balances, histories and rules for each value type.
- No universal cross-currency conversion; any conversion path is explicit, governed and bounded.
- Source/sink registry, issuance budgets, anomaly detection, velocity limits and circuit breakers.
- Economy health measures supply, source/sink ratio, velocity, concentration, item supply, trade volume and anomalies.
- Randomized reward tables are versioned and auditable.

### Entitlements and inventory

- Supports cosmetics, badges, passes, tickets, promotional rewards and game-specific items.
- Item types may be time-limited, consumable, account-bound, tradable and tenant-specific.
- Item provenance is retained internally and useful portions may be surfaced to players.
- Expiring items clearly disclose expiration before acquisition and before loss.

### Marketplace

- P2P marketplace/trading supported.
- Listings show exact item, quantity/attributes, seller context where appropriate, price, fees, restrictions, transferability and expiration.
- Trade confirmation shows a final side-by-side summary; material changes reset confirmation.
- Anti-wash-trading controls use relationship/device/network/velocity/circular-trade signals.
- Marketplace fees are explicit and versioned; no hidden spread.
- No generic player-to-player lending/rental system initially.

### Blockchain

- Platform-native ownership is primary; blockchain/NFT ownership is an optional pluggable path.
- Optional support for on-chain ownership/transfer, tokenized rewards/economies, and smart-contract tournament/prize logic where appropriate.
- Support both embedded/provider-managed and external self-custody wallets through a provider-agnostic abstraction.

## Money movement and providers

- The platform does **not** custody or move money. External providers handle purchases and payouts.
- Platform consumes authenticated/idempotent transaction and fulfillment state and manages game entitlements, prize eligibility, audit and reconciliation.
- Provider integration is agnostic across payments/payout, KYC, age verification, geolocation, fraud/risk, messaging, analytics, moderation and AI.
- Provider callbacks require authentication/signatures, replay protection, schema validation, timestamp windows and idempotency.
- Provider outages degrade only the dependent capability where possible.

## Multi-tenancy and white label

- True multi-tenant system with mature shared infrastructure and strong logical isolation.
- Shared game catalog by default, with support for tenant-exclusive games/features.
- Global identity underneath; tenant-specific profile, social graph, branding, configuration, catalogs, rules, promotions, analytics and admin scope.
- Tenants can create promotions/prize programs through platform-approved templates and guardrails.
- Tenant UX can be fully independently branded, but core interaction/navigation/account/gameplay/trust patterns remain platform governed.
- Tenant admin roles are deny-by-default and may compose only tenant-scoped permissions.
- Tenant data may be protected by database-enforced row-level or equivalent policies in addition to service authorization.

## Architecture and platform contracts

### Game SDK and lifecycle

- Formal SDK/plugin model for internal teams and approved external studios.
- Private/managed developer onboarding, sandbox and certification; no public developer portal.
- Standard lifecycle: initialize → validate → allocate → ready → start → active → result submitted → finalize → teardown, with explicit failure/reconnect states.
- Capability manifest per game/plugin; deny by default.
- Semantic versioning, compatibility windows and recertification on material changes.
- Browser games run in separate origin/sandbox boundaries and communicate through a versioned message/RPC bridge.
- Browser, Unity and Unreal adapters provide semantic parity for core platform capabilities.

### Domains and data

First-class domains include: Identity, Tenant, Social, Game Catalog, Match/Session, Matchmaking, Tournament, Economy/Ledger, Entitlements, Marketplace, Trust, Case Management, Policy/Eligibility, Notifications, Live Ops and Analytics.

- Domains own authoritative writes.
- Opaque canonical IDs. IDs never grant access.
- Explicit state machines for consequential workflows.
- Append-only authoritative history for match results, economy/ledger, trades, prizes, policy decisions, moderation and privileged admin actions.
- Strong consistency for invariants; eventual consistency for projections/search/recommendations/analytics.
- Transactional outbox or equivalent for consequential state+event publication.
- Saga/workflow orchestration for consequential multi-domain transactions.

### APIs and events

- Contract-first version-controlled OpenAPI for service APIs.
- Backward-compatible additive evolution within supported majors.
- Purpose-specific response DTOs; sensitive fields deny-by-default.
- Cursor pagination, capped page sizes and query/workload budgets.
- Consequential mutations are idempotent.
- Commands/intents are separate from authoritative domain events. Clients do not assert facts such as PlayerWon.
- Common event envelope includes ID, type, source, time, schema version, tenant, actor/session context and correlation ID.
- Actor + role + tenant + resource + action + policy context is checked server-side for every relevant API operation.

## Security, resilience and operations

### Security architecture

- Zero-trust boundaries; no implicit trust from network location.
- Workload identity and authenticated encrypted service-to-service communication.
- Managed secret/KMS system; no production secrets in source or images.
- Short-lived credentials preferred; automated rotation.
- Envelope encryption and scoped key domains for sensitive data.
- Privileged operators require strong phishing-resistant MFA and step-up for dangerous actions.
- Edge gateway controls do not replace per-service authorization.
- Egress controls and SSRF defenses.
- Secure supply chain: pinned/scanned dependencies, SBOM, build provenance, vulnerability SLAs.
- Dev/staging/prod separate trust domains; raw production PII prohibited in routine test environments.
- Threat modeling is continuous; independent penetration/red-team exercises occur at meaningful milestones.

### Reliability and SRE

- Multi-region real-time capacity with viable regional alternatives.
- Graceful degradation; critical gameplay state preserved before noncritical recommendation/analytics features.
- Backup restoration is tested; critical backups are encrypted, isolated and immutable/versioned.
- Controlled chaos/failure testing.
- Backpressure, bounded queues, retry budgets and dead-letter handling.
- Event/tournament change-protection windows for nonessential high-risk releases.
- Canary/staged rollout and rollback design.
- Core target-state availability: approximately 99.95% for critical identity/session/matchmaking/game-session APIs, 99.9% for ordinary player platform services, with differentiated targets for back office.
- Journey SLOs include login, matchmaking, match-start success, reconnect, result finalization and entitlement correctness.
- Error budgets influence release policy.

### Admin and command center

- Full admin/operations console for accounts, compliance, fraud, moderation, tournaments, prizes, configuration, economies, analytics and support.
- Real-time command center monitors concurrency, latency, region/game health, provider health, tournaments, fraud spikes, economy anomalies and tenant health.
- Guarded operational actions support draining regions, disabling game/version/mode, pausing prize functionality, rolling back configuration and kill switches.
- Narrow job-function RBAC; no generic invisible superuser.
- Separation of duties and maker/checker flows for high-risk operations.
- Break-glass access is explicit, time-limited, strongly authenticated, logged and reviewed.
- Bulk operations require dry-run/preview, count/blast-radius confirmation and stronger approvals.

## Compliance, policy and privacy

- Versioned, auditable policy/rules engine.
- Precedence: law/regulatory configuration → platform compliance/safety → tenant policy → game/mode configuration. Lower layers cannot weaken higher prohibitions.
- Policy versions have effective dates and are recorded with consequential decisions.
- Policy changes support dry-run/simulation against historical/synthetic cases.
- If prize eligibility cannot be established, prize/redeemable functionality fails closed while harmless social play may remain available.
- Sweepstakes templates explicitly model free entry/AMOE, entry caps, terms versions and auditable entry source.
- Jurisdiction matrix is structured data, not scattered client logic.
- Privacy request orchestration spans all domains/providers.
- Retention is class/purpose-specific.
- Verified legal identity remains private; public identity is pseudonymous.
- Raw precise location/identity artifacts are minimized where derived eligibility status is sufficient.

## AI governance

- AI may support opponents/bots, matchmaking, moderation, fraud/risk, coaching/tutorials, personalization and highlight generation.
- AI opponents are clearly identified; ranked/prize modes do not silently substitute bots for humans.
- AI coaching/tactical recommendations are not available during consequential competitive play.
- AI inventory/registry records model/provider, purpose, inputs/outputs, risk tier and version.
- Consequential AI-supported decisions record model/config and remain policy-governed.
- Operator explanations may show reason factors/confidence; player explanations avoid exploit-enabling details.
- Provider-neutral AI gateway.
- No external-model training on platform/player data by default.
- AI tools never directly equal authorization; consequential tool actions remain structured, scoped and policy checked.
- AI kill switches/degraded deterministic paths are required.

## Analytics, telemetry, experimentation and FinOps

- Centralized event taxonomy with game-specific extensions.
- Governed event schemas and canonical metric definitions.
- OpenTelemetry-compatible correlation across matchmaking, allocation, match, result and reward.
- Security/audit/economic evidence is complete; high-volume performance traces may be sampled.
- Experiments use stable server-authoritative assignment and support mutual-exclusion groups.
- Ordinary growth experiments may not weaken protected security/identity/prize disclosures without explicit review.
- FinOps dimensions include tenant, game, service/domain, environment, region, owner and workload class.
- Track cost per active player, completed match, server/player-hour, tournament participant and tenant.
- Tenant cost-to-serve and cost anomalies are visible internally.

## Prototype and demonstration environment

- High-fidelity coded prototype, not Figma-only.
- Prototype is production-seed code: real architectural seams/contracts with simulated implementations behind them.
- Responsive web plus separate mobile prototype.
- Full platform simulation: multi-tenant switching, game states, matchmaking, balances, tournaments, prize flows, chat, leaderboards, moderation/admin, command-center behavior.
- Realistic seeded data that can be generated, reset and regenerated.
- Named scenarios include tournament surge, provider outage, fraud spike, prize dispute, tenant launch, matchmaking degradation and regional incident.
- Scenarios are deterministic by scenario ID/seed and simulated clock.
- Prototype emits production-like semantic events and diagnostic timelines.

## Business and commercial model

- Separate business proposition from detailed fundraising/cap-table modeling; the latter is out of scope.
- Include formal moat analysis and two-sided GTM for players and B2B tenants/game studios.
- Commercial operating model supports platform fees, partner economics, studio economics, prize exposure and unit economics.
- Default B2B model: **platform subscription/minimum commitment + measurable usage charges**, with optional modules.
- Core commercial scale metric: Monthly Active Players, supplemented by high-cost usage where appropriate.
- Core security/isolation/audit is never a premium add-on.
- Usage transparency and bill-shock controls for tenants.
- Metering comes from authoritative idempotent usage events.
- Studios may use license, revenue-share or commissioned models; certification remains commercially neutral.
- Prize obligations are tracked separately from recognized revenue and virtual-economy balances.

## High-fidelity design system decisions

- One primary task per screen.
- Same information architecture across platforms, device-appropriate composition.
- Semantic typography hierarchy; protected minimum sizes for consequential information.
- Dedicated numeric typography for scores, balances, timers and rankings.
- Semantic status colors are protected from tenant redefinition.
- Familiar system actions use familiar iconography.
- Confirmation intensity scales with consequence.
- Destructive controls use protected placement/patterns.
- Platform overlay remains unspoofable and always able to expose exit/report/connection controls.
- Protected value/economy components provide truthful semantics while games may wrap them in expressive presentation.
- Desktop leaderboards/brackets use dense structure; mobile emphasizes local/player progression context.
- Design tokens are shared between Figma and code with primitive → semantic → component → tenant alias layers.
- Tenant branding modifies approved tokens/content, not protected security/compliance/integrity structure.

## Engagement-design correction — supersedes earlier conservative language

This is a critical correction made after Q569.

### Governing rule

**Design for maximum legitimate engagement.** Use emotion, anticipation, competition, reward, momentum, urgency, social energy and appropriate risk-taking deliberately. Apply restraint only where presentation could materially distort the player’s understanding of cost, probability, loss, eligibility, scarcity, prize status, or the consequences of an action.

The platform is a game platform, not a compliance interface. Safeguards preserve truth, integrity and player agency; they do not suppress emotional game design.

### Revised decisions

- **Challenges/missions:** use daily, weekly, seasonal, event-based and escalating challenges as retention/re-engagement systems.
- **Streaks:** may deliberately create continuity pressure and loss aversion; genuine broken streaks may reset. Streak rules must be real and disclosed.
- **Countdowns:** use strong, escalating urgency for real deadlines. No fake/resetting countdowns.
- **Scarcity:** genuine scarcity should feel scarce; use rarity tiers, limited counts, exclusive windows and status. No fabricated scarcity.
- **Season passes:** use compelling progression, locked upcoming rewards, rarity, milestones and premium presentation; maintain competitive-integrity boundaries.
- **Randomized rewards:** theatrical suspense, reveals, rarity flashes, haptics and dramatic celebration are allowed. Do not fabricate near-miss frequency, misstate odds, or present an economic loss as a win.
- **Session/continued play:** optimize Result → Reward → Progression → Next Opportunity → Play Again. Routine wellness information belongs at natural boundaries and should not unnecessarily interrupt competition.
- **Promotion frequency:** use adaptive relevance/fatigue management rather than simplistic blanket caps; explicit opt-outs/dismissals remain respected.
- **Claim/reveal rituals:** authoritative grant occurs first, but UI should still create a compelling reveal/collect experience.
- **Experimentation:** actively test engagement psychology—CTA prominence, streak framing, urgency, reward intensity, social proof, animation, haptics, progression pacing—while factual fundamentals remain truthful.
- **Gaming + fintech balance:** fintech-grade clarity **before consequential decisions**; premium gaming-grade emotion during play and at outcome/reveal.
- **Confirmations:** avoid excessive friction; protect only actions whose consequence justifies it.
- **Economy UI:** protected truth layer + expressive thematic presentation layer.

### Mandatory two-sided adversarial review

Every future decision must ask both:

1. Could this design deceive, exploit, enable abuse, or misrepresent reality?
2. Are we being so cautious that we unnecessarily damage fun, retention, excitement, competition, conversion or commercial performance?

A design fails if it fails either side.

## Explicitly deferred or excluded

- Accessibility is not a primary design requirement for this project.
- Initial localization/multilingual support is excluded.
- Voice chat excluded; text only.
- Household/linked accounts excluded.
- Social-login providers excluded.
- Direct player challenge flow deferred; core venues are matchmaking, rooms and tournaments.
- Persistent rooms/communities deferred; rooms are ephemeral.
- Automatic human backfill excluded.
- General social-media feed excluded.
- On-prem/private-cloud deployment excluded.
- Public developer portal excluded.
- Generic item lending/rental marketplace excluded.
- Detailed cap-table/fundraising model excluded.

## Interview coverage by range

- **Q1–Q127:** product scope, audience, multi-game platform, compliance boundary, multi-tenancy, SDK, operations, business and brand scope.
- **Q128–Q159:** executive-deliverable framing and transition back into product UX; home/discovery/social decisions.
- **Q160–Q229:** crossplay, leaderboards, rooms, tournaments, onboarding, profiles, rewards, marketplace and player UX.
- **Q230–Q329:** AI, practice, sessions, trust, abuse, social controls, tenant transitions and mobile/browser behavior.
- **Q330–Q409:** SDK lifecycle, APIs, data/domain boundaries, RBAC, economy safety, observability, resilience, compliance, live ops and prototype contracts.
- **Q410–Q489:** security architecture, key/secrets, supply chain, incident response, recovery, AI governance, design tokens, analytics and requirements traceability.
- **Q490–Q529:** testing strategy, FinOps, search/recommendation integrity, support operations and certification evidence.
- **Q530–Q569:** high-fidelity visual standards and commercial/tenant economics.
- **Post-Q569 correction:** engagement design revised to maximize legitimate excitement and retention while preserving truthful economic/competitive representation.

## What happens after go

Only after the user explicitly says **go**:

1. Analyze the Cryptan Figma as the primary reference.
2. Research relevant direct and best-in-class adjacent competitors.
3. Produce the competitive/product teardown.
4. Derive the recommended technical stack from the research and workload requirements, including alternatives and why/why-not.
5. Produce separate build artifacts rather than one monolithic report.
6. Create high-fidelity redesigned concepts and end-to-end flows.
7. Build production-seed coded prototypes for responsive web and mobile.
8. Keep the executive overview narrative aimed at investors/board, while detailed product/engineering artifacts stand separately.
