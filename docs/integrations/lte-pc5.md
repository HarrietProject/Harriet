# LTE PC5 direct-link evaluation

**State:** Watch. Dedicated-kit bench proposed. Stock handset support and field delivery remain unverified.

## Scope

LTE PC5 sidelink is a candidate direct bearer for a sealed Harriet object.
Ordinary carrier LTE depends on network infrastructure. A direct test needs
matched devices and a host interface that can exchange arbitrary binary
payloads in both directions without a cellular base station. Confirm the
specific kit's operating authority and lab setup before enabling RF. Treat
license, SDK access, device support, and lawful deployment as qualification
questions.

New Radio (NR) sidelink and multihop user-equipment relay research inform future
work. Their results do not establish an LTE PC5 payload interface, a stock
phone path, or Harriet delivery. See the
[NIST NR sidelink relay study](https://www.nist.gov/publications/extending-communication-range-5g-nr-multi-hop-ue-ue-relays).

## Proposed bench sequence

1. Pin both kit, firmware, and host SDK versions. Record their supported
   operating mode, configuration, payload ceiling, and use restrictions.
   Set up in an authorized lab environment.
2. Exchange two-way synthetic binary frames with the production cellular
   network and unrelated IP paths unavailable. Log each direction,
   application payload size, and observed loss. Stop if arbitrary host data
   or operation without a base station cannot be established.
3. Send one sealed Harriet note to the authorized endpoint. Require original
   object identifier and digest, a durable inbox write, and a recipient signature
   over that exact object. Return the signed receipt through the qualified
   reverse path. Link-layer acknowledgments provide link evidence only.
4. Repeat with a withheld receipt and duplicate retry. Verify one recipient
   inbox entry and an authenticated receipt recovered by the sender. Record
   failure conditions, timing, and measured power if metering is available.

Record the result as evidence for the named pair and authorized configuration.
Route distance, stock handset application access, multihop, coexistence, and
energy suitability need separate evidence. See
[cross-carrier field validation](../development/cross-carrier-field-validation.md).
