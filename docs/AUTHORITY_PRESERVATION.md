Authority Preservation

Overview

Distributed systems must determine which decisions are valid.

This process requires some form of authority.

Authority may be represented by:

- leaders
- coordinators
- consensus groups
- quorum systems
- validation boundaries

Without authority preservation, correctness becomes difficult to maintain.

---

The Problem

Infrastructure changes.

Nodes fail.

Networks partition.

Systems restart.

During these events, competing authority claims may appear.

The challenge is determining which claim remains valid.

---

Authority Failure Scenarios

Split-Brain

Multiple partitions simultaneously claim legitimacy.

Example:

Partition A → Authority A
Partition B → Authority B

Both cannot be correct at the same time.

---

Stale Authority

An older authority attempts to resume control after being replaced.

Example:

Authority v10
→ Authority v11
→ Authority v10 returns

The older authority should not automatically regain control.

---

Recovery Races

Multiple recovering nodes attempt to establish authority simultaneously.

The system must determine a canonical outcome.

---

Regional Isolation

A region becomes disconnected.

When connectivity returns:

- preserve canonical history
- reject contradictory authority claims
- avoid state corruption

---

Desired Properties

Single Canonical Authority

Only one authority chain should be accepted as canonical.

Deterministic Decisions

Authority outcomes should not depend on randomness.

Replay Resistance

Old authority transitions should not be reusable.

History Preservation

Authority changes must not rewrite accepted history.

Recovery Safety

Recovery must not introduce competing truths.

---

Research Questions

How should authority be transferred?

How should stale claims be rejected?

How should competing claims be evaluated?

How should authority survive transport instability?

---

Authority and Continuity

Many systems implicitly couple authority to infrastructure.

Examples include:

- server ownership
- network location
- process identity

Research into continuity-oriented systems explores whether authority can remain stable despite infrastructure change.

---

Validation Topics

Potential validation areas include:

- authority transitions
- lineage verification
- split-brain containment
- authority recovery races
- reintegration behavior
- blackout recovery

---

Core Observation

Transport changes are common.

Authority corruption should not be.

Preserving authority may be one of the most important requirements for maintaining execution correctness.

---

Open Research Topics

- authority lineage models
- deterministic authority transitions
- canonical authority selection
- authority preservation across migration
- authority preservation during recovery

---

A distributed system may survive infrastructure failure.

The harder challenge is preserving legitimate authority afterward.