# ExtinctionOS × PingPlayers integration review

**Purpose:** a public, source-free review package for PingPlayers' engineering and operations teams to assess an optional ExtinctionOS integration for hosted *The Isle: Evrima* servers. Sensitive release artifacts and credentials are kept out of this repository.

ExtinctionOS is a separate server-management and community platform. A server owner pairs a game server with their ExtinctionOS account, configures only the features they want, and gives staff role-scoped access. Players can use the linked community website and companion app for eligible community features. The proposed commercial flow is a PingPlayers server purchase with an optional ExtinctionOS bundle: PingPlayers installs and operates the approved game-side components; the customer's only setup step is to connect and pair that server from their ExtinctionOS account. PingPlayers would host the game process; ExtinctionOS would remain responsible for its own application, account, and integration services. This is a proposal, not a claim of PingPlayers endorsement or a completed one-click integration.

The public [ExtinctionOS product page](https://extinctionos.com/welcome) provides the product tour, operating model, and feature context; this repository is the technical review companion.

## What PingPlayers can review here

- [Feature directory](docs/feature-directory.md): title, purpose, operating path, audience, and current readiness for every feature in the ExtinctionOS catalog.
- [Architecture and data flow](docs/architecture-and-data-flow.md): trust boundaries and the proposed server-pairing model.
- [Security review](docs/security-review.md): permissions, native-library risks, data handling, and outstanding verification.
- [Installation runbook](docs/pingplayers-installation.md): proposed minimal files, host commands, validation, removal, and one-click integration contract.
- [Bundle responsibilities](docs/bundle-responsibilities.md): precisely what PingPlayers must provision at purchase time and what the customer does at pairing.
- [Private release manifest template](docs/private-release-manifest-template.md): the binary and runtime facts PingPlayers should receive out of band after review.
- [Test-panel findings](docs/test-panel-findings.md): observed capabilities and limits of the supplied PingPlayers test server, without exposing its credentials or address.
- [Acceptance checklist](docs/acceptance-checklist.md): the evidence needed before listing the integration for customers.

## Scope and readiness

The catalog contains web-only tools, game-connected tools, and features still in development or awaiting multiplayer validation. A configured page is **not** proof of supported game delivery on PingPlayers. The proposed test starts with a private test server and a host-approved loader configuration. No production customer installation or marketplace listing should occur until the checklist is satisfied.

The native game component is a Linux x86-64 shared library named `ExtinctionOSPlugin.so` in the current build. PingPlayers has stated that its game containers use `LD_PRELOAD`, glibc 2.39, and a persistent user-owned server root. The review repository intentionally contains **no source code, build scripts, binary, credentials, customer records, or production configuration**. A versioned binary and its checksum would be delivered through a separate private release channel only after security and compatibility review.

## Review request

Please confirm the approved loader path and startup-variable mechanism, whether the plugin can coexist with other preloads, what runtime network and filesystem access is allowed, how PingPlayers wants to receive a private binary, and what evidence is required for a one-click listing. The exact questions and test gates are in the [acceptance checklist](docs/acceptance-checklist.md).

This documentation is provided for integration evaluation. It does not grant rights to redistribute proprietary runtime components.
