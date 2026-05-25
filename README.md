# chdman webapp

This webapp doesn't have the most convenient interface, but it aims to give the user the greatest amount of control.

I took the command line program chdman and directly converted it into a webapp. I did not modify any of chdman's code, I only modified the scripts used to compile it. Anything that is possible to do with chdman, should also be possible with chdman-web.

## How to Compile chdman.js and chdman.wasm

This information is for software developers only.

On Linux:

1. Install Emscripten 3.1.35
2. Download the source code for MAME's 0.287 release
3. Replace scripts/genie.lua with the genie.lua from chdman-web
4. In the root directory of MAME, compile chdman-web with the command `emmake make SUBTARGET=chdmanweb TOOLS=1 EMULATOR=0 TESTS=0 BENCHMARKS=0 NO_OPENGL=1 DEPRECATED=0 -j5 --ignore-errors` (`ignore-errors` is used because the tool romcmp will always fail to link unless the initial memory is set very high)
5. Rename the output `chdman` to `chdman.js`

## Credits

Both genie.lua and chdman are under the [3-clause BSD License](http://opensource.org/licenses/BSD-3-Clause).