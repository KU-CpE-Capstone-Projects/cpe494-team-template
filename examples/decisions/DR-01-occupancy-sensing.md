# DR-01: How each seat detects occupancy (fictional example)

| Owner | Status | Date | Related requirement IDs |
| --- | --- | --- | --- |
| @yousef-example | Accepted | 2026-10-05 | FR-02, NFR-03, NFR-05, NFR-07 |

**What are we deciding?** Which sensing method each seat node uses to decide "occupied" or "free".

**Why now?** The PoC specification (B7) and BOM need a sensor choice, and the library has ruled out cameras.

## Options considered

| Option | Description | Pros | Cons |
| --- | --- | --- | --- |
| A | PIR motion sensor only | Cheap (≈0.8 KD), low power | Misses a still person reading |
| B | PIR + thin pressure pad on the chair | Detects still sitting; still cheap (≈2.5 KD) | Bag on chair counts as occupied |
| C | Ceiling camera with people counting | One device covers a zone | Not allowed by the library; privacy risk |

## Choice and reasons

**Chosen:** B

- Meets FR-02 (detect a seated person) where A fails in 6 of 10 bench trials with a still reader.
- Supports NFR-07 (no personally identifiable data) — C would capture images.
- Library staff interviews (P6, P7) said cameras would not be approved.

## Impact

| Dimension | Expected effect (+/− and a number if known) |
| --- | --- |
| Accuracy / quality | + ≈ 92% in bench test (20 trials); bags cause false "occupied" |
| Speed / compute | Negligible; state change sent within 2 s |
| Bandwidth | ≈ 20 bytes per state change; ~40 messages per seat per day |
| Privacy | Only seat state + timestamp; zone totals kept 24 h |
| Cost | + 1.7 KD per node vs option A |

## Verification

**How we will test it:** test cases T-01 and T-03 in `tests/` (20 trials per node, three users, with and without a bag).

| Pass criterion | Threshold | How verified | Result (after test) |
| --- | --- | --- | --- |
| Detection accuracy | ≥ 90% | T-01, manual observation | 19/20 (95%) |
| False "occupied" from a bag clears | within 30 min | T-03, timeout logic | pending |
