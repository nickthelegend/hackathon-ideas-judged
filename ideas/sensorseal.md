# SensorSeal: judge verdict CUT (what it would take)

**Why it's cut:** an ESP32 secure element, P-256 signature verification inside a Noir circuit, a payout contract and a dashboard is a 3–4 week build with hardware risk. It can't finish alongside Blackbox, TasteProbe and LEASH. The listed targets (Nebius Physical AI Oct 30, Celo Nov 9, QIE Nov 30, Arbitrum Dec 5, Decentralize AI Feb 27, 2027) are better served by our other ideas, or come later.

## Weak spots
1. **Feasibility 2/10:** hardware plus in-circuit ECDSA.
2. **A simulated device key defeats the whole point** ("trust-me oracle"), so the cheap version isn't credible.
3. **There's no real customer** (microinsurer) to demo with.

## How to revive it (after Dec 5, aiming at Decentralize AI or QIE)
- **Architecture:** ESP32 + ATECC608 signs readings → hash chain → a Noir proof of "temperature above T for N consecutive readings, signed by key K" → a payout contract on Arbitrum or Celo releases a stablecoin.
- **De-risk order:** (1) benchmark P-256 verification in Noir; if it's too slow, verify signatures on-chain with a precompile and only prove the predicate. (2) Get the hardware reading-and-signing loop working. (3) Contract. (4) Dashboard.
- **MVP:** one sensor, one predicate, one payout, real hardware.
- **Demo script:** a hair dryer on the sensor → the threshold is crossed → the payout lands within a minute; a spoofed reading from an unknown key is rejected.
- **Plan (2 weeks):** week 1 = circuit and hardware spikes plus a go/no-go; week 2 = contract, UI and video.
- **Cut rule:** if in-circuit P-256 isn't working by day 4, switch to on-chain signature verification and keep only the threshold predicate in ZK.
