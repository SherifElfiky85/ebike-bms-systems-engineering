# 3. Interfaces (Interface Control Document)

Interfaces are split into **External** (crossing the BMS boundary) and **Internal** (block to block within the BMS), matching the boundary defined in [System Context](01-system-context.md) and the blocks defined in [Architecture](02-architecture.md).

## External Interfaces

| ID | Signal | Direction | Protocol | Range / Values | Failure Behavior |
|---|---|---|---|---|---|
| EXT-01 | Cell Voltage (×13) | Cells → BMS | Analog (ADC) | 2.5–4.3V | Signal out of range → Protection Logic flags fault |
| EXT-02 | Cell/Pack Temperature | Cells → BMS | Analog (NTC) | -20–80°C | Sensor open/short → treated as fault (fail-safe) |
| EXT-03 | Balance Current | BMS → Cells | Analog (switched resistor) | 0–200mA per cell | N/A (passive, no ack needed) |
| EXT-04 | Discharge Current | Cells → BMS (via shunt/Hall) | Analog | 0–60A | Signal loss → assume worst case, disable discharge |
| EXT-05 | Charge Current | Charger → BMS | Analog | 0–4A | Out of range → charge disabled |
| EXT-06 | Charge Enable/Disable | BMS → Charger | Digital (GPIO or CAN) | 0/1 | Charger must fail to "disabled" if signal lost |
| EXT-07 | Discharge FET Enable | BMS → Power Path (FETs/Contactor) | Digital (GPIO) | 0/1 | Fail-safe: FET opens (disconnects) if driver signal lost |
| EXT-08 | Fault Status | BMS → Motor Controller | UART | Bitfield (fault codes) | MC treats missing heartbeat as fault |
| EXT-09 | Current Limit | BMS → Motor Controller | UART | 0–35A | Missing signal → MC defaults to minimum safe limit |
| EXT-10 | SoC | BMS → Display/HMI | UART | 0–100% | Missing signal → HMI shows "no data" |
| EXT-11 | Fault Codes | BMS → Display/HMI | UART | Enumerated codes | — |

## Internal Interfaces (block-to-block)

| ID | Signal | Direction | Notes |
|---|---|---|---|
| INT-01 | Cell voltage/temp data | Cell Monitoring → Protection Logic | Basis for all threshold checks |
| INT-02 | Cell voltage data | Cell Monitoring → SoC Estimation | Combined with current history |
| INT-03 | Cell voltage data | Cell Monitoring → Cell Balancing | Identifies which cells need bleeding |
| INT-04 | Disconnect/Enable command | Protection Logic → Power Path Control | Single authority for FET/charge gating (EXT-06, EXT-07) |
| INT-05 | Fault status | Protection Logic → Communication | Feeds EXT-08 |
| INT-06 | SoC value | SoC Estimation → Communication | Feeds EXT-10 |
