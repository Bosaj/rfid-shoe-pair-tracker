# RFID Shoe Pair Tracker

> Count left and right shoes separately with RFID so store staff see broken pairs and stock mismatches.

**Status:** pre-alpha scaffold (no code yet). **Feasibility rating:** 2/10 as a new idea — commercial retail RFID products exist; value is in a small-retailer workflow.
**Idea:** #08 in the owner's ideas backlog. **Author:** Oussama Elhadji (`@Bosaj`) <oussousselhadji@gmail.com>.

---

## Problem

Seen at Decathlon: during stock checks it is hard to know how many left and right shoes are on the shelf. Display shoes and returns break pairs, so sizes look available but cannot be sold.

## Why build it (gap analysis)

Large retailers already use item-level RFID (the original notes mention Checkpoint ItemOptix and TAG Co. products; verify their current capabilities). The open question is whether small shoe shops need a cheap phone-based version: one tag per shoe, a handheld UHF reader, and a pair-matching report.

## Prior art & open bases to fork

- [GS1 EPC Tag Data Standard](https://www.gs1.org/standards/rfid/tds) — How item identity is encoded on RFID tags; a left/right flag can live in the serial.

## Proposed architecture

1. Tag scheme: SGTIN per product + serial with a left/right bit, written at receiving.
2. Reader app: Bluetooth UHF handheld connected to a phone app that streams EPC reads.
3. Pair engine: group by product + size, count left vs right, list missing halves by location.
4. Report: mismatches by shelf, with export to the shop's stock system.

## Tech stack (proposed)

- Android app (reader SDK)
- Kotlin pair-matching engine with tests
- CSV / Google Sheets export

## Roadmap

- v0.1 — Tag encoding scheme + simulated reader.
- v0.2 — Pair-matching engine and mismatch report.
- v0.3 — Real UHF handheld integration.
- v0.4 — Multi-location stock + export.

---

## For LLM agents & contributors continuing this project

This repo is a **scaffold**: README + standard files, no implementation yet. If you are an AI agent asked to "continue developing", read this section first.

- Start with a simulator: generating fake EPC reads lets you build and test the pair engine without hardware.
- Interview a store manager before buying any reader.

**Ground rules:** keep this README in sync with reality as you build; prefer forking/reusing the bases above over greenfield code; write tests for anything correctness-critical; never commit secrets (see `.gitignore`); follow Conventional Commits (see `CONTRIBUTING.md`).

## Getting started

```bash
# nothing to run yet — this is a scaffold.
```

## 📄 License
**Proprietary & Commercial Software License** — All Rights Reserved © 2026 Oussama Elhadji (`@Bosaj`) <[oussousselhadji@gmail.com](mailto:oussousselhadji@gmail.com)>.

Unauthorized copying, distribution, resale, or reverse engineering is strictly prohibited. See [LICENSE](LICENSE) for full legal terms.
