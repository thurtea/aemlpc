# aemlpc roadmap

aemlpc is a from-scratch LPC MUD driver written in C++20: lexer, parser,
bytecode compiler, VM, object system, call_out/heart_beat, and net. LPC
is mudlib-only. The host runtime stays C++20. Do not rewrite the driver
in LPC. The product is the driver. `mudlib/` is a minimum Library that
ships with the driver so it can boot and be tested. Do not grow world
content or Rifts as roadmap work.

Primary dialect target is FluffOS. The `dialect` config also selects
LDMud. DGD is comparison-only.

## Done that matters

The language core works. Driver-side capabilities already landed:

- Multi-port `listen:` (telnet plus extra ports)
- TLS on marked listen ports
- WebSocket and WSS
- Connection encoding (default utf-8) and GMCP
- `save_object` FluffOS `.o` write-side
- Net efun sidecar (`src/efun/NetEfuns.cpp`)

Build: CMake 3.20+, C++20, PCRE2, libcrypt, SQLite, OpenSSL. See
`INSTALL.md`. Run: `./build/aemlpc etc/driver.cfg` (or `make build` /
`test` / `run`).

## Parked on purpose

Dead Souls leftover `status` keyword, DGD parity, LLVM JIT, swapout,
hotboot, LSP, efun-count chase, host rewrite, and full generational GC
unless a leak is measured.

## Next

Next work is driver work in `src/` (compiler, VM, object, efun, net, gc,
scheduler, security, persist). Mudlib changes only to prove driver
behavior or keep the minimum boot path alive.

Known gaps: namespace, includes, and binary are still partly `amlp`;
`save_object` still throws on width>1 mappings; object and closure slots
write `0`.

## Status record

These two files plus `git log`, build, and test output are authoritative,
not chat. Standing rules: `CURSOR.md`. Efun comparison:
`docs/COMPARISON.md`.
