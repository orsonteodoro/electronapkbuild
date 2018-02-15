# electronapkbuild

## Instructions

### Update libuv with patch

increment pkgrel by 1

Add the patch below to source

This package requires a patched libuv.  You can find the patch at: https://github.com/electron/node/commit/693b35014efe6416d52e3ae0c1bcfa173670e45b#diff-e8b03d17fba605de23431c53172682a5 or https://github.com/electron/node/commits/2586ef1eb5f5f53da2c1852efb47c20dc8888534/deps/uv

You may need to disable check for unit tests if you have a bad router or it fails.

### Building

Rename this folder to electron and place it in testing

To build run:
abuild snapshot
abuild checksum
abuild -rK

To run:
cd src/*2/out/R
paxmark -cm electron
./electron --help

## What works?

The electron executible runs (but still segfaults at the end) with --help.

## NOTES

You only need paxmark -cm for electron to work with --help but gentoo puts -r (disable RANDMMAP) for some reason.


## BUGS

It segfaults at the end when electron --help is invoked.
