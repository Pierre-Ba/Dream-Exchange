# Dream Exchange

> **Leave a dream. Take a dream.**

## What this is

Dream Exchange is an experiment in **reciprocal vulnerability**.

It is a place where people entrust their dreams to a shared archive and, by doing so, gain access to dreams that other people have entrusted to the community.

There is no money, no fame, no audience to accumulate, and no status to optimize.

The basic social contract is simple:

> **Dreams open to you when you open your dreams to the community.**

To enter this private human space, you must place something of yourself inside it too. Vulnerability is a two-way street. You cannot simply arrive to passively observe other people's inner lives.

The exchange is therefore not primarily dream-for-dream barter. It is reciprocal vulnerability.

---

## Core principles

### 1. Reciprocity

Access requires contribution. Someone who reveals nothing should not have unrestricted access to the vulnerability of people who do.

The exact mechanism is deliberately unresolved. The mechanism can evolve; the principle cannot:

> **Reading and revealing should remain meaningfully reciprocal.**

### 2. Dreams belong to their dreamers

This is non-negotiable. Contributing a dream does not transfer ownership to the platform, its operators, another participant, or the community.

> **You own your dreams. You are entrusted with other people's dreams.**

Access is not ownership. The product should say “dreams shared with you,” not “dreams you own.”

### 3. Anonymity is fundamental

Public identity must not be the price of belonging. A participant should be able to contribute without attaching their real-world identity to their dreams.

The system may need private continuity so a participant can manage their own archive, export or withdraw contributions, and maintain access. That continuity should not become visible to other participants.

Public identity should be scoped to the contribution, not the person. If a dream is shown with a pseudonym, that pseudonym should belong to that dream alone and should not allow readers to recognize the same contributor across multiple entries.

> **Private continuity, public discontinuity.**

Anonymity is not a secondary privacy feature. It is part of the architecture.

### 4. Dreams over dreamers

There should be no reason to accumulate followers, influence, prestige, or reach.

Avoid follower counts, popularity leaderboards, status hierarchies, engagement scores, public reputation scores, and persistent public contributor identities.

A reader should encounter a dream as a contribution, not as another post in a recognizable person's history. The archive may preserve continuity privately for the contributor, but it should not expose contribution counts, "more from this dreamer," or other metadata that lets public reputation accumulate around a person.

### 5. Nothing to gain by faking

It is impossible to prove that somebody actually dreamed what they say they dreamed. The project should not pretend otherwise.

Instead of intrusive authenticity policing, remove incentives to fabricate: no money, fame, follower count, reach, or status attached to extraordinary dreams.

The platform can establish **provenance**, not truth: when something was deposited, whether it was captured close to waking, whether it was later edited, and perhaps an immutable first version alongside later clarifications.

### 6. Mundane dreams are dreams

The platform must not create pressure to produce good literature. Extraordinary dreams, boring dreams, and tiny fragments are all legitimate contributions.

If spectacular dreams produce greater privileges, people will optimize for spectacle. The system should resist that dynamic.

### 7. No authenticity competition

There should be no authenticity score, trusted-dreamer leaderboard, or community vote on whether somebody's dream was “real.”

Abuse, spam, automation, harassment, and prohibited content are moderation problems. Whether somebody truly dreamed about a floating whale is not.

### 8. No purchased privilege

Money must not provide access to vulnerability that contribution would otherwise require.

Removing money changes the central question from “What is this dream worth?” to “What am I willing to reveal in order to enter this space?”

The absence of financial incentives is part of the culture, not merely a monetization choice.

### 9. Non-extraction

The archive must not quietly become raw material for an unrelated purpose.

A dream is contributed so that it may be experienced by another participant through the reciprocal exchange mechanism. That permission does not extend to academic research, public publication, machine-learning or AI training, advertising, behavioral profiling, commercial licensing, bulk analysis, or dataset creation.

These are not optional consent settings inside Dream Exchange. They are outside the permitted use of contributed dreams.

> **Your dreams will never be used to advertise to you.**

### 10. Revocability

Entrusting something should not mean surrendering it forever. The exact semantics of deletion and previously granted access require careful design, but the principle should favor the dreamer's continuing agency.

### 11. Portability

People should always be able to retrieve what **they** contributed. Exporting your own archive should be easy.

Receiving access to somebody else's dream does not create an export right. Dreams shared with you remain inside the archive and cannot be downloaded or exported as part of your own data.

### 12. Transparency

Trust should not depend entirely on promises from an operator. The software should be inspectable, and important rules governing storage, access, consent, deletion, and secondary use should be understandable.

The architecture should make betrayal difficult, not merely promise that current maintainers have good intentions.

---

## Open source, not open data

The software should be open source. The dream archive should emphatically **not** be open data.

The public repository may contain application code, protocols, database schemas, privacy mechanisms, moderation tooling, documentation, and governance processes. It must contain **zero dream content**.

> **The software belongs to everyone. Your dreams belong to you.**

The long-term ambition is not for the founder to remain indispensable. If the project succeeds, the community should eventually be capable of maintaining, auditing, forking, and preserving its infrastructure itself.

---

## The archive as a commons

The most valuable thing created by the project may not be any individual dream.

Over years, the archive could become an unusual record of human interior life: millions of small accounts of what human minds did when nobody was watching.

A future archive of that scale could become commercially valuable for AI training, psychological research, advertising, cultural analysis, or uses that do not yet exist. Safeguards should therefore be designed for the future moment when violating the principles might become financially tempting.

Good intentions today are not sufficient protection against incentives tomorrow.

---

# Toward a Reciprocal Archive Protocol

Dream Exchange may eventually be more than a single website.

> **A reciprocal archive is a collection of privately contributed human experiences in which access is earned through contribution rather than payment, status, or identity.**

Dreams would be the first implementation.

There are three useful layers:

**Principle** — Access to vulnerability requires vulnerability.

**Protocol** — Rules governing contribution, reciprocal access, anonymity, ownership, consent, revocation, and portability.

**Archive** — A particular community implementing those rules.

Separating these layers could allow different communities to experiment with forms of reciprocity without abandoning the underlying social contract.

## Federation without financialization

Decentralization does not require tokens, markets, cryptocurrency, or financial incentives.

In the future there could be many compatible archives: the original public Dream Exchange, language-specific communities, small private archives, communities devoted to particular kinds of dreams, or research archives operating under separate informed-consent rules.

### Content should not automatically federate

Unlike conventional federated social networks, dream content should probably not propagate freely between servers.

A dream can remain inside the archive to which it was entrusted. What may eventually federate are smaller proofs and permissions:

- anonymous or pseudonymous identity proofs;
- proof that someone has contributed;
- access requests;
- exchange invitations;
- consent;
- revocation.

The system could potentially prove **participation without exposing content**.

This is a direction to explore, not a requirement for the first implementation.

## Possible protocol vocabulary

**Dream** — A contribution belonging to one dreamer.

**Contribution** — The act of entrusting a dream to an archive.

**Access** — Permission for another participant to experience a dream.

**Exchange** — The reciprocal act through which access is granted.

**Consent** — The narrow permission required for reciprocal human reading.

In Dream Exchange, contributing a dream permits the archive to show that dream to another participant selected through the exchange mechanism. It does not permit participant search, targeted sharing, academic research, public publication, machine-learning use, or recipient export.

---

## Design through behavior, not ideology

Do not begin by designing an elaborate decentralized protocol. Begin with the smallest archive that genuinely embodies these principles.

Observe what people consider a meaningful contribution; what reciprocity feels fair; how anonymity behaves socially; what provenance matters; what deletion means after something has been shared; how contribution-scoped pseudonyms feel in practice; how random matching feels; how people react to fragments and mundane dreams; and where trust breaks.

Then extract the protocol from the behavior that works.

> **Dream archive → community norms → protocol**

rather than:

> Protocol → hope humans behave according to it.

---

# Product language matters

The interface should communicate the culture without requiring users to read a manifesto.

Instead of **Upload content**:

> **What did you dream?**

Instead of **Purchase / unlock**:

> **This dream is closed. Leave a dream of your own to enter.**

After contribution:

> **Thank you for trusting the archive. Another dream is now open to you.**

Instead of **Your collection**:

> **Dreams shared with you.**

Small language choices can reinforce the difference between possession and trust.

---

# A product test

When uncertain about a feature, imagine one participant:

Someone wakes at 4:17 AM after dreaming about their father, who died twelve years ago. They open the archive, write four incoherent sentences, and go back to sleep.

Ask:

> **Does this decision make that person more or less willing to leave those four sentences here?**

If follower counts make them less willing, do not add follower counts. If public profiles make them less willing, do not add public profiles. If automatic AI interpretation makes them less willing, do not impose it. If requiring a polished narrative makes them less willing, welcome fragments.

The goal is not to maximize consumption.

The goal is to create the conditions under which people are willing to **entrust something to one another**.

---

# Open questions

- What exactly does one contribution unlock?
- How should random matching behave when there are few eligible dreams of comparable length?
- Can recipients respond without creating social-media dynamics?
- How should contribution-scoped pseudonyms be generated and displayed?
- How much provenance should be visible?
- What happens to previously granted access when a dream is withdrawn?
- How should moderation work without compromising anonymity?
- How do we resist scraping and bulk extraction?
- Can participation be proven across independent archives without revealing dream content?
- What governance structure makes the founding principles difficult to overturn?
- What should never become a feature, even if users ask for it?

---

# North star

Dream Exchange should become infrastructure that its community can trust and eventually maintain without depending on its founder.

It should accumulate human experience without claiming ownership over it.

It should allow strangers to encounter one another's inner lives without turning those people into products, performers, audiences, or data inventory.

And it should preserve one simple bargain:

> **If you ask another human to open a small window into themselves, you should be willing to open one too.**
