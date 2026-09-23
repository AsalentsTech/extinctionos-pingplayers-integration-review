# PingPlayers bundle responsibilities

## Intended purchase and onboarding experience

1. A customer orders a supported PingPlayers *The Isle: Evrima* server and selects the optional ExtinctionOS bundle.
2. PingPlayers provisions the server and installs the approved, private ExtinctionOS game-side release. The customer is **not** asked to upload a `.so`, run a command, edit startup variables, or compile software.
3. PingPlayers verifies the game starts with the bundle and exposes only a short-lived, one-time pairing path or code in the owner's private panel.
4. The customer signs in to ExtinctionOS, selects **Add server**, and pairs the server. The customer then chooses features and permissions inside ExtinctionOS.
5. PingPlayers and ExtinctionOS exchange only the minimum private provisioning status and server identity needed to support install, upgrade, unpair, and removal.

## PingPlayers engineering tasks

1. **Compatibility:** pin the supported game/container versions; verify Linux x86-64, glibc 2.39, C++ runtime, and the private binary's dependency report.
2. **Artifact channel:** agree on a private release location and per-version SHA-256 or signature verification. This review repository must never become the binary download endpoint.
3. **Game-side files:** install the approved `ExtinctionOSPlugin.so` into a persistent, user-owned location. A full-feature release may also need a server-local connector and/or plugin host. PingPlayers and ExtinctionOS must agree on those artifacts and their supervision after test-server discovery; a `.so` alone is not represented as the entire platform.
4. **Process loader:** configure the approved absolute plugin path in the game startup `LD_PRELOAD` setting, preserving other preload entries and host anti-cheat rules. Ensure settings survive ordinary restarts and updates.
5. **Runtime service:** if the connector is required, run it under the same restricted server identity or another approved service identity, with only necessary filesystem and outbound-network access. Provide a health indicator and stop/restart lifecycle. Do not build source on customer containers.
6. **Private pairing:** implement a random, short-lived, single-use pairing claim bound to the purchased server and owner. The current ExtinctionOS connector installer uses a host-side code; the proposed owner-only web pairing requires a new private host-assisted handshake. Do not place a reusable secret in a public URL, GitHub repo, game/RCON console, game command line, or downloadable client bundle.
7. **Panel status:** display installed version, healthy/unhealthy state, pairing state, upgrade availability, and removal action to the owner. The ExtinctionOS account remains the place to configure features.
8. **Lifecycle:** on game update, validate compatibility before re-enabling the bundle; on failed install/start, restore the prior preload and artifact. On cancellation, unpair/revoke the connector, remove only ExtinctionOS files/settings, and leave game data intact.
9. **Security and support:** approve filesystem and egress inventory, coexistence with existing host mods/voice, log retention, incident process, and responsibility split before customer distribution.

## ExtinctionOS responsibilities

- Supply versioned, privately delivered, reviewable binary artifacts and dependency/checksum manifest; no customer-runtime compiler or source install.
- Provide the pairing endpoint and owner UI, enforce account and server permissions, expose connector health, and keep website/companion data server-scoped.
- Mark each feature's readiness accurately; do not expose game-connected features until its live capability and test gate pass.
- Provide release notes, compatibility guidance, safe unpair/revoke behavior, and a support route for integration failures.

## Customer responsibilities

The target flow is: the owner selects the bundle during PingPlayers purchase, then signs in to ExtinctionOS and pairs that server. They may configure optional features and invite staff there. They should not need shell, file-transfer, or startup access for ordinary use. This streamlined pairing requires the host-assisted bootstrap in item 6; it is not claimed to exist yet.

## Host automation contract to agree

PingPlayers needs a private, idempotent job roughly equivalent to: stop server → record prior settings and artifact → fetch approved pinned release → verify signature/checksum and ELF dependencies → install with normal game-user ownership → apply startup preload without disturbing other entries → start and health-check → expose pairing claim → report success. Every failed step must reverse only the changes made by that job. The exact panel API, installer execution environment, connector supervisor, and artifact endpoint remain to be specified with PingPlayers; none should be invented from the current email exchange.

For ExtinctionOS, use a private owner-only claim rather than printing a reusable credential in public or retained game logs.
