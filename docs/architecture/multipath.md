# Multipath

**State:** Architecture under design; not implemented.

Planners may use multiple viable paths when policy and replica budgets allow. Metrics can include latency, capacity, energy, trust, congestion, scheduled availability, administrative preference, and delivery history. Path diversity must be real; nominally different links sharing one failure domain should not be counted twice.

The project may borrow ECMP, MPTCP concepts, anycast-like rendezvous, and scheduled contacts at the appropriate layer. It will not mechanically merge routing protocols.

Each carriage profile owns route discovery, loop prevention, metrics, and congestion behavior. The delivery overlay consumes only exposed capabilities and selects bounded attempts and replicas; it does not inject one protocol's routes into another. Adapters must declare metric meaning, freshness, uncertainty, and known shared failure domains.

Routing Information Protocol version 2 (RIPv2) provides precedent for expiring route facts, triggered updates, and loop controls. See [RFC 2453](https://www.rfc-editor.org/rfc/rfc2453.html).

In Harriet, verified path changes can trigger a new evaluation of queued work. Back off when there is no new evidence and keep an attempt unconfirmed when its outcome is ambiguous. Custody and signed delivery evidence belong to the message, independently of route availability.

The [cross-carrier field-validation plan](../development/cross-carrier-field-validation.md) proposes a first test with distinct failure domains, using a radio hop followed by a delayed IP hop.
