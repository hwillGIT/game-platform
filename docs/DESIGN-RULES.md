# Governing Product, Interview and Design Rules

_Last updated: 2026-10-04_

These rules govern the rest of the interview and supersede any earlier wording that conflicts with them.

## 1. Best practice is the default

When an industry best practice or dominant pattern is clear:

- research it;
- state it;
- adopt it;
- move on.

Do not ask the user to choose among alternatives unless there is a strong, specific reason the default may not fit this product.

## 2. Every decision gets an adversarial review

For each meaningful requirement, test:

- cheating;
- fraud;
- collusion;
- incentive gaming;
- abuse;
- operator/tenant misuse;
- privacy/security failure;
- race conditions;
- failure/recovery;
- economic exploitation;
- unintended emergent behavior.

## 3. Adversarial thinking runs in both directions

Ask both:

1. Could this design deceive, manipulate, exploit or misrepresent?
2. Are our safeguards unnecessarily harming fun, retention, competition, conversion or commercial performance?

A design can fail by being unsafe **or** by being unnecessarily sterile.

## 4. Engagement is a first-class design objective

The platform should deliberately optimize for:

- excitement;
- anticipation;
- competition;
- progression;
- social energy;
- continued play;
- replay velocity;
- reward salience;
- appropriate risk-taking;
- commercial performance.

The constraint is **truthfulness**, not emotional intensity.

### Explicitly encouraged

- streaks;
- challenge chains;
- momentum;
- progress bars;
- real countdowns;
- real scarcity;
- seasonal urgency;
- dramatic reveal sequences;
- rarity effects;
- rank-up celebrations;
- tournament advancement;
- genuine prize celebrations;
- strong post-match Play Again flow;
- social proof;
- limited-time events;
- reward suspense;
- haptics/motion/sound;
- adaptive engagement optimization.

### Not allowed

- fake scarcity;
- countdowns that reset deceptively;
- hiding material fees;
- presenting loss as an economic win;
- misrepresenting odds;
- mislabeling currency/value;
- concealing prize status;
- materially misleading near-miss effects;
- hiding exit/cancel so thoroughly that agency is impaired.

## 5. Truth layer + expressive presentation layer

For economy/prize/value surfaces:

- the **truth layer** is platform-protected and authoritative;
- the **presentation layer** may be highly expressive and game-specific.

A game may make a legitimate win spectacular. It may not make nonredeemable points look like cash.

## 6. Clarity belongs at the decision boundary

Before a consequential commitment, provide fintech-grade clarity:

- what is being committed;
- what value/currency is involved;
- material rules/conditions;
- prize/odds information where required;
- relevant restrictions.

After commitment, during play and at outcome, use premium-gaming-grade emotion.

## 7. Friction is proportional to consequence

Do not confirm everything.

- Reversible/low-risk action: immediate.
- Consequential/irreversible action: proportionate confirmation.
- High-impact admin/economic/security action: strong re-auth, scope preview and approval as required.

## 8. Coordination before play; authority during play; transparency after play

- Pre-match: flexible coordination.
- In-match: server authority and stable rules.
- Post-match: visible outcome, reward, review/dispute status and next action.

## 9. Player complexity should stay low

The player should not need to understand:

- multi-tenancy;
- provider orchestration;
- policy-evaluation internals;
- distributed consistency;
- fraud scoring;
- reconciliation;
- operational failover.

The platform handles that complexity underneath.

## 10. Requirements must be traceable

Each consequential requirement should eventually map to:

- domain;
- owner;
- actor;
- risk class;
- UX/design artifact;
- service/component;
- API/event/data contract;
- policy;
- test/certification evidence;
- implementation state.

Status model:

`Specified → Designed → Implemented → Verified`

Critical security, integrity, economy, compliance and reliability requirements may not be considered release-ready without linked verification evidence.
