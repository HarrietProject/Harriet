# Cross-carrier field validation

**State:** Proposed validation plan. The radio and wired results below are separate prototype tests.

## Portable outage scenario

A traveler in another city chooses a verified contact at home and writes a short check-in during a power or network outage. The portable device seals and saves it locally. When a compatible, permitted relay comes within reach, the device can hand off the sealed note and go offline. Fixed home stations and elevated relays can provide stable contact points, while a portable relay can carry the note to a later contact.

A localized outage may leave a reachable uplink outside the affected area. If both ends remain isolated, the note needs a sequence of radio contacts, physical carriage, or both. The recipient still needs a working endpoint at the last contact. With no available next hop, a custodian waits within the message lifetime and its own resource limits. The receipt may return separately. This is a store, carry, and forward pattern described by [RFC 9171](https://www.rfc-editor.org/rfc/rfc9171.html#section-1).

The traveler needs to see whether the note is saved locally, held by a relay, or delivered. Delivery means the authorized recipient endpoint saved the note and signed a receipt for it. Whether a person has read it remains a separate event. See [Cache and custody](../architecture/cache-and-custody.md).

## Independent routes and existing components

Evaluate alternate routes by what can take them offline. Wired and wireless connections through one router share that router and may share its power and upstream provider. A battery-powered radio relay that can later reach a different network can survive the loss of the original router or uplink. Record shared power, relay, access point, and provider dependencies when claiming a new path improves availability.

Reuse the existing radio and Internet Protocol (IP) profiles and native messaging behavior. Reticulum's LXMF messaging protocol supports encrypted store-and-forward through propagation nodes and can encode an encrypted message in a QR code. Harriet's cross-carrier work is to preserve recipient authorization, policy, custody, and delivery evidence as the selected profile changes. [Reticulum's LXMF documentation](https://reticulum.network/manual/software.html#lxmf)

An adapter may change framing or split and reassemble a sealed object while preserving the same protected bytes and recipient. A shorter version of a message is a separate representation and needs explicit sender authorization. The sender can prepare an essential note for a narrow link and allow fuller detail to follow when capacity permits. Ordinary relays handle those sealed objects within the applicable confidentiality, lifetime, and resource limits. See [Harriet architecture](../../ARCHITECTURE.md).

## What has been tested

See the [prototype evidence](prototype-evidence.md) for scope and verification details.

- A directed bench test with a Raspberry Pi, RAK4631, and T-Deck Plus carried a compact encrypted note over LoRa and returned a recipient-signed receipt. In a delayed run, the Pi retained the original object after the sender exited and sent it after the recipient returned. An operator initiated the final transmission.
- Separate wired tests exercised durable retention across Pi power removal and recipient-signed HTTPS delivery between stations. The phone browser interface in the pilot requires a reachable station. Offline phone origination and unattended relay handoff across radio and IP remain open.
- A desktop survey screened an illustrative fixed link across river and urban terrain. The coarse elevation model flagged obstructions along the direct ray for illustrative rooftop antenna heights. This is a planning result. Actual antenna heights, local clutter, interference, and repeatable delivery in both directions remain unmeasured. A field survey should record attempts and returns at practical antenna heights and check each leg independently before crediting a relay route. [ITU-R P.526 propagation reference](https://www.itu.int/rec/R-REC-P.526)

Field range, energy consumption, and unattended recovery remain unqualified. Record power while waiting, during transmission, and through restart alongside delivery outcomes. See [hardware-in-loop evidence requirements](hardware-in-loop.md).

Use the existing direct LoRa pair to establish a repeatable baseline before adding an elevated relay. Survey native Meshtastic rebroadcast separately from Harriet custody and signed delivery. Fixed radio and IP bridges remain optional paths to assess when a workable site exists.

Direct phone-to-phone via LTE or 5G sidelink remains a research option. Stock handsets' application access and end-to-end field behavior are unverified. See the [dedicated-kit LTE PC5 evaluation](../integrations/lte-pc5.md) and [NIST research on 5G sidelink relay range](https://www.nist.gov/publications/extending-communication-range-5g-nr-multi-hop-ue-ue-relays).

## Proposed acceptance run

1. Verify the normal direct IP path by delivering a baseline note and validating its recipient-signed receipt. Use a fresh message for the fault run.
2. Isolate the sender's direct IP path and keep the relay's onward IP connection unavailable. Transfer a compact note over LoRa to the Pi. Verify that the Pi stores the sealed bytes and custody record durably before acknowledging custody. Power the sender off after that acknowledgment.
3. Later make IP available only from the relay to the recipient. Keep the sender off and require the Pi to resume autonomously. Verify that the authorized endpoint commits the original sealed object, matching its identifier and digest, and signs the delivery receipt.
4. Withhold the first signed receipt after the recipient commits. Require the relay to retry the same object and the recipient to return its stored receipt with a single inbox entry. Allow the sender to reconnect and verify the receipt. A radio acknowledgment or a custody acknowledgment leaves the message unconfirmed.

Keep the recorded object digest, custody and receipt evidence, inbox count, and times for link loss, handoff, and delivery. Confirm from the logs that the relay completed delivery while the sender and its direct path remained unavailable. A pass would establish radio-to-IP handoff, delayed forwarding, and recovery from a lost receipt for the tested configuration. Field distance, portable power budget, and independent return routes require separate evidence.
