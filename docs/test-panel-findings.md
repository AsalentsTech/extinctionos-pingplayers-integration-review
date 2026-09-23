# Test-server panel findings and initial binary staging

These observations are from the supplied PingPlayers *The Isle: Evrima* test-server panel on 23 September 2026. The panel survey was read-only; the later controlled staging test is recorded separately below.

| Panel area | Observed capability | Integration consequence |
| --- | --- | --- |
| Server overview | Running state, resource usage, allocated game/RCON/file-transfer ports, auto-boot and update-on-boot controls. | Useful for baseline/health checks; it does not prove custom loader access. |
| Basic Settings | Native game settings and RCON enablement/password are exposed; search found no `LD_PRELOAD` field. | Keep RCON values private. Host engineering must provide loader configuration. |
| Config Manager | `Game.ini` and `Engine.ini` templates are available; templates are rewritten at start/restart. Config Manager disables `TheIsleServer.sh` editing, although the file manager can open the script. Its timestamp advanced during the manual game-file sync. | A user edit to the game launch script is not a verified, durable preload hook. Ask PingPlayers to set the loader in its controlled startup configuration instead. |
| Console | Displays game, RCON, and app logs and offers a command input. | This is not a Linux shell or a private connector-pairing form. Do not enter pairing codes or secrets; commands/logs may be retained. |
| File Manager / SFTP | Persistent server directory and `TheIsle/Binaries/Linux` are accessible. | A binary can be staged there, but upload alone does not load it. |
| Task Manager | Can schedule operations and select configuration overrides. | It is not a substitute for a host-managed preload and connector supervisor. |
| Logs | Exposes server log categories. | Can support post-install health review; scrub secrets before sharing evidence. |

The FTP/SFTP details page and knowledge base are available. Credentials, test-server address, account identity, and allocated ports are intentionally omitted from this repository. PingPlayers' infrastructure email is the source for their stated `LD_PRELOAD`, architecture, glibc, and container-root behavior.

## Controlled staging result

With the test server stopped and no players online, a stripped Linux x86-64 `ExtinctionOSPlugin.so` was uploaded only to `TheIsle/Binaries/Linux/ExtinctionOSPlugin.so`. The game was then restarted through the panel. PingPlayers reported the server running again on game version `0.21.784`; its app logs recorded a successful file sync and game start. Auto Boot was restored after the test. The game-side binary remains on the test server for PingPlayers engineering inspection. No source tree, installer archive, credentials, or connector runtime was uploaded.

**This is a file-placement and boot test, not a successful integration test.** The panel exposes neither the effective process `LD_PRELOAD` nor the game's mapped libraries. No ExtinctionOS load confirmation appeared in the available startup logs, and the separate ExtinctionOS server profile still reports its connector waiting. PingPlayers engineering needs to confirm the approved host-side loader configuration, inspect whether the library is actually mapped, and provide the safe way to run or supervise the private connector before pairing and gameplay tests can proceed.

The visible Steam-runtime entry-point script temporarily clears and later restores `LD_PRELOAD` around its helper work, confirming that startup environment handling belongs to the host launch chain. We did not modify that third-party entry point. Neither the game/RCON console nor a downloadable connector file is an appropriate place to embed a live pairing code.

The panel also exposes separate **Auto Update** and **Update on Boot** controls. Auto Update was off. For a controlled test, Update on Boot was turned off, the original `TheIsleServer.sh` was backed up, and an otherwise identical copy with a single harmless startup marker was uploaded while the empty game server was stopped. After restart, the game reached Running, but PingPlayers replaced the edited script with the original 279-byte script despite Update on Boot being off; the post-boot file matched the backup byte-for-byte. The staged `.so` remained in place, while ExtinctionOS still showed the connector waiting. No marker appeared in the available logs. **Update on Boot remains off on this dedicated test server for follow-up diagnostics.** This falsifies the specific persistent launch-script edit as an autoload method in the current setup; it does not prove that PingPlayers cannot supply a supported host-side loader setting. No startup file remains modified.

## Pairing UX clarification

ExtinctionOS currently issues a short-lived code for its server-local connector installer. That installer expects an operating-system context and is not a game-console command. The desired customer experience—PingPlayers installs the bundle, owner pairs only in ExtinctionOS—requires a **new host-assisted private bootstrap handshake** or an approved private PingPlayers panel action. Until implemented, an operator must pair the connector through a secure host-side channel. Do not paste a pairing code into the game/RCON console.
