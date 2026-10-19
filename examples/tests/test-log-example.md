# Test log (fictional example)

## Test cases

| Test ID | Requirement ID | Objective | Steps | Expected result | Pass criterion |
| --- | --- | --- | --- | --- | --- |
| T-01 | FR-02 | Seat state detected | Sit 10 s, read 5 min, leave | occupied → free | 19/20 trials correct |
| T-02 | NFR-03 | End-to-end latency | Change state; time map update | map updates | ≤ 60 s in 95% of 30 trials |
| T-03 | FR-02 | Bag on chair clears | Put bag on chair, leave | free after timeout | ≤ 30 min |

## Results log

| Date | Test ID | Build / tag | Result | Measured value | Issue # |
| --- | --- | --- | --- | --- | --- |
| 2026-11-02 | T-01 | `494-poc-spec-v1.0` | Pass | 19/20 (95%) | — |
| 2026-11-02 | T-02 | `494-poc-spec-v1.0` | Fail | 95th pct. 84 s | #34 |
| 2026-11-09 | T-02 | fix #34 (gateway batching 5 s) | Pass | 95th pct. 41 s | — |
| 2026-11-09 | T-03 | `494-poc-spec-v1.0` | Fail | stayed occupied | #31 |
