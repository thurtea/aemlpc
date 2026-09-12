# STATUS

**2026-09-12: identity rename.** Residual `amlp` driver-name strings are
now `aemlpc` (boot text, default `mud_name`, `AEMLPC_MAX_ITERATIONS`,
tmp/test prefixes, instruct include paths). Targets were already
`aemlpc` / `aemlpc_tests`. Persist dump magic `AMLPSTATE1` left as the
on-disk format token. Suite green (929, 0 fail).

**2026-09-12: docs reset.** `ROADMAP.md` and `STATUS.md` rewritten from
scratch as short driver-first records. The driver is the product.
`mudlib/` is the minimum ship Library only. No world-content or Rifts
work on the roadmap. LPC stays mudlib-only; the host stays C++20.

Do not treat chat as status. Verify against these two files, `git log`,
build, and test.

Future STATUS entries stay a few lines each: the decision and what
changed, not the derivation.
