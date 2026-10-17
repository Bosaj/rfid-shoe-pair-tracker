# 1. Architecture

1. Tag scheme: SGTIN per product + serial with a left/right bit, written at receiving.
2. Reader app: Bluetooth UHF handheld connected to a phone app that streams EPC reads.
3. Pair engine: group by product + size, count left vs right, list missing halves by location.
4. Report: mismatches by shelf, with export to the shop's stock system.

## Proposed stack
- Android app (reader SDK)
- Kotlin pair-matching engine with tests
- CSV / Google Sheets export

## Open bases to fork
- [GS1 EPC Tag Data Standard](https://www.gs1.org/standards/rfid/tds) — How item identity is encoded on RFID tags; a left/right flag can live in the serial.
