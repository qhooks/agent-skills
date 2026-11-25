---
name: qhooks-agreement-escrow
description: Use when the user asks to prepare, fund, attest, release, refund, or check a QHooks agreement.
---

1. Read the current tool catalog and schemas. Confirm the named payer, payee, asset, exact amounts, conditions, attestors, tranches, and expiry from the user's intent. Agreements run on Robinhood Chain (4663).
2. Use `agreement_create` or `agreement_fund` for the requested creation flow; they prepare the same atomic create-and-fund operation. Existing agreements cannot be topped up. Review the complete returned plan and fees. Only the named payer signs creation.
3. Obtain agreement IDs from real confirmed receipts, then call `agreement_status` and use the actual named actor and tranche. Call `agreement_attest`, `agreement_release`, or `agreement_refund` only for the user's explicit requested action and current state.
4. Review every unsigned transaction and require the intended wallet to sign. Never guess IDs or terms hashes, auto-attest, auto-release, or report an action complete before confirmation.
