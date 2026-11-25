---
name: qhooks-trade
description: Use when the user asks to prepare a QHooks spot token trade.
---

1. Read the current tool catalog and schemas. Call `qproof_check` first for the requested token; preserve evidence age, missing or partial data, and errors. This is stored evidence, not a fresh scan or guarantee. `qproof_scan` is a separate paid fresh scan; use it only when specifically requested and follow its payment flow.
2. Inspect the listed token market and pool, then call `quote` with the requested chain, token, side, raw positive integer amount, and signing wallet when required. Review route notes and quote details; stop if routing data is missing or not routable.
3. Only for the explicitly requested trade, call `prepare_trade` using the reviewed quote inputs. Review chain, wallet, transactions, fees, minimum output, and deadline. Re-prepare after input changes or expiry.
4. The QHooks tool does not sign or broadcast. The agent's own wallet (or the user's intended wallet) signs the reviewed plan. Never request keys or seed phrases.
