# Offline preparedness on Anchor and Brick

**State:** Proposed device integration with a tested private, single-computer fixture.

## Product boundary

The offline preparedness reader is one part of the software intended for both
Anchor, the base station, and Brick, the handheld. It keeps field guides and
other reference material readable locally without enrollment. Brick's intended local functions require no cloud service. The design calls for
local reading and message queuing during disconnection. Anchor can host more local storage or processing as its
hardware permits. Application capabilities should follow the device and
currently available interfaces.

Messaging is optional. When a person enables it, use the existing Harriet
person and device identity and contact model. Local reading does not require a
message identity. Transfer admission, content receipt, update trust, and
installation are independent.

## What the private fixture exercised

A bridge reused the existing offline reader and pinned Harriet Station
identity, contact, queue, and receipt code. On one computer using synthetic
identities and a file-based mock path, the fixture exercised the following:

- Create an expiring, one-use invitation with explicit fingerprint comparison
  and reciprocal approval. Reopen the same invitation records after an
  interrupted handoff. The issuer's local ledger enforces one use within the
  fixture.
- Queue an encrypted check-in offline for a selected contact. Reopen it after
  a process restart. A mock custodian stores the sealed object, and the
  recipient inbox suppresses duplicate copies.
- Withhold the first receipt, then recover the same delivery evidence on retry.
  An exact-object signature from the authorized endpoint after durable save
  establishes device delivery. Human acknowledgment remains separate.
- Send a guide-update notice with a version, size, and digest. The notice
  carries metadata and offers no installation authority.
- Carry optional position only when explicitly attached, with source, timestamp,
  accuracy, and staleness. Live sensors were outside the fixture.

The clean private review run passed 30 tests and a separate multi-process
drill. These checks exercised the fixture's local code and state transitions. Device
installation, disconnected boot and restore, two-device operation, live
transports, sensor accuracy, and field power remain open. The current Station
browser interface still needs a reachable host. See the
[prototype evidence](prototype-evidence.md) for earlier, separate tests.

## Proposed device and community work

First, run the attended two-device fixture with exported sealed objects and
independent fingerprint confirmation. When that passes, qualify actual local
transports one profile at a time and report which capabilities each device has.
Location, nearby Bluetooth, Meshtastic, MeshCore, and cellular can be optional
capabilities when supported and authorized. Availability can change during use.

## Capability and content proposals

An on-device capability view should show which interfaces are present, which
access the owner granted, what passed a functional check, how long the check is
valid, and the fallback. Recheck on resume, unplug, permission change, and
resource pressure. Keep printing, ordinary search, and local reading available
when an optional service stops. Give the reader a narrow handoff for authorized
message intents while Station retains contacts, keys, retries, and receipts.
An adapter's inventory or transport acknowledgment does not establish delivery.

Distribute small signed content descriptors separately from larger map,
reference, or model packs. Preserve package provenance, edition, region, rights,
version, and digest. Require trusted update and rollback behavior before
activation. Local inference is optional and should yield to reading and the
outbox. Qualify it first on source-linked retrieval from installed guides.
Future guides and recipes can share provenance and content metadata. Their
distribution needs its own review.

## Staffed locations and public discovery

Early setup may offer an optional local identity and public discovery. A
participating staffed location could publish time-bounded service notices,
hold sealed notes for later pickup, and direct people to a private reunification
process. A peer observation and an issuer-confirmed notice need distinct labels.
Record who issued a notice, when it was checked, when it expires, and how it
can be corrected or withdrawn.

A public posting or cache needs a separate audience and retention choice.
Keep names, precise locations, travel plans, and case details in an authorized
private handoff. Public discovery, caches, staffed-station directories, and
shared pack distribution remain proposals. No public enrollment or bulletin
service has been implemented.
