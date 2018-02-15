# electronapkbuild

## Instructions

Rename this folder to electron and place it in testing

The electron executible runs --help with paxmark -cm but gentoo puts -r (disable RANDMMAP)

This package requires a patched libuv.  You can find the patch at: https://github.com/electron/node/commit/693b35014efe6416d52e3ae0c1bcfa173670e45b#diff-e8b03d17fba605de23431c53172682a5 or https://github.com/electron/node/commits/2586ef1eb5f5f53da2c1852efb47c20dc8888534/deps/uv

## BUGS

It segfaults at the end when electron --help is invoked.
