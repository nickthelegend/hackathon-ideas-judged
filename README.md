# Hackathon Ideas: Judged

Honest judge verdicts on ideas bot's top 5 hackathon ideas for Nick (nickthelegend), as of Oct 19, 2026 (IST).

- **Sources:** `top5-ideas.md` (ideas, pitches, target events) and `hackathons.json` (195 open hackathons from hacklist.io and hackathons.fun, each with a `judgeScore` and `judgeIdea`). No data here was invented; deadlines and prizes are copied from those listings. **Confirm rules and timezones on each event page before relying on them.**
- **Rubric:** every idea is scored 1–10 on Novelty, Technical depth, Feasibility in the time left, Impact and Demo-ability. Overall is the average of the five.
- **Build plans:** `ideas/<slug>.md` has the end-to-end build plan for each idea. `CLAUDE.md` is for coding agents.

## Scorecard

| Idea | Novelty | Tech depth | Feasibility | Impact | Demo | Overall | Verdict |
|---|---|---|---|---|---|---|---|
| Blackbox Receipts | 6 | 7 | 9 | 8 | 9 | **7.8** | BUILD FIRST |
| LEASH | 9 | 9 | 5 | 9 | 9 | **8.2** | BUILD, stateless 2-rule version |
| TasteProbe | 7 | 6 | 8 | 7 | 9 | **7.4** | BUILD |
| Mnemosyne | 7 | 8 | 5 | 6 | 7 | **6.6** | ONLY IF BANDWIDTH |
| SensorSeal | 8 | 8 | 2 | 7 | 8 | **6.6** | CUT |

**Build priority:** 1. Blackbox Receipts → 2. TasteProbe → 3. LEASH (stateless) → 4. Mnemosyne (optional) → SensorSeal cut.

---

## 1. Blackbox Receipts: a verifiable flight recorder for agents ([plan](ideas/blackbox-receipts.md))
**Pitch:** every agent action emits a signed, hash-chained receipt covering inputs, tools, permissions, cost, approver and result. Receipts are anchored on Walrus or a chain, and auditors get selective-disclosure proofs.

**Targets** (from hackathons.json, `judgeIdea = Blackbox Receipts`):

| Hackathon | Deadline | Prize | judgeScore | Link |
|---|---|---|---|---|
| Open Agent Hackathon 2026 | 2026-10-20 | Up to $20,000 | 7 | https://hackathon.genai.works/sign-up?hackathon=019fd164-82b9-7382-a536-d9093c576ed2 |
| Life After Code: GitLab Transcend Hackathon | 2026-10-27 | $45,000 in cash | 10 | https://gitlab-transcend.devpost.com/ |
| Total Recall / Tatum x Walrus Memory Hackathon | 2026-11-10 | $4,500 | 8 | https://tatum.io/hackathon/total-recall |
| Cortensor Hackathon #5 | 2026-12-18 | $1,150 total, paid in $COR equivalent (50% liquid, 50% in a one-month staking lock) | 7 | https://dorahacks.io/hackathon/2418/detail |
| Decentralize AI Hackathon | 2027-02-27 | $51,750+ total value + $35,000 in participant AI compute credits | 10 | https://decentralizeai.tech/ |
Open Agent: the Oct 20 date is the **sign-up cutoff**. The build sprint runs **Oct 22–27**, per the listing.

**Rating:** Novelty 6 · Tech depth 7 · Feasibility 9 · Impact 8 · Demo 9 → **7.8**

**Verdict:** build this first. It's the most buildable idea, and one codebase can be entered in Open Agent ("The Agent That Can Explain Why" track) and GitLab Transcend ($45k, Oct 27). Novelty is its weak spot: "execution receipts" is a publicly suggested idea on Product Hunt, so a plain trace viewer loses. It wins only with real tamper evidence: the live demo where one edited line breaks the chain, plus at least one property you can prove ("no secrets read"). Without the crypto layer it's just LangSmith with extra steps.

## 2. LEASH: zero-knowledge spending mandates for AI agents ([plan](ideas/leash.md))
**Pitch:** your agent can only spend money (PayPal, USDC, x402) inside a secret policy it can't break, even when it's prompt-injected.

**Targets** (`judgeIdea = LEASH`):

| Hackathon | Deadline | Prize | judgeScore | Link |
|---|---|---|---|---|
| Arbitrum Hackathon | 2026-10-25 | USD300,000 | 8 | https://www.tradingview.com/news/coindar:93a824ebd094b:0-arbitrum-to-hold-hackathon-on-october-23rd/# |
| Arc Microgrants: Built with Arc Studio | 2026-11-01 | $4,000 USDC | 8 | https://dorahacks.io/hackathon/arc-microgrants-2 |
| Agents on Open Rails Hackathon | 2026-11-09 | $5,000 paid in CELO ($2,000 + $2,000 + $1,000 across three tracks) | 8 | https://celo-devs.beehiiv.com/p/agents-on-open-rails-hackathon-starts-tuesday-october-6th |
| PayPal AI Hackathon | 2026-11-12 | $67,500 cash plus credits | 10 | https://paypalaihackathon.devpost.com/ |
| Midnight: Build Privacy-First Apps — Wave 3 | 2026-11-16 | 5,000 USDT | 8 | https://app.akindo.io/wave-hacks/jaMZjqPOBsLXvjdG |
| Arbitrum Open House Dubai: Online Buildathon | 2026-12-05 | $30,000 (breakdown TBD) | 9 | https://www.hackquest.io/hackathons/Arbitrum-Open-House-Dubai-Online-Buildathon |
| PayBox Hackathon Chapter 1 | rolling | $20,000 USDC | 7.5 | https://developer.paybox.sh/ |

**Rating:** Novelty 9 · Tech depth 9 · Feasibility 5 · Impact 9 · Demo 9 → **8.2**

**Verdict:** it has the highest ceiling and it's Nick's core strength, but the **rolling-cap nullifier circuit is a trap**. Private state notes plus nullifiers plus time windows will eat the whole sprint. Ship a **stateless 2-rule circuit** (a Merkle merchant allowlist plus a per-transaction cap) for PayPal AI ($67.5k, Nov 12). The PayPal gateway is the money shot, and the on-chain verifier is a bonus. Rolling caps can come later for Midnight and Arbitrum if the 2-rule version is solid.

## 3. TasteProbe: GEO audits using synthetic taste-graph buyers ([plan](ideas/tasteprobe.md))
**Pitch:** see how ChatGPT, Perplexity and Gemini recommend (or ignore) your brand to thousands of realistic buyer personas, then get the fixes.

**Targets** (`judgeIdea = TasteProbe`):

| Hackathon | Deadline | Prize | judgeScore | Link |
|---|---|---|---|---|
| Meta Global AI Developer Hackathon | 2026-10-25 | $1,000,000 cash prize pool | 9 | https://cerebralvalley.ai/e/meta-ai-developer-hackathon/apply |
| ODSC AI x NEBIUS / Hackathon | 2026-10-29 | not listed | 6.5 | https://luma.com/rccjwcey |
| Nebius x NVIDIA Global AI Hackathon | 2026-10-30 | $50,000 cash plus prizes | 10 | https://nebiusglobalaihackathon.devpost.com/ |
| Qloo Agentic Hackathon | 2026-10-30 | $25,000 cash | 9 | https://qloo.devpost.com/ |
| Galuxium Nexus V2 | 2026-10-31 | $1,600 in Backboard.io platform credits (not cash, requires active $5/mo Backboard subscription to redeem) + up to $1,000 in a discretionary cash seed fund | 7 | https://galuxium-nexus-v2-29411.devpost.com/?ref_feature=challenge\u0026ref_medium=discover\u0026_gl=1*1hbpb49*_gcl_au*MTYxMjE0OTcwMy4xNzg2OTYwNDAz*_ga*MTkwNDE3NjkzNi4xNzg2OTYwNDAz*_ga_0YHJK3Y10M*czE3ODc5MTk3NTQkbzYkZzEkdDE3ODc5MTk5NjAkajU3JGwwJGgw |

**Rating:** Novelty 7 · Tech depth 6 · Feasibility 8 · Impact 7 · Demo 9 → **7.4**

**Verdict:** a solid pick for **Qloo ($25k, Oct 30)** and **Nebius x NVIDIA ($50k, Oct 30)**. One build serves both if inference runs on an NVIDIA open model on Nebius. GEO is a crowded category, so the edge has to be Qloo-grounded personas and honest statistics: share of voice with confidence intervals, not vibes. Shallow tech depth is the risk, and the counterfactual "fix → re-run → the bar moves" loop is what lifts it. Skip Bolt Builders Week (Oct 20); there isn't time.

## 4. Mnemosyne: user-owned agent memory you rent out per recall ([plan](ideas/mnemosyne.md))
**Pitch:** your preferences live encrypted on Walrus. Agents pay per recall via x402 and get ZK attribute proofs instead of raw data.

**Targets** (from the top5-ideas.md list, matched to hackathons.json; no cards carry this `judgeIdea` tag):

| Hackathon | Deadline | Prize | judgeScore | Link |
|---|---|---|---|---|
| Total Recall / Tatum x Walrus Memory Hackathon | 2026-11-10 | $4,500 | 8 | https://tatum.io/hackathon/total-recall |
| Midnight: Build Privacy-First Apps — Wave 3 | 2026-11-16 | 5,000 USDT | 8 | https://app.akindo.io/wave-hacks/jaMZjqPOBsLXvjdG |
| Decentralize AI Hackathon | 2027-02-27 | $51,750+ total value + $35,000 in participant AI compute credits | 10 | https://decentralizeai.tech/ |
| PayBox Hackathon Chapter 1 | rolling | $20,000 USDC | 7.5 | https://developer.paybox.sh/ |
| Solana Hackathon 2026 | 2026-11-08 | Accelerator places for winners (non-cash) | 5 | https://www.encodeclub.com/programmes/solana-hackathon-2026 |

**Rating:** Novelty 7 · Tech depth 8 · Feasibility 5 · Impact 6 · Demo 7 → **6.6**

**Verdict:** **only for Walrus Total Recall (Nov 10) if we have bandwidth.** It overlaps LEASH (Noir + x402) and Blackbox (Walrus), so it's a reuse play, not a new bet. Its weak spot is that it's a two-sided marketplace with no demand side at a hackathon, so the demo has to show one real consumer agent. If the time isn't there, skip it.

## 5. SensorSeal: payouts on proof of a physical event ([plan](ideas/sensorseal.md))
**Pitch:** a secure-element IoT sensor signs readings, and a ZK proof that a threshold was crossed triggers a parametric payout.

**Targets** (from the top5-ideas.md list, matched to hackathons.json):

| Hackathon | Deadline | Prize | judgeScore | Link |
|---|---|---|---|---|
| Nebius x NVIDIA Global AI Hackathon | 2026-10-30 | $50,000 cash plus prizes | 10 | https://nebiusglobalaihackathon.devpost.com/ |
| QIE Mainnet Hackathon 3.0 | 2026-11-30 | $17,000 | 8 | https://hackathon.qie.digital/ |
| Arbitrum Open House Dubai: Online Buildathon | 2026-12-05 | $30,000 (breakdown TBD) | 9 | https://www.hackquest.io/hackathons/Arbitrum-Open-House-Dubai-Online-Buildathon |
| Decentralize AI Hackathon | 2027-02-27 | $51,750+ total value + $35,000 in participant AI compute credits | 10 | https://decentralizeai.tech/ |
| Agents on Open Rails Hackathon | 2026-11-09 | $5,000 paid in CELO ($2,000 + $2,000 + $1,000 across three tracks) | 8 | https://celo-devs.beehiiv.com/p/agents-on-open-rails-hackathon-starts-tuesday-october-6th |

**Rating:** Novelty 8 · Tech depth 8 · Feasibility 2 · Impact 7 · Demo 8 → **6.6** (feasibility vetoes it)

**Verdict:** **CUT.** Hardware plus in-circuit P-256 verification plus payout contracts won't be finished in time alongside three other builds. Park it; the plan file says what would revive it.

---

## judgeScore leaderboard (top 15 from hackathons.json)

| # | Hackathon | Deadline | Prize | judgeScore | Best idea | Link |
|---|---|---|---|---|---|---|
| 1 | Life After Code: GitLab Transcend Hackathon | 2026-10-27 | $45,000 in cash | 10 | Blackbox Receipts | https://gitlab-transcend.devpost.com/ |
| 2 | Nebius x NVIDIA Global AI Hackathon | 2026-10-30 | $50,000 cash plus prizes | 10 | TasteProbe | https://nebiusglobalaihackathon.devpost.com/ |
| 3 | PayPal AI Hackathon | 2026-11-12 | $67,500 cash plus credits | 10 | LEASH | https://paypalaihackathon.devpost.com/ |
| 4 | Decentralize AI Hackathon | 2027-02-27 | $51,750+ total value + $35,000 in participant AI compute credits | 10 | Blackbox Receipts | https://decentralizeai.tech/ |
| 5 | Meta Global AI Developer Hackathon | 2026-10-25 | $1,000,000 cash prize pool | 9 | TasteProbe | https://cerebralvalley.ai/e/meta-ai-developer-hackathon/apply |
| 6 | Qloo Agentic Hackathon | 2026-10-30 | $25,000 cash | 9 | TasteProbe | https://qloo.devpost.com/ |
| 7 | MDBA Youth Blockchain Hackathon | 2026-10-31 | USD50,000 | 9 | — | https://dorahacks.io/hackathon/mdba-youth |
| 8 | ET AI Hackathon 2026: Agentic Edition | 2026-11-02 | INR200,000 | 9 | — | https://internshala.com/competitions/et-ai-hackathon-2026-agentic-edition/ |
| 9 | Agentic Banking Hackathon | 2026-11-13 | USD100,000 | 9 | — | https://www.hackerearth.com/challenges/hackathon/agentic-banking-hackathon-2/ |
| 10 | Code for a Billion — Bharat Agentic-AI Hackathon 2026 | 2026-11-15 | ₹18 lakh cash (₹1.5L/₹1L/₹50k per track) | 9 | — | https://codeforindia.org/hackathon |
| 11 | Arbitrum Open House Dubai: Online Buildathon | 2026-12-05 | $30,000 (breakdown TBD) | 9 | LEASH | https://www.hackquest.io/hackathons/Arbitrum-Open-House-Dubai-Online-Buildathon |
| 12 | Arbitrum Hackathon | 2026-10-25 | USD300,000 | 8 | LEASH | https://www.tradingview.com/news/coindar:93a824ebd094b:0-arbitrum-to-hold-hackathon-on-october-23rd/# |
| 13 | AWS Communication Developer Services (CDS) Agentic AI Partner Hackathon | 2026-10-28 | $40,000 cash | 8 | — | https://aws-cds-partner.devpost.com/ |
| 14 | Arc Microgrants: Built with Arc Studio | 2026-11-01 | $4,000 USDC | 8 | LEASH | https://dorahacks.io/hackathon/arc-microgrants-2 |
| 15 | Agents on Open Rails Hackathon | 2026-11-09 | $5,000 paid in CELO ($2,000 + $2,000 + $1,000 across three tracks) | 8 | LEASH | https://celo-devs.beehiiv.com/p/agents-on-open-rails-hackathon-starts-tuesday-october-6th |
Ties are sorted by earliest deadline. "—" means no idea is tagged for that event yet.

## Caveats
- Several listings duplicate or contradict each other (e.g. Open Agent Oct 20 vs Oct 27).
- Uniqueness checks behind the ideas were quick web searches, not a full prior-art review.
- All scores are judgement calls.
