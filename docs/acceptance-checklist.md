# PingPlayers review and acceptance checklist

## Decisions requested from PingPlayers

- Confirm the test server's game build, container architecture, glibc and `libstdc++` versions, persistent root, and permitted binary location.
- Provide the approved method to set, preserve, inspect, and remove `LD_PRELOAD` without overwriting other preloads.
- Agree on an owner-only web pairing handshake that lets PingPlayers install unpaired components and ExtinctionOS claim exactly that server without putting a secret in the game console.
- Confirm whether existing PingPlayers voice or other extensions share the process and the required coexistence test order.
- State the policy for outbound HTTPS/WebSocket connections and for a server-local connector process, if one is necessary.
- State the private artifact delivery and signing/checksum requirements for review and eventual automatic installation.
- State whether PingPlayers wants an integration in its panel, marketplace, knowledge base, or another distribution channel, and who implements each side.
- Define security evidence required for commercial approval: binary scan, dependency list, filesystem/network inventory, data-processing information, and incident contact.
- Confirm the permitted native-library opens and system calls under PingPlayers' existing monitoring; ExtinctionOS does not request anti-cheat or monitoring exceptions.

## Test evidence to collect

| Gate | Evidence | Required before listing? |
| --- | --- | --- |
| Baseline | Server starts and players can join before modification; backup and current settings recorded privately. | Yes |
| Binary | Exact version and checksum; x86-64 ELF; host library compatibility; no runtime compilation. | Yes |
| Loader | Preload applied once, survives restart, coexists with existing preloads, and appears in startup diagnostics. | Yes |
| Health | Game starts, map loads, player joins, stability observed, and restart/stop behavior is normal. | Yes |
| Pairing | Owner authorization binds exactly the chosen PingPlayers server; revoke/unpair works. | Yes |
| Bundle onboarding | Customer selects bundle during purchase, PingPlayers installs it, owner pairs only from ExtinctionOS, and no customer file/shell steps are needed. | Yes before bundle launch |
| Read-only telemetry | Presence and supported events are accurate and respect staff/player privacy. | Yes for advertised connected features |
| Controlled actions | Each advertised native action succeeds only for authorized users and is audited. | Yes for that feature |
| Economy | Cross-site/companion claims and rewards are single-award, idempotent, and server-scoped. | Yes for advertised economy features |
| Gameplay rules | Nesting, cross-species chat, group composition, and other multiplayer rules pass explicit multi-player tests; incomplete ones remain disabled. | Yes before advertising each |
| Rollback | Removing ExtinctionOS preload and artifact restores the original server without deleting data. | Yes |
| One-click flow | Install, upgrade, failure rollback, unpair, and uninstall pass on a fresh test container. | Yes before panel launch |

## Known limitations at review time

The feature directory is an inventory, not a certification matrix. Its status labels describe current product configuration and publication state; they do not establish PingPlayers compatibility. In particular, nesting, cross-species chat, and group composition are still marked **In development**, and several features need a connector or multiplayer validation. The initial file-placement and boot result is recorded in [test-panel findings](test-panel-findings.md); loader, connector, pairing, and multiplayer gates remain open. Keep detailed logs and any credentials in a private review channel, not this public repository.
