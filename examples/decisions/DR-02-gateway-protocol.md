# DR-02: Node-to-gateway and gateway-to-server protocols (fictional example)

| Owner | Status | Date | Related requirement IDs |
| --- | --- | --- | --- |
| @dana-example | Proposed | 2026-10-12 | NFR-03, NFR-05, NFR-08 |

**What are we deciding?** How seat nodes talk to the zone gateway, and how the gateway reaches the server.

**Why now?** Firmware and the network diagram (B9) depend on it.

## Options considered

| Option | Description | Pros | Cons |
| --- | --- | --- | --- |
| A | BLE advertisements → gateway; MQTT over TLS → server | Very low node power; standard broker | BLE range ≈ 10–15 m indoors |
| B | Wi-Fi on every node; HTTPS → server | No gateway | Battery life weeks, not months; campus Wi-Fi registration per device |

## Choice and reasons

**Chosen (proposed):** A — meets NFR-05 (≥ 60 days battery) and needs only one registered device per zone.

## Verification

Range test across one library floor (T-05); battery estimate from measured current (KPI sheet).
