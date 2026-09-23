# ExtinctionOS feature directory

This inventory covers 118 catalog entries as of 23 September 2026. Some names appear twice because an owner configuration page and a player-facing page are separate surfaces. These are non-sensitive functional descriptions, not source-code disclosures or claims that every game hook works on PingPlayers.

**Readiness key:** “Configured feature” means a product setting or interface exists, not that native game delivery is proven on PingPlayers. “Connector required” and “Multiplayer validation pending” require corresponding live tests. “In development” is not advertised as working. “Owner-published page” is visible only when the owner publishes it.

## Community Presence

### Community Field Network (owner/staff)

- **Purpose:** Build a public server website included with your ExtinctionOS subscription. No domain purchase or DNS setup is required.
- **How it works:** The owner selects and publishes community pages for one server; eligible visitors use that server-branded site.
- **Catalog status:** Configured feature

### Custom pages (owner/staff)

- **Purpose:** Build public community tabs. Preview updates as you type. Changes go live only when saved and published.
- **How it works:** The owner edits a page, previews it, then saves and publishes it; drafts are not public.
- **Catalog status:** Configured feature

### Discord bot (owner/staff)

- **Purpose:** Connect one bot per game server for player login, role checks, alerts, and Discord-enabled tools.
- **How it works:** An owner authorizes a bot for one server; saved role and channel settings control enabled Discord functions.
- **Catalog status:** Configured feature

### Discord heatmap (owner/staff)

- **Purpose:** Share a privacy-safe view of activity across Gateway. ExtinctionOS updates one Discord message on your schedule, without names or exact player pins.
- **How it works:** An aggregate activity message is updated on a chosen schedule without player names or exact pins.
- **Catalog status:** Configured feature

### Mod panel (owner/staff)

- **Purpose:** Build role-protected Discord control panels for moderation, players, world cleanup and server operations.
- **How it works:** Authorized Discord roles see only the moderation and operations actions granted to them.
- **Catalog status:** Configured feature

### Broadcast Verification (owner/staff)

- **Purpose:** Let Streamer-role members manage their own channels, then approve exactly who may be monitored and announced.
- **How it works:** Streamers submit channels; staff explicitly approve monitoring and announcements.
- **Catalog status:** Configured feature

### Community Bulletins (owner/staff)

- **Purpose:** Publish time-limited notices on the community website with ordering, previews, and optional member dismissal.
- **How it works:** The owner sets notice text and timing, previews it, then publishes it to the community surface.
- **Catalog status:** Configured feature

### Website settings (owner/staff)

- **Purpose:** Manage appearance, wording, CSS and public-page layout. Discord credentials are managed in the dedicated Discord Bot tab.
- **How it works:** The owner saves branding and page presentation for the selected community site.
- **Catalog status:** Configured feature

### Welcome messages (owner/staff)

- **Purpose:** Configure a private welcome shown to a player when they join and test delivery on a selected dinosaur.
- **How it works:** The owner saves a greeting and selects delivery style; the join event triggers private delivery if the connector supports it.
- **Catalog status:** Configured feature

### Your name, your server (owner/staff)

- **Purpose:** Set a custom chat name for one Steam ID on the selected server.
- **How it works:** The owner assigns a chat display name to one Steam account on one server.
- **Catalog status:** Configured feature

## Community Economy

### Predictions (owner/staff)

- **Purpose:** Create fair event markets, accept Souls wagers, then settle winners or refund everyone.
- **How it works:** The owner defines and settles a market; eligible players place Souls wagers and the service books payouts or refunds.
- **Catalog status:** Configured feature

### Reward Crates (owner/staff)

- **Purpose:** Build reward cases with controlled prices, access rules, rarity weights, and opening limits.
- **How it works:** The owner publishes a weighted reward pool and limits; openings use server-side eligibility, payment, and reward records.
- **Catalog status:** Configured feature

### Community Games (owner/staff)

- **Purpose:** Configure games, safe bet limits, win odds, and player payouts for the active server.
- **How it works:** The owner sets game rules and bet limits; the service checks balances and records each outcome and payout.
- **Catalog status:** Configured feature

### Community Credits (owner/staff)

- **Purpose:** Configure player earnings, daily claims, role rewards, and economy balances.
- **How it works:** The owner configures earning and claim rules; balances and transactions are maintained server-side.
- **Catalog status:** Configured feature

### Species Market (owner/staff)

- **Purpose:** Choose who may use the shop and configure dinosaur sales, marketplace listings, and tokens.
- **How it works:** The owner publishes inventory and prices; purchases need balance and eligibility checks before verified game delivery.
- **Catalog status:** Configured feature

### Dinosaur Reserve (owner/staff)

- **Purpose:** Dinos parked by players. Edit values to apply on the next verified restore.
- **How it works:** Players request park or activate; the service checks ownership and limits, then requires a compatible game-state connector.
- **Catalog status:** Connector required

### Appearance Market (owner/staff)

- **Purpose:** Design skins players can obtain with currency and control who may use them.
- **How it works:** The owner publishes skins; player purchase and application require entitlement checks and supported in-game application.
- **Catalog status:** Configured feature

### Account Ledger (owner/staff)

- **Purpose:** Review supporter purchases, automatic rewards, and manual benefit delivery.
- **How it works:** Purchases, claims, and adjustments are recorded centrally; each player sees only their own account history.
- **Catalog status:** Configured feature

### Predictions (player)

- **Purpose:** Offer the owner-published prediction/betting experience using the configured community economy and settlement rules.
- **How it works:** The owner defines and settles a market; eligible players place Souls wagers and the service books payouts or refunds.
- **Catalog status:** Owner-published page

### Reward Crates (player)

- **Purpose:** Offer owner-configured reward cases with clear eligibility and community-economy integration.
- **How it works:** The owner publishes a weighted reward pool and limits; openings use server-side eligibility, payment, and reward records.
- **Catalog status:** Owner-published page

### Community Games (player)

- **Purpose:** Offer owner-configured Community Games experiences using community currency and guarded game rules, rather than a separate unmanaged balance.
- **How it works:** The owner sets game rules and bet limits; the service checks balances and records each outcome and payout.
- **Catalog status:** Owner-published page

### Species Market (player)

- **Purpose:** Offer owner-configured dinosaur purchases with costs and eligibility checked against the community economy and verified game delivery.
- **How it works:** The owner publishes inventory and prices; purchases need balance and eligibility checks before verified game delivery.
- **Catalog status:** Connector required

### Dinosaur Reserve (player)

- **Purpose:** Let linked players review their parked dinosaurs and use guarded Park/Activate workflows when the matching game runtime is online. Owner limits control eligibility and storage.
- **How it works:** Players request park or activate; the service checks ownership and limits, then requires a compatible game-state connector.
- **Catalog status:** Connector required

### Appearance Market (player)

- **Purpose:** Give players a place to preview, purchase and manage owner-published skins, with application constrained by supported game integration.
- **How it works:** The owner publishes skins; player purchase and application require entitlement checks and supported in-game application.
- **Catalog status:** Connector required

### subscriptions (player)

- **Purpose:** Show the community owner’s published player subscription store, separate from ExtinctionOS platform subscriptions. Automatic benefits depend on configured delivery integrations.
- **How it works:** The owner publishes this server-scoped page; linked players see permitted content and actions. Game data requires its matching integration.
- **Catalog status:** Owner-published page

## Island Rules

### Developer Gateway (owner/staff)

- **Purpose:** Create scoped API keys for trusted ExtinctionOS integrations.
- **How it works:** An owner issues scoped integration credentials and can revoke them without sharing the main account login.
- **Catalog status:** Configured feature

### Auto-restart (owner/staff)

- **Purpose:** Save preparation, advance warnings, and scheduled game restarts.
- **How it works:** The owner sets a schedule and warning sequence; the host retains control of the actual process restart.
- **Catalog status:** Configured feature

### Backups & restore (owner/staff)

- **Purpose:** Create verified recovery points and roll player data back safely, with automatic restart and a retained copy of the current data.
- **How it works:** An authorized owner captures a recovery point and verifies it before guarded restore and restart.
- **Catalog status:** Configured feature

### Baryonyx unlock (owner/staff)

- **Purpose:** Give specific players Baryonyx in their class selection by Steam ID or Discord role.
- **How it works:** An owner grants this species to eligible Steam accounts or Discord roles; game delivery needs compatible runtime support.
- **Catalog status:** Configured feature

### Bodydrops (owner/staff)

- **Purpose:** Spawn a corpse near hungry dinosaurs using ordered, configurable rules.
- **How it works:** Configured hunger and placement rules request corpse spawns only when the connector can validate live game state.
- **Catalog status:** Connector required

### Commands (owner/staff)

- **Purpose:** Build chat commands from controlled actions. Evrima RCON displays direct replies in its private announcement overlay; it cannot insert a normal Global or Local chat line.
- **How it works:** The owner maps chat commands to allowed actions; a connector validates the issuer and uses supported reply channels.
- **Catalog status:** Connector required

### Community earnings (owner/staff)

- **Purpose:** Show owner-configured sources of community currency and whether earnings are currently available.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Community subscriptions (owner/staff)

- **Purpose:** Display the server community subscriptions available to the linked player.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Cross-species chat (owner/staff)

- **Purpose:** Allow selected species to hear each other's local chat while leaving global and administrative chat untouched.
- **How it works:** Selected species pairs are intended to share local chat only; this remains in development and needs multiplayer proof.
- **Catalog status:** In development

### Custom community URL (owner/staff)

- **Purpose:** Choose the address players use after extinctionos.com/community/.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Social Group Limits (owner/staff)

- **Purpose:** Override the maximum group size per species. Species left on Default keep the base-game limit.
- **How it works:** The owner chooses per-species caps; default species retain base-game limits until validated overrides apply.
- **Catalog status:** Multiplayer validation pending

### Sunlight Schedule (owner/staff)

- **Purpose:** Jump instantly to a native day phase outside the saved cycle. Website owner access and exactly one logged-in native game admin are required.
- **How it works:** An authorized owner requests a native day-phase change through a compatible connector after admin-state checks.
- **Catalog status:** Connector required

### Diet editor (owner/staff)

- **Purpose:** Change what a species may eat, including carnivore, herbivore, and scavenging options.
- **How it works:** The owner defines diet permissions; a compatible runtime must apply and verify them in-game.
- **Catalog status:** Connector required

### Embeds (owner/staff)

- **Purpose:** Create a reusable message, preview it, then send it to a Discord channel.
- **How it works:** Staff preview a reusable Discord message and send it to an authorized channel.
- **Catalog status:** Configured feature

### Growth settings (owner/staff)

- **Purpose:** Freeze species server-wide and set custom grow times per species.
- **How it works:** The owner sets freezes or grow times per species; game-state enforcement requires the connector.
- **Catalog status:** Connector required

### Hunt History (owner/staff)

- **Purpose:** Control the public and Discord Hunt History while protecting player identities.
- **How it works:** Supported events feed a privacy-controlled record; publication is optional and multiplayer event capture must be validated.
- **Catalog status:** Multiplayer validation pending

### Companion Activity (owner/staff)

- **Purpose:** Stream near-real-time player stats to the launcher overlay while it is open.
- **How it works:** An open companion session receives authorized, near-real-time player status from the linked server.
- **Catalog status:** Configured feature

### Live Appearance Studio (owner/staff)

- **Purpose:** Let players recolor their own dinosaur from the launcher overlay while restricting access by Discord role.
- **How it works:** Eligible players select allowed color regions; saving needs a verified game application path.
- **Catalog status:** Configured feature

### Group Composition Rules (owner/staff)

- **Purpose:** Let selected species group together using controlled invite limits and allowed pairs.
- **How it works:** Allowed species pairings and invite limits are being developed; not yet an approved live rule.
- **Catalog status:** In development

### Mixpacking punishment rules (owner/staff)

- **Purpose:** Warn cross-species packs, allow time to split up, then apply controlled penalties until the rule is satisfied.
- **How it works:** Configured detection, warning, grace period, and penalty rules require verified live group telemetry.
- **Catalog status:** Configured feature

### Mutation effects (owner/staff)

- **Purpose:** Override the verified native mutation values for every live and newly spawned dinosaur.
- **How it works:** Owner-defined mutation values require native verification before applying to live and new dinosaurs.
- **Catalog status:** Connector required

### Nest Management (owner/staff)

- **Purpose:** Control where nests may be placed, who can participate, and hatchling mutation chances.
- **How it works:** Nest placement, participants, and hatchling rules are being developed and require full multiplayer validation.
- **Catalog status:** In development

### Oviraptor unlock (owner/staff)

- **Purpose:** Give specific players Oviraptor in their class selection by Steam ID or Discord role.
- **How it works:** An owner grants this species to eligible Steam accounts or Discord roles; game delivery needs compatible runtime support.
- **Catalog status:** Configured feature

### Plants & hunger (owner/staff)

- **Purpose:** Control plant abundance and the hunger and thirst decay rates.
- **How it works:** The owner configures the rule or page; game-facing delivery requires a compatible paired connector and verification.
- **Catalog status:** Connector required

### Player Community Credits Ledger (owner/staff)

- **Purpose:** Review every coin booking for the active server without exposing another player's statement.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Species Capacity (owner/staff)

- **Purpose:** Control which dinosaurs players can pick and how many of each may be alive.
- **How it works:** Owner caps and availability rules are applied only when a compatible runtime can verify active species counts.
- **Catalog status:** Connector required

### Prime notifications (owner/staff)

- **Purpose:** In-game progress popups above chat.
- **How it works:** Supported in-game progress events trigger a private player notification.
- **Catalog status:** Configured feature

### Prime quest fix (owner/staff)

- **Purpose:** Restore missing Prime completion flags after qualifying native zone entries.
- **How it works:** The owner configures the rule or page; game-facing delivery requires a compatible paired connector and verification.
- **Catalog status:** Connector required

### Proximity voice (owner/staff)

- **Purpose:** Required local voice automatically connects live players through the current Companion. Same-species communication is standard unless saved Cross-species Chat pairs allow otherwise.
- **How it works:** The companion handles opt-in live voice sessions for connected players; game-server and player-service compatibility are separate gates.
- **Catalog status:** Required player service

### Server config files (owner/staff)

- **Purpose:** Edit Game.ini, Engine.ini, and GameUserSettings.ini through the guarded SFTP connection.
- **How it works:** Authorized staff edit guarded allowlisted configuration files over a private file connection.
- **Catalog status:** Configured feature

### Server list alerts (owner/staff)

- **Purpose:** Watch your EOS listing and notify Discord when it disappears or returns.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Appearance Studio locks (owner/staff)

- **Purpose:** Hide species, lock color zones, and limit player palettes without affecting staff-created skins.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Style templates (owner/staff)

- **Purpose:** Reusable look presets: colors, font and custom CSS. Apply one to any server, keep it private or share it with other owners.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Travel Network (owner/staff)

- **Purpose:** Create controlled travel destinations with role, species, distance, and cooldown limits.
- **How it works:** Eligible linked players request owner-published destinations; movement depends on connector-side validation and cooldowns.
- **Catalog status:** Connector required

### Vegetation Impact (owner/staff)

- **Purpose:** Let heavy dinosaurs knock small trees over using controlled thresholds.
- **How it works:** A native extension applies configured tree-impact thresholds only after build-specific compatibility tests.
- **Catalog status:** Connector required

### Recovery Move (owner/staff)

- **Purpose:** Let stranded players safely relocate after standing still, with cooldowns and movement checks.
- **How it works:** A stranded player requests movement; cooldown and stationary checks precede a supported game action.
- **Catalog status:** Configured feature

### Climate Schedule (owner/staff)

- **Purpose:** Choose an instant live-server transition outside the saved cycle. Website owner access and exactly one logged-in native game admin are required.
- **How it works:** An authorized owner requests a native weather transition through a compatible connector after admin-state checks.
- **Catalog status:** Connector required

### Field Brief (player)

- **Purpose:** Give players a branded starting point with community announcements, server status and shortcuts to published pages.
- **How it works:** The owner publishes this server-scoped page; linked players see permitted content and actions. Game data requires its matching integration.
- **Catalog status:** Owner-published page

### Hunt History (player)

- **Purpose:** Present the owner-enabled activity feed when its supported event source is connected; an empty feed is not proof of event capture.
- **How it works:** Supported events feed a privacy-controlled record; publication is optional and multiplayer event capture must be validated.
- **Catalog status:** Owner-published page

### Appearance Studio (player)

- **Purpose:** Provide the community’s owner-enabled skin-design interface and honor its restrictions and supported preview/application workflow.
- **How it works:** The owner publishes this server-scoped page; linked players see permitted content and actions. Game data requires its matching integration.
- **Catalog status:** Owner-published page

### Travel Network (player)

- **Purpose:** Let eligible linked players review owner-published teleport destinations and use a guarded compatible in-game movement workflow.
- **How it works:** Eligible linked players request owner-published destinations; movement depends on connector-side validation and cooldowns.
- **Catalog status:** Connector required

## World Operations

### Wildlife Reset (owner/staff)

- **Purpose:** Periodically clear AI corpses to keep the map clean using Evrima's native RCON wipe.
- **How it works:** The owner schedules guarded AI cleanup through a supported native server action.
- **Catalog status:** Connector required

### Habitat Seeder (owner/staff)

- **Purpose:** Draw Habitat Seeder zones on Gateway, choose species, and tune count, growth, respawn, and despawn.
- **How it works:** Staff draw zones and species targets; the native connector must manage live population within caps.
- **Catalog status:** Connector required

### Wildlife Director (owner/staff)

- **Purpose:** Create automatic AI creature presets with population caps and respawn controls.
- **How it works:** Owner presets define AI counts and pacing; live spawning requires the compatible game connector.
- **Catalog status:** Connector required

### Aquatic Population (owner/staff)

- **Purpose:** Manage Schooling Fish and Elite Fish populations with guarded refill limits.
- **How it works:** The owner sets fish refill limits; the native connector must verify actual aquatic population.
- **Catalog status:** Connector required

### Island Operations Map (owner/staff)

- **Purpose:** See where connected players are on Gateway. This page is private to authorized staff.
- **How it works:** Authorized staff see connected-player location data; public disclosure is excluded.
- **Catalog status:** Connector required

### Wildlife Population (owner/staff)

- **Purpose:** Prepare guarded AI population and spawn pacing for the selected server.
- **How it works:** The owner sets guarded AI population limits; native telemetry and spawn control are required.
- **Catalog status:** Connector required

### Island Operations Map (player)

- **Purpose:** Provide the owner-enabled player map experience with privacy and access rules, using the supported map integration.
- **How it works:** Authorized staff see connected-player location data; public disclosure is excluded.
- **Catalog status:** Connector required

## Owner experience

### AI Assist (owner/staff)

- **Purpose:** Installation help, safe error diagnosis, setup commands, and guidance for every ExtinctionOS feature.
- **How it works:** The owner asks for setup guidance and diagnostics; it does not bypass permissions or directly change a server without an authorized action.
- **Catalog status:** Configured feature

### Game admins (owner/staff)

- **Purpose:** Manage and persist the administrator list in Linux Game.ini. Saved administrators are restored before every server launch.
- **How it works:** An owner updates the administrator list in guarded game configuration; saved entries persist across launch.
- **Catalog status:** Configured feature

### Platform subscriptions (owner/staff)

- **Purpose:** Choose the monthly plan that matches the number of servers and ExtinctionOS tools you need.
- **How it works:** An owner chooses a platform tier; entitlements determine which ExtinctionOS tools are available.
- **Catalog status:** Configured feature

### Referrals (owner/staff)

- **Purpose:** Invite another server owner and earn a 5% discount when they purchase a paid plan.
- **How it works:** Invitations and qualifying paid subscriptions are recorded so eligible discounts can be calculated.
- **Catalog status:** Configured feature

### Server Admins (owner/staff)

- **Purpose:** Invite people, assign roles, and control exactly which ExtinctionOS server functions they can use.
- **How it works:** The owner invites staff and assigns roles per server, controlling access to each function.
- **Catalog status:** Configured feature

### Server owner tutorial (owner/staff)

- **Purpose:** We will show where to go, what to fill in, where to get it, and why each required connection matters.
- **How it works:** A guided setup sequence explains required connections and records completed steps.
- **Catalog status:** Configured feature

## Player Safety

### Staff Recruitment (owner/staff)

- **Purpose:** Create public application forms and review their configuration.
- **How it works:** The owner publishes a form; applicants submit it and authorized staff review the response.
- **Catalog status:** Configured feature

### Ban & Unban (owner/staff)

- **Purpose:** Review warnings, kicks, bans, and private staff notes for the active server.
- **How it works:** Authorized staff review discipline records and request a supported game action through the connector.
- **Catalog status:** Connector required

### Overlay (owner/staff)

- **Purpose:** Enable the ExtinctionOS Overlay for everyone on this server after one server-owner setup.
- **How it works:** The owner enables the player overlay; clients receive only data they are authorized to see.
- **Catalog status:** Connector required

### Player workspace (owner/staff)

- **Purpose:** Give a linked player a private area for their account-specific community actions and status.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Players (owner/staff)

- **Purpose:** Inspect current dinosaurs and survival status. Steam64 IDs are visible only to authorized staff.
- **How it works:** Authorized staff inspect the selected server’s roster and survival status; private identifiers remain restricted.
- **Catalog status:** Configured feature

### Tickets (owner/staff)

- **Purpose:** Player support from the website and connected services.
- **How it works:** Players submit support requests; staff handle them in a server-scoped queue.
- **Catalog status:** Configured feature

### Staff Recruitment (player)

- **Purpose:** Let players submit community applications through owner-configured forms instead of scattered messages.
- **How it works:** The owner publishes a form; applicants submit it and authorized staff review the response.
- **Catalog status:** Owner-published page

## Seasons & Events

### Seasonal Progress (owner/staff)

- **Purpose:** Create free and premium reward tracks powered by quest, playtime, and kill XP.
- **How it works:** Quest and activity events produce server-side XP records; eligible tiers and claims are checked against saved progress.
- **Catalog status:** Configured feature

### Contracts (owner/staff)

- **Purpose:** Let players or staff place rewards on another player's head and track active contracts.
- **How it works:** The owner configures bounties; verified multiplayer events are required before settling a target or reward.
- **Catalog status:** Multiplayer validation pending

### Community Events (owner/staff)

- **Purpose:** Manage public event listings. Gameplay steps are saved definitions only; they do not run here.
- **How it works:** Staff publish schedules and requirements; saved gameplay definitions do not themselves automate game events.
- **Catalog status:** Multiplayer validation pending

### Drawings (owner/staff)

- **Purpose:** Create website or Discord giveaways, collect entries, and draw random winners.
- **How it works:** Staff define eligibility and draw winners from recorded entries.
- **Catalog status:** Configured feature

### Rankings (owner/staff)

- **Purpose:** Configure public rankings, seasons, privacy rules, and placement prizes.
- **How it works:** The owner chooses metrics, privacy, and season rules; authorized events feed standings.
- **Catalog status:** Configured feature

### Isolation Rules (owner/staff)

- **Purpose:** Mark repeat same-species killers as outcasts, warn nearby players, and configure their skin and reward.
- **How it works:** Configured repeat-kill rules require validated multiplayer events before warning or penalizing players.
- **Catalog status:** Multiplayer validation pending

### Expeditions (owner/staff)

- **Purpose:** Build daily, weekly, and monthly quest pools with XP and configurable rewards.
- **How it works:** Owner-defined daily, weekly, and monthly objectives award XP and rewards from verified completion records.
- **Catalog status:** Configured feature

### Seasonal Progress (player)

- **Purpose:** Present owner-configured progression tiers and rewards so players can see their next community milestone.
- **How it works:** Quest and activity events produce server-side XP records; eligible tiers and claims are checked against saved progress.
- **Catalog status:** Owner-published page

### Contracts (player)

- **Purpose:** Show owner-enabled bounty targets, progress and rewards, with authoritative events required for verified settlement. Multiplayer validation remains important.
- **How it works:** The owner configures bounties; verified multiplayer events are required before settling a target or reward.
- **Catalog status:** Connector required

### Community Events (player)

- **Purpose:** Help players discover owner-published community events and their requirements, schedules and eligible actions.
- **How it works:** Staff publish schedules and requirements; saved gameplay definitions do not themselves automate game events.
- **Catalog status:** Owner-published page

### Drawings (player)

- **Purpose:** Let players discover owner-published giveaways, read entry requirements and follow their participation status.
- **How it works:** Staff define eligibility and draw winners from recorded entries.
- **Catalog status:** Owner-published page

### Rankings (player)

- **Purpose:** Show owner-published rankings so players can follow their community progress and achievements.
- **How it works:** The owner chooses metrics, privacy, and season rules; authorized events feed standings.
- **Catalog status:** Owner-published page

### Isolation Status (player)

- **Purpose:** Present the owner’s outcast-system information and rules. Enforcement and events require the matching live integration and multiplayer validation.
- **How it works:** The owner publishes this server-scoped page; linked players see permitted content and actions. Game data requires its matching integration.
- **Catalog status:** Owner-published page

### Expeditions (player)

- **Purpose:** Give players owner-configured objectives and eligibility-checked rewards, with game-linked progress dependent on compatible telemetry.
- **How it works:** Owner-defined daily, weekly, and monthly objectives award XP and rewards from verified completion records.
- **Catalog status:** Owner-published page

## Platform Control

### Advanced rules (owner/staff)

- **Purpose:** Plugin-powered and specialized server rules are kept separate from standard Game.ini controls.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Anti-cheat (owner/staff)

- **Purpose:** Detect mid-session identity swaps and illegal imported skin colors, then apply your configured response.
- **How it works:** Configured checks detect supported identity or skin anomalies; owner-selected responses are audited.
- **Catalog status:** Configured feature

### Anti-crash (owner/staff)

- **Purpose:** Let the host recover a failed game process, with a limit on repeated starts.
- **How it works:** A bounded process-recovery policy prevents unlimited restart loops.
- **Catalog status:** Configured feature

### Audit log (owner/staff)

- **Purpose:** Every server-changing action is recorded locally.
- **How it works:** Server-changing operations produce a local, reviewable action record.
- **Catalog status:** Configured feature

### Configuration (owner/staff)

- **Purpose:** Verified values read from the Linux Game.ini. Passwords and private administrator IDs are never displayed.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Compatibility repairs (owner/staff)

- **Purpose:** Configure safe workarounds for known base-game problems on the active server.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Game servers (owner/staff)

- **Purpose:** Register additional server profiles while keeping player lists and connection status separate.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Health & crash detection (owner/staff)

- **Purpose:** Background observations distinguish connection loss from planned restarts. Connection loss alone does not prove a game crash.
- **How it works:** Health observations distinguish an offline connection from a confirmed failure and planned restart.
- **Catalog status:** Configured feature

### Netcode profiles (owner/staff)

- **Purpose:** Choose a safe starting point, review every Engine.ini override, then apply it with a verified backup.
- **How it works:** The owner reviews proposed config overrides; changes require a verified backup and compatible connector.
- **Catalog status:** Connector required

### Overview (owner/staff)

- **Purpose:** The connector is trying to reach the game server.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Schedules (owner/staff)

- **Purpose:** ExtinctionOS sends countdown warnings and saves the server. PingPlayers performs the scheduled reboot.
- **How it works:** ExtinctionOS warns and saves; PingPlayers remains responsible for the timed process reboot.
- **Catalog status:** Configured feature

### Server controls (owner/staff)

- **Purpose:** Send announcements, save the world, and restart the server.
- **How it works:** Authorized users request announcement, save, or restart; connector and host permissions gate delivery.
- **Catalog status:** Configured feature

### Server setup (owner/staff)

- **Purpose:** Add a private server, then pair its local connector. RCON stays on the game-server machine.
- **How it works:** An owner registers one private server and pairs its local connector; RCON remains on the game host.
- **Catalog status:** Configured feature

### Tool library (owner/staff)

- **Purpose:** Explore every tool’s readiness and On/Off status. Only the ExtinctionOS site owner can change library switches. This empty-data preview simulates a connected compatible runtime, so completed tools appear green; unfinished tools remain marked In development.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

## Player Identity

### Overlay preferences (player)

- **Purpose:** Personal overlay preferences controls on the community website.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Player support tickets (player)

- **Purpose:** Personal player support tickets controls on the community website.
- **How it works:** The server owner saves per-server settings; any game-affecting operation also requires the relevant permission and compatible connector.
- **Catalog status:** Configured feature

### Account Ledger (player)

- **Purpose:** Give players a private view of their own purchases, subscriptions and transaction status.
- **How it works:** Purchases, claims, and adjustments are recorded centrally; each player sees only their own account history.
- **Catalog status:** Configured feature

### Voice preferences & sound check (player)

- **Purpose:** Personal voice preferences & sound check controls on the community website.
- **How it works:** The interface is limited to a restricted preview; it is not an approved general-availability integration.
- **Catalog status:** Restricted preview
