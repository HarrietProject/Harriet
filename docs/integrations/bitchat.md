# Bitchat proximity messaging evaluation

**State:** Watch. Native parallel messaging is a candidate for a pinned-build test.

The upstream Bitchat projects for Apple platforms and Android describe Bluetooth Low Energy mesh
messaging and an optional internet path through Nostr. Native proximity
messaging could help people using ordinary phones alongside Harriet radio
profiles. Treat the native application as a separate payload with its own
identities, permissions, and delivery semantics. No Harriet or Reticulum packet
bearer, bridge, or identity translation has been verified. See the
[Apple project](https://github.com/permissionlesstech/bitchat) and
[Android project](https://github.com/permissionlesstech/bitchat-android).

## Proposed comparison

1. Pin the official builds, OS versions, and applicable licenses. Confirm the
   intended private-message mode and its peer verification steps.
2. Disable Wi-Fi and cellular connectivity on both test phones and enable
   Bluetooth. Exchange a synthetic private message and record the observed
   endpoint and application evidence.
3. Repeat with the recipient locked, after disconnect and reconnect, and in
   both directions. Record visibility, delivery behavior, timing, and resource
   cost where measured.
4. Add a second independent platform or a relay only after the initial pair
   behaves repeatably. Assess any optional internet path separately with
   explicit operator permission.

Check iOS and Android interoperability, background behavior, and any supported
headless endpoint before proposing a profile. Review the exact shipped license
and dependency obligations before redistribution. Keep ordinary Harriet relays
opaque and preserve the [delivery evidence model](../architecture/cache-and-custody.md).
