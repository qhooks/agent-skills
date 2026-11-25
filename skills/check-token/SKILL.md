---
name: qhooks-check-token
description: Use when the user asks to inspect QHooks token safety evidence.
---

1. Read the current tool catalog and exact schema, then call `qproof_check` for the requested EVM token or Solana mint.
2. Report the stored verdict, evidence age, coverage, and any missing, stale, partial, or unavailable fields. Stored evidence is not a fresh scan or a guarantee.
3. `qproof_scan` performs a separate paid fresh scan through x402. Use it only when the user specifically requests a fresh paid scan; follow the returned payment requirements and report completion only when confirmed.
