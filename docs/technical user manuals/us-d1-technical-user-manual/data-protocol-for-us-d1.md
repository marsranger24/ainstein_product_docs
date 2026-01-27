---
title: Data Protocol for US-D1
deprecated: false
hidden: false
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

**Table 3: CAN Frame Data Packet Definition**

| From (Byte) | US-D1 Altimeter (Data) | To/Receiver (Note)                     |
| :---------- | :--------------------- | :------------------------------------- |
| EtdID       | 0x**\*\*\*\***         | Extended ID frame (Default 0x00090002) |
| 1           | 0x\*\*                 | Altitude (Most Significant 8 Bits)     |
| 2           | 0x\*\*                 | Altitude (Least Significant 8 Bits)    |
| 3           | 0x\*\*                 | SNR(Most Significant 8 Bits)           |
| 4           | 0x\*\*                 | SNR(Least Significant 8 Bits)          |
| 5           | 0x00                   | (Reserved)                             |
| 6           | 0x00                   | (Reserved                              |
| 7           | 0x00                   | (Reserved                              |
| 8           | 0x00                   | (Reserved                              |

## 5.3 DroneCAN Data Protocol Specifications

From firmware v2.4.0, US-D1 starts to support the limited feature of DroneCAN. The  
physical specs and baud rate of DroneCAN is same as Private CAN in above section,  
while the data packet and protocol follows and is compatible with the DroneCAN  
standard.

- Baud Rate: 1 Mb/s
- CAN Standard: CAN Protocol 2.0 section A and B, ISO 11898-1:2015,-4
- Message Broadcasting only
- Source Node ID
  - Default ID 32 or 33
  - Support 1 ~ 127 (Need US-D1 Firmware Update Kit to configure)
- Node Status Message
  - Data type ID: 341
  - Broadcasting in 1 Hz
- Range Sensor Measurement
  - Data type ID: 1050
  - Broadcasting in 10 Hz
- Compatible with Ardupilot and PX4 DroneCAN driver
- US-D1 measurement decoding

[block:parameters]
{
  "data": {
    "h-0": "US-D1 Measurement Reading",
    "h-1": "DroneCAN Message Field",
    "0-0": "Range (in meter)",
    "0-1": "uavcan.equipment.range_sensor.Measur  \nement.range",
    "1-0": "SNR (in dB)",
    "1-1": "uavcan.equipment.range_sensor.Measur  \nement.field_of_view"
  },
  "cols": 2,
  "rows": 2,
  "align": [
    "left",
    "left"
  ]
}
[/block]


Example of US-D1 data in DroneCAN GUI:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3d7b8252d4db08e2ab8231a6a7567736030f936a955eb48b8a26e67b3ddbc20d-Screenshot_2026-01-27_at_1.41.44_AM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]