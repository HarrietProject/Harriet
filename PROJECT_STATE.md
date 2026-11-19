# Project state

**As of:** 2026-11-18

**Maturity:** platform architecture under design, with a tested private Station pilot

## Public name

Harriet is the adopted public project and platform name, in honor of Harriet Tubman. The canonical controlled identifiers now follow the Harriet convention. This naming migration does not change implementation status. See [Why Harriet](WHY_HARRIET.md) and [RFC 0003](docs/rfc/0003-complete-harriet-identifier-migration.md).

## What exists

- Eight public repositories owned by `HarrietProject`.
- This canonical documentation and governance repository.
- Early architecture, doctrine, threat-model, and development documents.
- A separate `harriet-fieldnode` repository containing pre-prototype hardware documentation and no published test evidence.
- A private Harriet Station pilot with Windows and Apple Silicon macOS installation, signed contact exchange, and bounded delivery tests.

## Private pilot evidence

Harriet Station supports separate station identities, signed contacts, and explicit approval of requests to connect back.
A live two-host run delivered the original encrypted note after contact approval and verified the recipient's signed receipt.
Controlled tests exercised retry after a missing receipt and duplicate suppression for the same protected note over HTTPS.

A separate Pi bench retained a committed encrypted object through an abrupt power cut and delivered it after an operator-triggered recovery.
A compact LoRa bench delivered a queued encrypted object after the sender process exited and the recipient radio returned.
The recipient saved the object and returned a signed receipt. This was a directed bench run under operator control.

Phone pairing has worked on one local Wi-Fi client. A second handset is still under investigation.
Near-term work is to close that pairing test, make the Station checks repeatable, and qualify the current radio profile.
Automatic radio selection, range, power consumption, unattended relay recovery, and general platform conformance are open.

## Adopted and under design

Human intent is the stable abstraction; Harriet is a platform rather than one protocol or kit; Reticulum is the adopted target for the first profile, which remains under design without a conformance claim; ordinary relays do not require plaintext; translation is explicit; delivery controls remain separate and bounded; and upstream standards take precedence over reinvention.

The communication envelope, identity bindings, adaptive representation, receipts, custody, home relays, multipath, segmentation, Base contribution, expansion modules, and conformance suite remain under design.

## Not implemented

City-scale federation, automatic representation conversion, opportunistic phone exchange, OpenWrt packages, HF custody networks, vehicle carriage, satellite or optical convergence, planetary relays, and reputation systems are roadmap concepts only.

Claims advance through reference design, prototype, tested, qualified, and released only with versioned artifacts, reproducible procedures, recorded results, and limitations.

Known blockers include incomplete canonical licensing, unresolved public package and domain availability, absent platform schemas and fixtures, no independent security review, no hardware measurement campaign, and contradictory satellite repository descriptions. See the [repository audit](docs/project/repository-audit.md).
