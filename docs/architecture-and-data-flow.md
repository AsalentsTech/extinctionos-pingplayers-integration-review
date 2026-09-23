# Architecture and data flow

## Components

1. **PingPlayers game container:** runs the dedicated *The Isle: Evrima* server. A host-approved, version-pinned `ExtinctionOSPlugin.so` may be preloaded into that process. The file is private delivery material, not stored in this repository.
2. **Server-local connector:** pairs the game-server instance with ExtinctionOS and mediates supported telemetry and requested game actions. The connector must be scoped to one owner-authorized server; it must not expose RCON or local game files to public clients.
3. **ExtinctionOS service:** stores server configuration, account links, entitlements, community content, economy records, and audit events. It authorizes actions before forwarding supported requests to the paired server.
4. **Owner/staff web console:** lets authorized people configure rules and review the selected server. Staff permissions are role-scoped.
5. **Community website and companion:** show published content and eligible player actions for linked accounts. They do not receive server credentials or direct shell access.

```text
Owner/staff browser ─┐
Community/companion ├─ HTTPS → ExtinctionOS service ─ authenticated pairing → server-local connector
                    │                                             │
                    └─ account/role checks                         └─ supported game events/actions
                                                               PingPlayers game container
```

## Trust boundaries

- The owner opts in and pairs an individual server. Being a PingPlayers customer alone must not enroll a server.
- Authentication and authorization are checked in ExtinctionOS and again at the connector boundary where applicable. A community-page action is not a direct game command.
- Private values (SFTP, RCON, Discord tokens, account secrets) stay outside this repository and are not embedded in the shared library or customer-facing UI.
- Only feature-specific, necessary data should cross the boundary: for example linked player identity and eligible game state for a requested action. Staff-only location and identity data must remain access-controlled.
- Economy and reward decisions must be authoritative on the service side; the browser/companion may display state but may not mint rewards locally.
- A host restart or compatibility failure must leave the game server recoverable by disabling the loader and restoring the previous binary/configuration.

## Boundaries to verify on the test server

The current standalone installation has not yet established that the full connector, all native hooks, and all game-facing features work under PingPlayers' container image. The test must verify the shared library's ELF dependencies, loader behavior, outbound connectivity, file permissions, event capture, and command delivery. See the [acceptance checklist](acceptance-checklist.md).
