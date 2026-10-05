# Design and Decision Principles

> Governing principles extracted from the discovery interview through Q569 and the subsequent engagement-design correction.
>
> This is the canonical principles document. Where earlier interview wording conflicts with these principles, this document governs.

## 1. Best practice is the default

Every interview/design question should begin with a concise research or best-practice note. If the industry norm clearly applies, make the decision and continue. Do not manufacture a strategic fork merely to ask the user for permission.

An alternative becomes strategic only when a concrete product constraint creates a real reason to deviate—for example compliance, economics, game integrity, tenant isolation, performance, security, or deliberate differentiation.

## 2. Adversarial thinking is mandatory—and two-sided

Every decision must pass two adversarial tests.

### Abuse test

Could this design be exploited through cheating or collusion, fraud or account abuse, incentive gaming, marketplace/economy manipulation, privacy/security failure, operator/tenant insider misuse, automation/bot abuse, denial of service or cost amplification, ambiguous/invalid state, or failure/retry/replay edge cases?

### Engagement test

Are safeguards unnecessarily reducing fun, excitement, competition, retention, momentum, conversion, legitimate urgency, social energy, appropriate risk-taking, or commercial performance?

A design can fail by being too permissive **or** too sterile.

## 3. Design for maximum legitimate engagement

This is a game platform, not a compliance interface.

Use emotion, anticipation, competition, progression, reward, scarcity, momentum, urgency, social proof, streaks, reveal rituals, dramatic audiovisual treatment, and appropriate risk-taking deliberately.

The boundary is **truthfulness**, not emotional intensity. Constrain a design only when it materially misrepresents:

- cost or value;
- odds/probability;
- whether the player won or lost;
- scarcity or expiration;
- eligibility;
- prize status;
- the consequences of an action;
- or the ability to leave/cancel.

### Consequential-decision rule

- **Before** a consequential economic/prize decision: fintech-grade clarity.
- **During play and at outcome/reveal:** premium gaming-grade emotion and spectacle.

### Examples explicitly encouraged

- dramatic tournament wins;
- rank-up celebrations;
- streaks and streak pressure;
- real countdowns;
- real scarcity and rarity;
- suspenseful randomized reward reveals;
- high-energy progress/milestone treatment;
- strong post-match Play Again/Next Match flows;
- limited-time events;
- reward anticipation;
- personalized re-engagement;
- meaningful social proof;
- adaptive promotion intensity based on relevance/fatigue;
- strong audiovisual and haptic reinforcement;
- escalating seasonal/event urgency.

### Examples explicitly prohibited

- fake/resetting countdowns;
- fabricated scarcity;
- obscured odds or currency relationships;
- manufactured near-miss frequency that falsely implies repeated almost-wins;
- presenting a net loss as an economic win;
- hiding exit/cancel while emphasizing continued play;
- silently changing promotion terms after participation;
- concealing material fees or true prize state.

## 4. Protect truth; free the presentation

For economic, prize, eligibility, and other consequential surfaces, separate the system into two layers:

- **Truth layer** — platform-owned, authoritative, protected semantics.
- **Presentation layer** — game- and tenant-expressive, highly emotional, thematic, and engagement-oriented.

A game may make a legitimate win spectacular. It may not make nonredeemable points look like cash, or an economic loss look like a win.

This allows premium game design without sacrificing financial, policy, or competitive truth.

## 5. Engagement loops are intentional product mechanics

Retention mechanics are not treated as defects merely because they encourage more play.

The platform may deliberately use:

- daily/weekly/seasonal challenges;
- chained objectives;
- streaks and streak recovery/preservation mechanics;
- premium seasonal progression;
- visible upcoming locked rewards;
- rarity, exclusivity, and genuine scarcity;
- real event countdowns;
- social proof;
- reward suspense and reveal rituals;
- personalized re-engagement;
- replay momentum.

The default post-match loop is:

**Result → Reward → Progression → Next Opportunity → Play Again**

Safeguards should interrupt this loop only when a concrete risk or policy requirement justifies it.

## 6. Experimentation may optimize engagement psychology

The experiment platform may test:

- CTA prominence;
- streak framing;
- challenge structure;
- urgency presentation;
- rarity presentation;
- reward sequencing;
- reveal intensity;
- animation/haptics/sound;
- post-match replay prompts;
- social proof;
- promotion frequency;
- progression pacing.

Protected factual fundamentals are not ordinary growth variables: actual price, governing odds, eligibility, prize state, material fees, and whether the player won or lost must remain truthful.

## 7. Friction is proportional to consequence

Do not confirm everything.

- Reversible/low-risk action: immediate.
- Consequential/irreversible action: proportionate confirmation.
- High-impact admin/economic/security action: strong re-authentication, scope preview, and approval as required.

Excessive confirmation is itself a product defect when it breaks gameplay momentum without preventing a concrete harm.

## 8. Simple player surface, sophisticated platform underneath

Players should not need to understand tenant routing, provider orchestration, fraud scoring, reconciliation, policy engines, event sourcing, distributed transactions, regional capacity, or certification mechanics.

The interface should answer: **What is this? What can I do with it? What happens if I act?**

## 9. Coordination before play; authority during play; transparency after play

- Before play: rooms, parties, preferences and settings can be flexible.
- During play: authoritative server state wins; platform chrome recedes; interference is minimized.
- After play: results, rewards, review holds, disputes and consequences are transparent and reviewable.

## 10. Authority is narrow and explicit

Games, tenants, providers, operators and clients receive only the capabilities they need. Extensibility is safe only when extension points are narrower than the platform they extend.

No client assertion becomes authoritative merely because it was authenticated. `PlayerWon` is a server-produced fact, not a client command.

## 11. Consequential value requires stronger controls

Anything affecting prizes, transferable value, tradable assets, external fulfillment, identity, sanctions or competitive integrity receives stronger validation, idempotency, auditing, authorization, review, failure handling and reproducibility.

These controls protect truth and integrity; they should not unnecessarily suppress celebration, urgency, suspense, or other legitimate game presentation.

## 12. Multi-tenancy means isolated experiences on shared mature infrastructure

The platform shares infrastructure and global identity underneath while keeping tenant-facing state, branding, social graphs, catalogs, promotions and admin scopes isolated. Tenant transitions are explicit.

Tenants customize approved tokens, content and configuration; they do not fork protected security, compliance or game-integrity semantics.

## 13. Identity can be flexible; accountability cannot

Players may use different pseudonyms per tenant. Display names can change. Tenants can change. Rooms can disappear.

Internally, every consequential action remains tied to a durable actor, tenant, policy version, event and audit trail.

## 14. Provider agnosticism is a platform property

Payments/payout, KYC, geolocation, fraud, moderation, messaging, analytics, AI and related external systems are adapters behind platform contracts. No core business workflow should become indistinguishable from a vendor API.

## 15. Anything configurable has bounds

Live config, economy parameters, promotions, tenant rules, experiments, feature flags and admin actions require schemas, allowed ranges, owners, previews/dry-runs where appropriate, auditability, rollback or kill-switch behavior, and approval thresholds proportional to risk.

## 16. Anything consequential must be reproducible

A dispute or incident should be reconstructable from authoritative events, state transition, policy version, game/build/SDK version, AI model/config where relevant, operator actions, provider events, correlation IDs and certification evidence.

## 17. Failure is a designed state

The system must be useful and safe under disconnect, provider outage, regional degradation, duplicate/reordered events, delayed callbacks, stale clients, partial multi-service failure, overloaded queues, operator mistake, malicious input, and rollback/recovery.

Do not treat the happy path as the specification.

## 18. Requirements are complete only when verifiable

Each consequential requirement should ultimately link to domain/owner, design artifact, architecture component, API/data contract, risk class, test/certification evidence and implementation status.

Target lifecycle: **Specified → Designed → Implemented → Verified**.

## 19. Interview remains discovery until go

The existence of strong requirements is not authorization to begin the reference teardown or build. The explicit trigger remains the user saying **go**.
