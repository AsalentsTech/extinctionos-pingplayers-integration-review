# Security review and disclosures

## Why this requires host review

`LD_PRELOAD` loads a native shared library into the dedicated game process. That is a high-trust integration even when the delivery is binary-only: it can affect process stability and inherits the process's filesystem and network privileges. PingPlayers should treat it as a native extension, inspect the release artifact, and approve the exact startup configuration before a customer-facing listing.

## Proposed controls

| Area | Expected control / review evidence |
| --- | --- |
| Artifact provenance | Version-pinned x86-64 ELF, SHA-256 digest, release notes, and dependency report delivered privately. No `make`, compiler, or source tree needed at customer runtime. |
| Installation | Stop server first; install only the approved `.so` under the persistent server root; set permissions for the game user; configure one explicit preload path; restart and verify. |
| Least privilege | Run with the existing game user, not root. Limit writable paths and outbound destinations to those needed by the approved connector. |
| Secrets | Provision pairing and connection secrets through host-approved private settings; never through public GitHub, filenames, launch arguments visible to players, or hard-coded binary strings. |
| Actions | Owner opt-in, per-server pairing, permission checks, and server-side validation before game-affecting commands. |
| Data | Minimize collection, restrict staff-only location/identity information, and keep audit records for changes and rewards. |
| Compatibility | Test against PingPlayers' glibc 2.39 image, its `libstdc++` version, current Evrima build, and any other preloaded libraries. Compatibility is not assumed from a successful load alone. |
| Recovery | Retain a copy of overwritten files and settings; remove the preload and restore the previous artifact if health checks fail. PingPlayers advised that it has no rollback feature and reinstall resets a server. |
| Updates | Explicit version, checksum, change notes, health check, and controlled restart. No silent binary replacement. |

## What is not in this repository

No native source, implementation scripts, customer or test-server credentials, server IP addresses, private endpoints, production data, or compiled plugin are published here. The contents describe behavior and review requirements, not sensitive implementation details.

## Open disclosures for PingPlayers engineering

Before approval, ExtinctionOS must provide a **private** artifact manifest, exact runtime dependencies, requested filesystem paths, outbound domains/ports, telemetry categories, retention rules, and a reproducible test result. PingPlayers should be able to inspect the binary and reject unexpected system calls, processes, downloads, writes, or network destinations. The final release must be checked for unintended embedded secrets and debug symbols. This document does not claim those checks have already passed.

## Known standalone behavior and proposed PingPlayers boundary

The existing ExtinctionOS deployment uses three distinct game-side concerns: a native shared library, a local native/plugin host, and a server-local connector. The current standalone installer is source-based and systemd-specific; it is **not** the proposed PingPlayers deliverable. For PingPlayers, these parts must become privately distributed, precompiled, reviewed artifacts or an equivalent host-approved package. Removing one part can reduce the available features; installing only the `.so` must not be advertised as complete integration.

The existing connector's intended outbound application destination is `https://extinctionos.com` over HTTPS. It is designed to initiate connections outward rather than require another public inbound game-server port. The game-side interface can use local game logs, local command/result files, local heartbeat/state files, and local RCON where supported. PingPlayers must approve the final path and network inventory for its container before deployment; an observed destination in the existing installer is not a final network allowlist.

Depending on enabled features, the platform may process server identity, linked Steam/Discord account identifiers, player presence/species/activity, owner-configured rules, staff actions, community balances and reward history, and optional staff-only map/location data. Player-facing pages must be scoped to the linked player and server; exact locations and private identifiers must not become public. The detailed event-field, retention, deletion, and subprocessor inventory remains an acceptance deliverable, not an unsupported claim in this document.

The currently running private plugin on the standalone Linux server is an ELF x86-64 shared object and references glibc symbols through `GLIBC_2.38` and C++ runtime symbols through `GLIBCXX_3.4.31`. PingPlayers stated glibc 2.39; that alone does **not** establish C++ runtime compatibility, game-build compatibility, or approval of the binary. A release-candidate manifest and an actual container load test are required.

PingPlayers has said its wrapper and Easy Anti-Cheat do not categorically block preloaded libraries, but it records opened libraries and system calls. ExtinctionOS welcomes this review. We do not ask PingPlayers to disable monitoring, anti-cheat, or loader protections. Any unexpected library load or syscall should fail the acceptance gate until explained.

Security concerns can be raised through the ExtinctionOS owner's existing PingPlayers integration conversation; no public credentials are required.
