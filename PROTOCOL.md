# Reciprocal Archive Protocol

> **Draft — 0.1**
>
> This document is an early attempt to describe the protocol beneath Dream Exchange.
> It is intentionally incomplete. The goal is to name the core objects, rules, and
> invariants clearly enough to guide experiments without prematurely fixing the
> technical implementation.

Dream Exchange begins with a simple social rule:

> **Access to vulnerability requires vulnerability.**

The protocol exists to make that rule portable.

It should allow a community to say: a person has made a qualifying contribution,
therefore that person may receive access to a contribution entrusted by someone else.

The protocol does **not** decide whether a contribution is true, valuable, beautiful,
interesting, or important.

It only coordinates reciprocal access.

---

## 1. Scope

A **Reciprocal Archive** is a collection of privately contributed human experiences
in which access is earned through contribution rather than payment, status, fame,
or public identity.

Dream Exchange is the first intended implementation.

A future archive might contain dreams, fears, memories, confessions, letters never
sent, or another form of personal human experience. Each archive decides what counts
as a qualifying contribution.

This protocol should remain content-agnostic where possible.

---

## 2. Goals

The protocol should make it possible to:

1. contribute something privately to an archive;
2. retain ownership and agency over that contribution;
3. receive a proof that a qualifying contribution was made;
4. use that proof to obtain reciprocal access;
5. grant access without transferring ownership;
6. participate without exposing a persistent public identity;
7. revoke or withdraw a contribution according to the archive's rules;
8. export one's own contributions;
9. express consent for uses beyond ordinary human reading;
10. eventually allow compatible archives to recognize participation without exchanging the underlying private content.

The protocol should make these actions possible without introducing social ranking,
financial privilege, or a requirement for public identity.

---

## 3. Non-goals

The protocol is not intended to:

- prove that a reported experience really happened;
- judge the quality or emotional value of a contribution;
- create a reputation score;
- rank contributors;
- maximize engagement or time spent;
- create a market price for contributions;
- create transferable financial assets or tokens;
- make archive content publicly indexable by default;
- enable bulk extraction of contributed material;
- imply consent for advertising, profiling, research, AI training, or commercial reuse merely because something was contributed.

A Reciprocal Archive is not a marketplace and should not accidentally become one.

---

## 4. Core invariants

An implementation may experiment with its user experience and reciprocity rules, but
a compatible Reciprocal Archive should preserve the following invariants.

### 4.1 Contribution before access

A participant must make a qualifying contribution before receiving reciprocal access
that would otherwise be unavailable.

The exact exchange mechanism is archive-specific.

### 4.2 Access is not ownership

Receiving access to another person's contribution does not transfer ownership of that
contribution.

> **You own your contributions. You are entrusted with other people's contributions.**

### 4.3 No purchased access

Money must not bypass the reciprocity requirement.

An archive may need funding to operate, but payment must not purchase privileged
access to contributions.

### 4.4 No status privilege

Popularity, followers, public identity, reputation, wealth, or influence must not
grant greater access than reciprocal contribution would otherwise provide.

### 4.5 Conservative consent

Contribution grants only the permissions necessary for the intended archive
experience.

Other uses require separate consent.

### 4.6 Content remains private by default

Contributed material must not become public or federated merely because it exists in
a Reciprocal Archive.

### 4.7 Participant agency

Contributors should retain meaningful control over their own material, including
export and withdrawal according to clearly stated rules.

---

## 5. Core objects

The names below are conceptual. They do not prescribe a database schema or wire
format.

### Participant

An entity capable of contributing to and receiving access from an archive.

A participant may have a private account or internal identifier so the archive can maintain ownership, access, export, withdrawal, moderation, and the participant's personal archive.

That continuity is for the participant and the system. It should not become a persistent public identity visible to other participants.

The protocol should not expose a real-world identity or a reusable public pseudonym as a requirement for participation.

### Contribution

A private item entrusted by a participant to an archive.

For Dream Exchange, a contribution is a dream or dream fragment.

A contribution may carry a **contribution-scoped pseudonym** for authorship. This pseudonym belongs to that contribution, not to the participant, and should not make separate contributions publicly linkable to the same person.

A contribution may include limited metadata such as:

- creation or deposit timestamp;
- approximate time of the original experience;
- content type;
- coarse length class;
- whether the contribution was later edited;
- consent preferences.

Metadata should be minimized. An archive should collect only what serves a clear
purpose.

### Contribution Class

A coarse description used when an archive wants reciprocity to be proportionate.

For Dream Exchange, an initial implementation might classify contributions as:

- fragment;
- short;
- medium;
- long.

This is not a quality score.

Its purpose is to make exchanges feel reasonably reciprocal. A short contribution
can unlock a short contribution; a longer contribution can unlock something of
roughly similar scale.

The exact classification method is implementation-specific and should remain coarse
enough to avoid turning word count into a game.

### Contribution Proof

An attestation that a participant made a qualifying contribution.

A proof should reveal as little as possible.

Conceptually, it may state only:

> A qualifying contribution of class X was accepted by archive Y.

It should not reveal the contribution itself.

A proof does not attest that the contribution is true.

A future privacy-preserving implementation may allow such proofs to be presented
without revealing a participant's identity or linking separate uses unnecessarily.

### Access Grant

Permission for a participant to read or otherwise experience a specific contribution.

An access grant is not a transfer of ownership.

It may be temporary, persistent, revocable, or subject to other archive-specific
rules, but those rules must be visible to participants.

### Exchange

The event that connects a qualifying contribution or contribution proof with an
access grant.

For example:

```text
Participant A contributes a short dream
        ↓
Archive accepts the contribution
        ↓
Archive issues a short-contribution proof
        ↓
Proof is redeemed
        ↓
Participant A receives access to a short dream
```

An exchange need not pair two people directly.

### Consent

A machine-readable and human-readable expression of permitted uses.

An archive may distinguish permissions such as:

- human reading inside the archive;
- discovery or search within the archive;
- sharing with specifically authorized participants;
- academic research;
- public publication;
- machine-learning or AI use;
- recipient export.

The default should be the minimum necessary permission.

Absence of consent must not be interpreted as consent.

### Withdrawal

An action by which a contributor asks the archive to stop making their contribution
available.

The exact semantics are still unresolved because recipients may already have seen
the material. The protocol should distinguish between:

- preventing future access;
- revoking active access where technically possible;
- deleting archive-held copies;
- the impossibility of making another human forget what they have already read.

The system should communicate these distinctions honestly.

---

## 6. Reciprocity

Reciprocity is the heart of the protocol, but its precise mechanism should not be
fixed too early.

Possible archive rules include:

### One-for-one

One qualifying contribution grants access to one contribution.

### Proportional

A contribution grants access to another contribution of roughly comparable class.

This is the current leading model for Dream Exchange.

The intent is not to assign value. It is to avoid a participant sharing a long,
carefully recorded dream and consistently receiving tiny fragments in return.

### Time-based participation

A recent qualifying contribution opens the archive for a limited period.

### Direct exchange

Two participants explicitly choose to reveal contributions to one another.

### Reciprocal circle

A small group contributes before any member receives access to the group's contributions.

Different archives may experiment with different mechanisms.

Compatibility should depend on preserving reciprocity, not on using one exact exchange rule.

---

## 7. Authenticity and provenance

The protocol does not attempt to prove subjective experience.

For Dream Exchange there is no reliable way to prove that a dream was actually dreamed.

Therefore:

> **The protocol attests to contribution, not truth.**

Archives may preserve provenance such as deposit time, revision history, or whether
an entry was captured soon after waking.

Provenance should not become an authenticity score.

There should be no protocol-level concept of a "trusted dreamer" or a vote on whether
someone's experience was real.

The preferred defense against fabrication is cultural and structural: remove the
rewards for fabrication.

---

## 8. Privacy model

Privacy should be treated as a protocol property, not merely a UI setting.

An implementation should aim to minimize the ability to connect:

- a real-world identity to a participant;
- a participant to unnecessary metadata;
- separate public contributions to the same participant;
- contribution proofs to the underlying content;
- activity across archives.

The intended model is:

> **Private continuity, public discontinuity.**

The archive may know that many contributions belong to the same participant because that participant needs a coherent personal archive and the system needs to enforce ownership, access, withdrawal, moderation, and reciprocity.

Other participants should not be able to infer that continuity from the public interface or protocol metadata.

Public authorship, if shown, should be contribution-scoped. A generated pseudonym may identify the author of one contribution, but it should not be reused in a way that makes the same contributor recognizable across multiple contributions.

The protocol should avoid public contribution counts, "more from this participant" links, reusable profile handles, or other mechanisms that let reputation accumulate around a contributor.

---

## 9. Federation

Federation is a possible future capability, not an MVP requirement.

The protocol should distinguish **federating participation** from **federating content**.

### Content should stay where it was entrusted

A contribution should not automatically replicate across compatible archives.

If a participant entrusted something to Archive A, Archive B should not receive a
copy merely because the archives interoperate.

### Proofs may travel

What may eventually travel between archives are privacy-preserving statements such
as:

- this participant made a qualifying contribution;
- the contribution belonged to a certain coarse class;
- this proof has not already been redeemed;
- this participant has permission for a particular action.

This would allow Archive B to recognize reciprocity without receiving the private
content held by Archive A.

### No global participation ledger

Federation should not require a public ledger of contributions or exchanges.

In particular, interoperability should not create a global map of who contributed
what, where, and when.

---

## 10. Proof properties

A future interoperable Contribution Proof should ideally be:

### Minimal

It reveals only what the receiving archive needs to know.

### Unforgeable

A participant should not be able to mint arbitrary proofs without making a qualifying
contribution.

### Non-content-bearing

The proof must not contain the private contribution.

### Privacy-preserving

Presenting a proof should not unnecessarily reveal real-world identity or unrelated
activity.

### Replay-aware

If a proof represents a single exchange entitlement, archives need a way to prevent
unlimited reuse.

### Non-financial

Proofs are access credentials, not assets.

They should not be designed for sale, speculation, transfer markets, or accumulation
as wealth.

The technical mechanism is deliberately unspecified. Signed credentials, anonymous
credentials, capabilities, and zero-knowledge techniques are possible areas of
exploration, not current commitments.

---

## 11. Interoperability

A future version of the protocol may define a small common vocabulary so that
independent archives can understand one another.

A minimal interoperable exchange might eventually communicate:

```json
{
  "protocol": "reciprocal-archive",
  "version": "0.x",
  "archive": "<archive identifier>",
  "proof_type": "qualifying-contribution",
  "contribution_type": "dream",
  "class": "short",
  "redeemable": true
}
```

This example is illustrative only.

It is not a proposed final schema and must not be treated as one.

The protocol should be extracted from real archive behavior before its wire format is
standardized.

---

## 12. Trust boundaries

A participant may need to trust an archive operator with some information.

The protocol should continuously reduce how much trust is required.

Questions every implementation should be able to answer include:

- Who can read raw contributions?
- Are contributions encrypted at rest?
- What metadata is retained?
- Are logs capable of containing contribution text?
- What happens to backups after withdrawal?
- Can administrators bulk-export the archive?
- How are moderation reports handled?
- What code determines eligibility and access?
- Can the operator silently change consent rules?
- How are protocol changes governed?

Open-source software helps make these answers inspectable, but open source alone does
not guarantee good data stewardship.

---

## 13. Archive compatibility

A future conformance specification may define what an archive must do to call itself
a **Reciprocal Archive**.

At minimum, compatibility is likely to require:

1. meaningful contribution before reciprocal access;
2. contributor ownership of contributed material;
3. no payment bypass for reciprocal access;
4. no requirement for persistent public identity, with participant continuity kept private by default;
5. no protocol-level social ranking;
6. conservative consent;
7. no automatic secondary use of contributions;
8. participant export of their own material;
9. transparent withdrawal semantics;
10. no automatic federation of private content.

These requirements are provisional.

---

## 14. Dream Exchange: initial interpretation

For the first Dream Exchange experiment, the simplest protocol interpretation may
be:

1. A participant submits a dream or dream fragment.
2. The system assigns it a coarse length class.
3. The dream is stored privately.
4. The participant receives one exchange entitlement of the same class.
5. Redeeming the entitlement reveals one previously unseen dream of approximately
   the same class from another participant.
6. The entitlement is consumed.
7. The recipient gains no ownership over the dream.
8. The original dreamer may later withdraw their dream according to the archive's
   published withdrawal rules.

There are intentionally no followers, likes, popularity rankings, public reputation
scores, or purchased entitlements.

This is a hypothesis to test, not the definition of the final protocol.

---

## 15. Questions deliberately left open

The following should be learned through real use before being standardized:

- What counts as a meaningful contribution?
- How coarse should contribution classes be?
- Should matching be random, chosen, or partially guided?
- When exactly is a contribution proof issued?
- Can an entitlement expire?
- Can a participant save access for later?
- What does withdrawal mean after another person has read a contribution?
- How should contribution-scoped pseudonyms be generated, displayed, and prevented from becoming cross-contribution identifiers?
- Should proofs work across archives?
- How can cross-archive proofs avoid becoming tracking identifiers?
- How should abuse prevention work without weakening anonymity?
- How can archives resist scraping and bulk extraction?
- What moderation information may safely move between archives?
- What governance process may alter protocol invariants?
- Which properties should remain social norms rather than technical rules?

---

## 16. Development philosophy

The protocol should follow the community, not precede it.

> **Dream archive → community norms → protocol**

The first implementation should optimize for learning.

Where the social behavior is not yet understood, the protocol should remain
deliberately underspecified.

Where a principle protects participants from extraction, ownership loss, purchased
privilege, or unwanted exposure, it should be specified strongly.

The aim is not to invent an elaborate decentralized system before anyone uses Dream
Exchange.

The aim is to discover the smallest set of rules that allows strangers to entrust
something vulnerable to one another with reciprocity and respect.

---

## Status

This document is a starting point.

Nothing here should be treated as a finalized standard, stable API, security model,
or interoperability commitment.

The protocol should evolve through implementation, observation, discussion, and
community governance.

For the values that should constrain that evolution, see
[PRINCIPLES.md](./PRINCIPLES.md).
