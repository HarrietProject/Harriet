# Vision

## North star

**The underlying medium changes. The human intent persists.**

Harriet seeks to make communication resilient, user-controlled, interoperable, openly specified, and infrastructure-independent where possible. A sender expresses the recipient, meaning, urgency, acceptable transformations, and required evidence. The platform then uses viable resources without pretending unavailable connectivity exists.

Choose a person once and let Harriet pursue permitted ways to reach them as networks, locations, and available power change. A home base can stay in one place while a traveler composes offline and hands off a sealed note to a nearby node. Each hop can happen at a different time. A surviving connection or a device that moves between places can bridge isolated networks. The [travel outage scenario](docs/development/cross-carrier-field-validation.md#portable-outage-scenario) makes this a concrete test.

Carry as much sender-authorized detail as feasible. On a constrained link, prioritize the minimum useful version the sender has approved, then send further detail if a later opportunity and the policy allow it.

## Ordinary participation

Eventual ordinary participation must allow a person to install or download Harriet, identify who must be reached, express simple privacy, urgency, acceptable-degradation, and acknowledgment preferences, and let the system handle technical profiles underneath. Command-line expertise and networking knowledge must not be prerequisites. This is an architectural requirement, not a claim of current implementation.

The goal is a mobile-first experience across Android, macOS, Windows, and Linux, including Raspberry Pi OS for stations and relays. A sender should be able to share a public contact by QR code or file, verify it, and send to a person by name. Away from a base, the device should retain an encrypted note without a connection and distinguish local storage, relay custody, and signed delivery.

## Ownership boundary

Harriet should own only the missing connective layer: a protocol-neutral description of communication intent; capability and policy exchange; provenance-preserving transformations; bounded delivery and custody behavior; adapter profiles; and conformance tests.

Identity primitives, cryptography, routing, radio firmware, delay-tolerant networking, local mesh, storage, operating systems, codecs, and physical transports should come from open standards and mature projects when fit for purpose.

## Success and limits

Success is independently deployable software and reference hardware that interoperate across administrative and technical boundaries, degrade honestly, and remain useful without a mandatory operator. No design can guarantee reachability, secrecy against compromised endpoints, lawful operation in every jurisdiction, infinite storage, interference immunity, or preservation of all semantics during translation.
