# PingPlayers installation and one-click integration proposal

This is a **host-review runbook**, not a command to modify a live customer server. PingPlayers must approve the exact paths, startup settings, and package contents. Their infrastructure team stated that the persistent file-manager root is user-owned, the server runs in a container, and a `.so` can be placed either in `TheIsle/Binaries/Linux` or the root directory. They use `LD_PRELOAD`, glibc 2.39, and Linux x86-64; an absolute path beneath `/gameserver/server/` is also possible. The commands below use a placeholder path and must be adapted to the actual container layout.

## Private deliverable — minimum set

1. **Required for native loading:** one approved, versioned x86-64 `ExtinctionOSPlugin.so` file, sent by a private release channel, not this GitHub repository.
2. **Required outside the file upload:** a host-managed `LD_PRELOAD` startup setting that names that exact file. PingPlayers must determine how this is set in its panel/container configuration and how it coexists with existing preloads.
3. **Required after launch:** a private one-time server-pairing process in ExtinctionOS. The current connector pairs host-side; an owner-only web pairing flow needs the host-assisted handshake described in [bundle responsibilities](bundle-responsibilities.md). Pairing tokens and any RCON/SFTP credentials must use approved private storage, never this review repository, game/RCON console, or shared artifact.
4. **Expected for the full game-connected feature set, pending host discovery:** a server-local connector/runtime and possibly a plugin-host component. The existing standalone ExtinctionOS deployment uses more than a `.so`; the complete private artifact list must be finalized from test-server results and approved by PingPlayers. It is **not** bundled or silently installed by this review proposal.

No source tree, C++ compiler, `make`, unrestricted installer script, website code, companion app code, database dump, or customer secrets are needed in the review repository or game-server file upload.

## Controlled manual test (host operator)

Use the PingPlayers test server, confirm an off-server backup, and stop the game process in the panel before changing files. PingPlayers has said reinstall resets to factory defaults; do not treat it as a rollback mechanism.

```sh
# Run inside the approved game container as its normal server user.
# Replace the placeholder only after confirming the actual persistent root.
SERVER_ROOT=/gameserver/server
PLUGIN="$SERVER_ROOT/TheIsle/Binaries/Linux/ExtinctionOSPlugin.so"

test -d "$SERVER_ROOT/TheIsle/Binaries/Linux" || exit 1
test -f "$PLUGIN" || exit 1
file "$PLUGIN"                         # ELF 64-bit x86-64 shared object
sha256sum "$PLUGIN"                    # compare with private release manifest
readelf -d "$PLUGIN" | grep NEEDED    # review dependencies
readelf --version-info "$PLUGIN" | grep -E 'GLIBC_|GLIBCXX_' | sort -u
```

Upload the approved binary by PingPlayers file manager or SFTP to the chosen persistent path. These commands validate the uploaded file; they do **not** download or execute code. The host then sets `LD_PRELOAD` to the absolute plugin path in its controlled startup configuration, preserving any existing preload entries in an approved order. Do not put it into an unreviewed `Game.ini` key or append a second ambiguous loader setting. Restart from the PingPlayers panel, inspect startup logs and game health, then complete the private pairing in ExtinctionOS.

On the supplied test server, SFTP exposes the game folder as `/server/TheIsle/Binaries/Linux`. PingPlayers must confirm its corresponding path **inside the game process container** before setting the loader. The email's `/gameserver/server/` path is the expected container-root mapping, not something SFTP alone proves.

If PingPlayers runs a provisioning job with shell access, this is the **command template** after it has received a private, approved release and stopped the server:

```sh
set -eu
SERVER_ROOT=/gameserver/server
STAGED_PLUGIN=/path/to/private/staging/ExtinctionOSPlugin.so
PLUGIN="$SERVER_ROOT/TheIsle/Binaries/Linux/ExtinctionOSPlugin.so"
EXPECTED_SHA256='<digest from private signed release manifest>'

test -f "$STAGED_PLUGIN"
test -d "$SERVER_ROOT/TheIsle/Binaries/Linux"
test "$(sha256sum "$STAGED_PLUGIN" | cut -d ' ' -f 1)" = "$EXPECTED_SHA256"
file "$STAGED_PLUGIN"
readelf -d "$STAGED_PLUGIN" | grep NEEDED
install -m 0644 "$STAGED_PLUGIN" "$PLUGIN"
test "$(sha256sum "$PLUGIN" | cut -d ' ' -f 1)" = "$EXPECTED_SHA256"
```

Use the existing game-user identity for this job; do not run the game as root. The operator must replace the staging path and digest with values supplied privately. The host-owned startup configuration then needs the equivalent of `LD_PRELOAD=<all previously approved preload entries>:<absolute PLUGIN path>`, with the exact ordering validated against other plugins and anti-cheat policy. PingPlayers should apply that setting through its panel/orchestrator, **not** by asking customers to run a shell command. The launch command itself remains the host's existing Evrima launch command; this repository does not provide or replace it.

If a separate connector or plugin host is approved, PingPlayers must likewise install its **private compiled package**, provision a restricted private configuration, supervise it with the container's supported process manager, and test its health. The artifact filename, process command, and outbound destinations are deliberately not fabricated here; they require the private release manifest and PingPlayers engineering sign-off.

If PingPlayers selects the root instead, the same steps apply with `PLUGIN=/gameserver/server/ExtinctionOSPlugin.so`. Do not use both locations at once.

## Removal / rollback

Stop the game server. Remove only the ExtinctionOS entry from the host-managed `LD_PRELOAD` setting, leaving other entries unchanged. Restore the previously saved binary or remove the ExtinctionOS binary if there was none. Restart and verify the unmodified game server reaches a healthy state. Preserve logs and backup copies for investigation. Do not invoke a factory reinstall unless the owner explicitly accepts the resulting data reset.

## One-click customer flow after approval

1. PingPlayers offers an **opt-in ExtinctionOS bundle at server purchase** for supported Evrima builds and explains the native preload and external-account connection.
2. PingPlayers installs a version-pinned private binary to the persistent root, verifies its checksum, and applies the approved startup variable while preserving other preloads.
3. PingPlayers restarts and checks game health; on failure it automatically restores the prior startup setting and artifact.
4. The owner opens ExtinctionOS, creates or selects a server, and completes a short-lived pairing flow. This is the customer's only installation-related step. The panel passes no long-lived secret in a public URL or repository.
5. ExtinctionOS reports connector and feature readiness per server. Website-only tools may be available before game-connected tools; incomplete or unvalidated features remain visibly unavailable.
6. Updating or uninstalling repeats the backup, checksum, restart, health-check, and rollback sequence.

This needs PingPlayers' engineering participation. An SFTP upload alone cannot create a safe panel-native one-click installation or guarantee every ExtinctionOS feature works inside their container.

See [bundle responsibilities](bundle-responsibilities.md) for the complete purchase-time task split and automation contract.
