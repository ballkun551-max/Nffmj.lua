BALLKUN RIDER FARM DATA COLLECTOR v0.2.6
===========================================

This is an adapted profile of the uploaded BALLKUN Universal Map Dump script.

What it is intended to collect:
- Client-visible Workspace hierarchy and object names/paths
- NPC and vehicle-related names/metadata matched by keywords
- PlayerGui/UI hierarchy and visible text/value metadata
- Value objects and client-visible positions where supported
- Remote object names/paths as metadata only (no calls, no interception)

What was disabled:
- Script decompilation
- Nil-instance/script collection
- Remote invoke hooks / remote traffic interception
- Large default scan limits were reduced for a first pass

How to use:
1. Run only in a Roblox experience you own or are authorized to test.
2. Open the collector UI and press START/SNAPSHOT.
3. Let it finish; inspect the output folder shown by the script.
4. Zip the generated folder and share it for Rider Farm analysis.

Expected output folder:
workspace/BALLKUN_RiderFarm_Data/<ExperienceName>_<PlaceId>/

Important:
- This script does not automate gameplay or call game remotes.
- It cannot reveal server-only logic, hidden server state, or guarantee exact
  Rider Farm event semantics.
- Executor filesystem APIs differ; if writefile/folder APIs are unavailable,
  the script may only report in-memory results.
- Review and test in an authorized environment. No live-game validation has
  been performed here.


v0.2.6 changes:
- Reworked saveMem() with explicit Lua environment resolution and persistent table reuse.
- Improved folder creation checks and flat-file / in-memory fallback behavior.
- Added startup and scan-start notifications.
- Added verified UI parenting fallback (gethui -> CoreGui -> PlayerGui).
- Switched button activation connections to Activated for mouse/touch compatibility.
