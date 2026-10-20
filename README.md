# RuntimeLab

Experimental tool lab built specifically for [Bahkruums](https://www.roblox.com/games/91698952875688/Bahkruums).

## UI lifecycle and frame pacing candidate

Protected native controllers and a native frame dispatcher handle movement, emotes/presets, camera, ESP and bounded profiling; Main remains in the Fiu-derived IR VM. String, numeric and field obfuscation remain. Native hot paths have less VM-based resistance to analysis.

An anchored compatibility patch addresses Fluent Creator's retained destroyed theme objects and full-registry theme updates on each new object. It also retires destroyed springs and compacts disconnected signals. An unknown upstream layout is left unchanged and reported as incompatible. The inspected upstream bundle SHA256 is 5a7c879f7d0e745403e3ce205f253ee896e5aabe45da12db4d818e5b40b9fb65.

A CLI test executing the actual original/patched Creator reproduced 1600 retained destroyed instances versus zero, and 1,280,800 versus 1600 theme property writes. The final hybrid passes 37 behavior checks plus focused notification, role, workbench, camera/movement, integrity and syntax checks. Live Roblox frame pacing remains unverified.

Monitor > Copy Performance Report copies frame gaps, subsystem timings with peak timestamps, UI theme counters and notification queue state. History is bounded; nothing is uploaded automatically.

## Shared notifications

Roles, item discoveries and menu messages share one bounded card queue. Staff outranks testers/contributors and regular members; role notices interrupt item cards, which resume afterward. Teleport and Skip remain available. Duplicates, expired entries, departed players and unloaded items are discarded; disabling the tracker removes its cards without removing role messages.

## Group role monitor

Monitor checks current players and new arrivals in group14906468. Matching names: Bahkruums Tester; Town sim tester; Contributors; Ingame perms; Moderator; Head Of Staff; Backrooms Dev; Town sim Dev; Studio Access; Member2; Member.

Only public roles are observable. Names are matched directly; screenshot counts are not rank IDs. Checks use one yielding queue and a five-minute cache, with no per-frame group queries. Existing matches are summarized; new matches produce notifications. Refresh, disable and the per-player result list are in Monitor.

## Animation presets

Capture playing tracks into A/B or enter IDs. Edit speed, weight, priority, loop and start position; enter a name and Save New Preset. Selecting a preset loads the editor; Play applies it. Core/Idle/Movement survive; Action through Action4 are replaced after assets load. Stop removes only owned layers. JSON persistence uses optional executor filesystem APIs, otherwise session memory. No sounds or skill/emote remotes are created.

## Run

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/VoyStealthMaster/RuntimeLab/codex/v7-diagnostic/RuntimeLab.lua"))()
```

RightShift or LAB shows the menu. Fluent is downloaded from its upstream release and patched only when the inspected Creator anchors match. The main branch remains the earlier V6; this candidate is on codex/v7-diagnostic.

The creator does not endorse exploiting live games. Cooperation is welcome if developers agree to keep their player identity private and not ban their account.

Independent project; not affiliated with or endorsed by Bahkruums. Obfuscation is not a secrecy guarantee. Runtime compatibility and server-visible behavior require live validation.

## Dependency license

[Fiu](https://github.com/rce-incorporated/Fiu), revision fa1983d39f11f2b650b871d7a2d4e3b4c3e4ef2b. [Fluent](https://github.com/dawid-scripts/Fluent).

```text
MIT License

Copyright (c) 2022-2024 TheGreatSageEqualToHeaven
Copyright (c) 2019-2024 Roblox Corporation
Copyright (c) 1994â€“2019 Lua.org, PUC-Rio.

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE. 

```
