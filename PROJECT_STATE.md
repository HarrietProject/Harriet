# Project state

**As of:** 2026-11-22

**Maturity:** platform architecture under design, with a tested private Station prototype

## Public name

Harriet is the adopted public project and platform name, in honor of Harriet Tubman. The canonical controlled identifiers now follow the Harriet convention. This naming migration does not change implementation status. See [Why Harriet](WHY_HARRIET.md) and [RFC 0003](docs/rfc/0003-complete-harriet-identifier-migration.md).

## What exists

- Eight public repositories owned by `HarrietProject`.
- This canonical documentation and governance repository.
- Early architecture, doctrine, threat-model, and development documents.
- A separate `harriet-fieldnode` repository containing pre-prototype hardware documentation and no published test evidence.
- A private Harriet Station pilot installed on Windows and Apple Silicon macOS, with separate identities and bounded delivery tests.
- No public platform implementation, released package, qualified hardware, production service, or active federation is established.

## Private pilot evidence

The pilot supports named recipients, signed public contact cards shared by QR code or file, fingerprint checks, and explicit approval of reciprocal contact requests. A live macOS-to-Windows HTTPS delivery verified the original sealed note and the recipient's signed receipt after contact approval. A prior unconfirmed send was consistent with the receive policy requiring a verified sender. Its exact rejection reason was unlogged. Controlled HTTPS tests exercised retry after a lost receipt, duplicate suppression, and recovery after restart.

A compact encrypted note and its signed receipt made a directed, short-range LoRa round trip. A separate delayed LoRa run retained the sealed note after the sender process exited and sent it after the recipient returned, with operator coordination. A wired Raspberry Pi run demonstrated queue survival across abrupt power loss and later delivery with operator-triggered recovery. These are bounded prototype results.

A separate private setup QR opens the Station's phone interface. One phone reached the local Station. Another reported repeated browser failures against both pilot hosts and timed out when trying private IPv6. A fix for HTTPS connection closure was verified between desktop hosts. The cause of the handset failure is still open.

## Adopted and under design

Human intent is the stable abstraction; Harriet is a platform rather than one protocol or kit; Reticulum is the adopted target for the first profile, which remains under design without a conformance claim; ordinary relays do not require plaintext; translation is explicit; delivery controls remain separate and bounded; and upstream standards take precedence over reinvention.

The complete communication envelope, identity lifecycle, adaptive representation, custody, home relays, multipath, segmentation, Base contribution, expansion modules, and conformance suite remain under design. The phone interface in the private pilot requires a reachable Station. A native mobile sender that can queue offline, Linux and Pi installation, energy measurements, unattended cross-carrier delivery, and real-world range remain open.

A Detroit-area desktop path survey found modeled obstructions along an illustrative rooftop route. Direct and relayed field viability remain unverified. The [cross-carrier field-validation plan](docs/development/cross-carrier-field-validation.md) defines the proposed travel-outage, range, and recovery tests.

## Not implemented

City-scale federation, automatic representation conversion, opportunistic phone exchange, OpenWrt packages, HF custody networks, vehicle carriage, satellite or optical convergence, planetary relays, and reputation systems are roadmap concepts only.

Claims advance through reference design, prototype, tested, qualified, and released only with versioned artifacts, reproducible procedures, recorded results, and limitations.

Known blockers include incomplete canonical licensing, unresolved public package and domain availability, absent platform schemas and fixtures, no independent security review, no hardware measurement campaign, and contradictory satellite repository descriptions. See the [repository audit](docs/project/repository-audit.md).
