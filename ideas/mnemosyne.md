# Mnemosyne: build plan (bandwidth-only)

**Target:** Tatum x Walrus Total Recall (**Nov 10, 17:00 UTC**, $4,500; must use Walrus Memory on Mainnet and Tatum AI Builder or RPCs). Optional reuse: Midnight Wave 3 (Nov 16), Decentralize AI (Feb 27, 2027).

**Go/no-go:** start only if Blackbox (Oct 27) and TasteProbe (Oct 30) have shipped and LEASH is on track for Nov 12. Otherwise skip it.

## Weak spots to fix
1. **It's two-sided with no demand side.** Fix: ship one real consumer agent (a travel or dining planner) that actually uses the memory.
2. **Scope overlap.** Fix: reuse the LEASH Noir tooling for attribute proofs and the Blackbox Walrus code for storage.
3. **Payments are a distraction for a $4.5k prize.** Fix: make x402 per-recall payments a stretch goal.

## Architecture
```
user web app (Next.js; skip Expo for speed) → encrypt memory → Walrus Memory (mainnet)
consumer agent → MCP memory server → consent request → user approves slice
                → returns attribute proof (Noir: e.g. budget < X, dietary = veg) instead of raw data
                → (stretch) x402 micro-payment per recall
revocation: rotate key / update policy → next recall fails
```

## MVP scope
- Store and update encrypted memory on Walrus mainnet via Tatum.
- MCP memory server with consent and revocation.
- One Noir attribute proof (a budget threshold).
- One consumer agent completing a real task.

## Day-by-day
| Date | Work |
|---|---|
| Nov 3 | Go/no-go check. Read the Total Recall rules; set up Tatum and Walrus. |
| Nov 4–5 | Encrypted storage plus the MCP server. |
| Nov 6 | Consent and revocation flow. |
| Nov 7 | Attribute proof, reusing LEASH's Noir setup. |
| Nov 8 | Consumer agent. |
| Nov 9 | Demo video. |
| Nov 10 | Submit before 17:00 UTC (22:30 IST). |

## Demo script
The agent asks for "dietary + budget" → a consent popup → the agent gets a proof, not the data → it books a real option → revoke → the next call fails.

## Risks and cuts
Cut x402 first, then the ZK proof (fall back to scoped plaintext disclosure, and label it honestly). Never cut real Walrus mainnet storage; it's a hard requirement.
