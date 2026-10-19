# RuntimeLab

RuntimeLab is an experimental tool lab built specifically for [Bahkruums](https://www.roblox.com/games/91698952875688/Bahkruums).

It brings animation playback, movement experiments, camera controls, player ESP and item navigation into one Fluent interface. The lab is designed to explore client behavior, reproduce bugs and test interactions between the game's systems.

RuntimeLab is an independent project and is not affiliated with or endorsed by the Bahkruums developers.

## Run

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/VoyStealthMaster/RuntimeLab/main/RuntimeLab.lua"))()
```

Requires an environment that supports `game:HttpGet` and `loadstring`. Fluent is downloaded separately from its upstream release. Use **RightShift** or the **LAB** button to show the menu. Features start disabled, except the passive Bhop Coach.

The creator does not endorse exploiting live games. Cooperation is welcome if developers agree to keep their player identity private and not ban their account.

This experimental build executes five compiled Luau bytecode components through the bundled Fiu interpreter, with independent opcode permutations for each component. String/numeric pools and shuffled byte encoding remain in place. This is an adapted standard interpreter, not a wholly custom VM or a guarantee against decompilation. Buffer support is required; VM callbacks may run slower than the native V5 build. In-game compatibility and performance require testing.

Fluent UI: [dawid-scripts/Fluent](https://github.com/dawid-scripts/Fluent).

## VM dependency

[Fiu](https://github.com/rce-incorporated/Fiu), pinned revision fa1983d39f11f2b650b871d7a2d4e3b4c3e4ef2b. The MIT license is included in RuntimeLab.lua and below.

```text
MIT License

Copyright (c) 2022-2024 TheGreatSageEqualToHeaven
Copyright (c) 2019-2024 Roblox Corporation
Copyright (c) 1994–2019 Lua.org, PUC-Rio.

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
