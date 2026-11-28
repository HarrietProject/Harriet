# Prototype evidence

**State:** Tested prototypes with bounded results. See the [project state](../../PROJECT_STATE.md) for overall maturity.

## Native Reticulum baseline

A component bench used separate sender, recipient, and propagation-relay
processes over loopback. Direct LXMF delivery matched the expected message hashes
and validated the sender signature. A second message survived a graceful propagation
relay restart and was retrieved by its recipient after the sender shut down.
Relay acceptance and final receipt are distinct. The bench did not establish a
final receipt reaching the stopped sender or qualify a radio profile.

## Prepared messages and custody

The prepared-message prototype exercised separate sender, Base, and recipient identities using Reticulum's native LXMF messaging over Transmission Control Protocol (TCP). The sender signed the policy and encrypted alternatives to the intended recipient. The Base committed the sealed offer and recovered it after a process exit. It selected a sender-authorized representation within the configured byte allowance and refused an allowance below the minimum. The recipient committed the protected packet before signing application evidence. A separate sealed file returned the original evidence to the Base. Importing it twice recorded delivery once.

The wired Raspberry Pi bench ran a similar exchange across two hosts. The Base retained the offer while the originating process and station directory were unavailable. It remained in flight until the operator returned the sealed receipt file. An initial clock preflight blocked the run. The later successful run used explicit bench timing guards while retaining the application timestamp checks.

The operator reported removing power from the Pi after custody was committed. The recovery record confirms that the Pi booted again with the original custody record and no prior transmission claim. An operator initiated forwarding, and the recipient's signed evidence completed the original obligation. The powered-off duration and long-term retention remain unmeasured.

## Compact radio bench

A directed short-range LoRa round trip carried a compact encrypted object and returned the recipient's signature. The recipient committed the object before submitting the receipt, and the sender-side endpoint verified the signature. Two earlier attempts failed. A separate delayed run retained the original object after the sender process exited. After the recipient radio returned, the operator started transmission and verified the returned receipt. These runs provide bench evidence for the tested pair. Repeatable field range, energy use, and unattended recovery remain open.

The range-preparation controller passed software checks against the same compact test objects. Field measurements for that controller are pending.

## Station pilot

The private Station pilot ran on Windows and Apple Silicon macOS. Each host kept its own identity. The pilot exchanged signed public contact cards, displayed fingerprint checks, and required recipients to approve reciprocal contact requests. In a live macOS-to-Windows HTTPS run, the original encrypted note was retried after contact approval. The recipient saved the note and the sender verified its signature. Controlled software checks exercised lost-receipt retry, duplicate suppression, and recovery after restart.

One handset opened the Station's browser interface over local Wi-Fi. Pairing on a second handset remains unresolved. The browser interface uses its reachable host's identity and storage. Independent mobile origination and Linux and Pi installation through the Station entry point still need verification.

## Offline verification

On November 28, 2026, 122 Python tests passed in scratch copies of the prototypes. The run covered 77 prepared-message tests, 19 Pi bench tests using generated objects and mocked radio input and output, and 26 range-preparation tests. The prepared-message count excludes four native LXMF integration tests that open loopback connections. The range-preparation check also verified the source hashes for the compact bench modules. The Station 0.5.5 installer archive matched its recorded SHA-256 digest. Every entry in the release manifest passed its integrity check, and all 30 files outside the bundled Python dependencies matched the working source tree.

These checks exercised software and artifact integrity. The physical observations above come from earlier runs. See the [cross-carrier field-validation plan](cross-carrier-field-validation.md) for the proposed radio-to-Internet Protocol (IP) handoff, disrupted return path, and recovery tests.
