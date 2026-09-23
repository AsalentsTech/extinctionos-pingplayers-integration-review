# Private release manifest template

This template lists what PingPlayers should receive through a **private, authenticated channel** after review. Do not fill it with secrets or publish an actual artifact URL in this repository.

| Field | Value to provide privately |
| --- | --- |
| Release version and build date | TBD |
| Supported Evrima build/container image | TBD |
| `ExtinctionOSPlugin.so` SHA-256, size, ELF architecture | TBD |
| Required glibc and `libstdc++` symbol versions | TBD |
| Runtime file read/write paths | TBD |
| Outbound domains, protocols, and ports | TBD |
| Required environment variables (names only) | TBD |
| Connector/plugin-host artifacts, checksums, and process commands (if approved) | TBD |
| Health-check command or endpoint | TBD |
| Install and removal test result | TBD |
| Compatibility with other PingPlayers preloads and voice | TBD |
| Vulnerability scan and debug-symbol review | TBD |

This GitHub review repository contains no release payload. A host should not fetch a mutable “latest” binary or compile source on customer game containers.
