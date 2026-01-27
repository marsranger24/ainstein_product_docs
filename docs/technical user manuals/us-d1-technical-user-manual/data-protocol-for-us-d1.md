---
title: Data Protocol for US-D1
deprecated: false
hidden: true
metadata:
  robots: index
---
## 5.1 UART Data Protocol Specifications

- Baud Rate: 115200 b/s
- Data bit: 8
- Parity bit: N
- Stop bit: 1
- Voltage Level: 3.3V

A single data packet consists of six(6) bytes. Table 2 defines the packet structure.

**Table 2: UART Data Packet Definition**

| From (Byte) | US-D1 Altimeter (Data) | To/Receiver (Note)                  |
| :---------- | :--------------------- | :---------------------------------- |
| 1           | 0xFE                   | Packet Head                         |
| 2           | 0x02                   | Version ID                          |
| 3           | 0x\*\*                 | Altitude (Least Significant 8 Bits) |
| 4           | 0x\*\*                 | Altitude (Most Significant 8 Bits)  |
| 5           | 0x\*\*                 | 5 0x\*\* SNR                        |
| 6           | 0x\*\*                 | Checksum (see formula below)        |

**Notes:**

- '\*' refers to a variable bit containing dynamic data.
- Altitude: The altitude bytes can be combined (total 16 bits) to represent the altitude information in centimeters. The structure would be: 0x[MSB][LSB], where MSB and LSB are each two hexadecimal numbers (8 bits).
- Checksum: The Checksum Byte could be used in the following:
  - checksum = (Version_ID + Altitude_H + Altitude_L + SNR) & 0xFF
  - if checksum = 1, check passed
  - if checksum = 0, check failed

## 5.2 Private CAN Data Protocol Specifications

- Baud Rate: 1 Mb/s
- Frame ID: customized (Extended Frame)
- CAN Standard: CAN Protocol 2.0 section A and B, ISO 11898-1:2015,-4

A single data packet uses four bytes of an Extended CAN frame. The type of CAN frame used and CAN ID of the device can be customized. The CAN frame is defined in table 3.