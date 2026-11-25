---
name: qhooks-qwallet-setup
description: Use when the user asks to set up, deposit into, or withdraw from their QWallet.
---

1. Read the current tool catalog and schemas. QWallet tools are unsigned and use Robinhood Chain (4663); the owner wallet signs transactions. QHooks does not hold keys or move QWallet funds.
2. Call `prepare_qwallet_setup` for the next setup step: deploy the verifier, deploy the pool, then enroll the agent's post-quantum public key. Call again after each confirmed receipt with the new address. Keep the token list from setup.
3. For a requested deposit, call `prepare_qwallet_deposit` with the reviewed asset and raw-unit amount. Inspect any exact approval and deposit transactions; deposits need no post-quantum signature and require enrollment.
4. For a requested withdrawal, call `prepare_qwallet_withdraw` with the exact asset, amount, and recipient. Both owner-wallet EIP-712 and post-quantum signatures are required on-chain, and the approval is valid for 15 minutes.
5. Never request or expose keys, passphrases, or backups. Report completion only after the wallet confirms the signed action.
