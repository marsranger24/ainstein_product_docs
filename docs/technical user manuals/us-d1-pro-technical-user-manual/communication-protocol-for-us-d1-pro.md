---
title: Communication Protocol For US-D1 Pro
deprecated: false
hidden: false
metadata:
  robots: index
---
## 5. Communication Protocol For US-D1 Pro

US-D1 Pro has two channels of CAN interface in hardware, and it does support two CAN communication protocols: Private CAN and DroneCAN.

## 5.1 Private CAN

## 5.1.1 Private CAN Specification

- CAN Interface Type - Default of CAN 2.0
- Baud Rate - Default of 1 Mb/s in CAN 2.0
- Support Frame Format and ID - Default of Extended Frame with 0x90002
- Standard: CAN FD (maintains backward compatibility with CAN 2.0), ISO  
  11898-1

The type of CAN frame used and CAN ID of the device can be customized. The CAN frame Data Field is defined in the table below.

**Table 5.1: Private CAN Data Format Definition**

| From (Byte) | US-D1 Altimeter (Data) | To/Receiver (Note)                     |
| :---------- | :--------------------- | :------------------------------------- |
| 1           | 0x\*\*                 | Altitude (Most Significant 8 Bits) [1] |
| 2           | 0x\*\*                 | Altitude (Least Significant 8 Bits)    |
| 3           | 0x\*\*                 | SNR(Most Significant 8 Bits) [2]       |
| 4           | 0x\*\*                 | SNR(Least Significant 8 Bits)          |
| 5           | 0x\*\*                 | Confidence [3]                         |
| 6           | 0x\*\*                 | Velocity [4]                           |
| 7           | 0x\*\* (4-bit)         | Counter [5]                            |
| 8           | (Reserved)             | (Reserved)                             |

**Notes:**

1. Altitude: It is the AGL altitude reading. Unit: centimeter (0.01 m); Unsigned value;
2. SNR: It is the Signal-to-Noise Ratio for the reflection signal. Unit: dB; Unsigned value; Note: there is no Absolute Threshold in SNR for users’ reference
3. Confidence: It indicates the radar’s measurement confidence in percentage, its range is from 0 to 100. Unit: %.
   1. Absolute threshold: 0 - Invalid detection
   2. Other: 1 ~ 100 - Reference for users
4. Velocity: It is the vertical velocity (ascending and descending); Unit: 0.1 m/s (0.1 meter per second); Range from -6.9 m/s to +6.9 m/s;
5. Counter: It indicates the CAN message’s counter, and automatically increments by 1 for a new CAN message. Range from 0 to 1

## 5.1.2 Private CAN Configuration Options

**Table 5.2: Private CAN Configurable Parameter**

[block:parameters]
{
  "data": {
    "h-0": "No.",
    "h-1": "Parameter",
    "h-2": "Configurable Range",
    "h-3": "Default",
    "0-0": "1",
    "0-1": "CAN Interface Type",
    "0-2": "- CAN 2.0  \n- CAN FD",
    "0-3": "CAN 2.0",
    "1-0": "2",
    "1-1": "Frame Format",
    "1-2": "- Standard Frame  \n- Extended Frame",
    "1-3": "Extended Frame",
    "2-0": "3",
    "2-1": "ID",
    "2-2": "- Standard Frame:  \n  0x000 ~ 0x7FF；  \n- Extended Frame:  \n  0x00000000 ~  \n  0x1FFFFFFF",
    "2-3": "0x90002",
    "3-0": "4",
    "3-1": "Baud Rate",
    "3-2": "- CAN 2.0:  - 500 Kbps  \n- 1000 Kbps  - CAN FD:  - 500 Kbps  \n- 1000 Kbps",
    "3-3": "1000 Kbps",
    "4-0": "5",
    "4-1": "Bit Rate Switch",
    "4-2": "- CAN FD:  - 500 Kbps  \n- 1000 Kbps  \n- 2000 Kbps  \n- 5000 Kbps",
    "4-3": "1000 Kbps"
  },
  "cols": 4,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

## 5.2 DroneCAN Specification

- CAN Interface Type: CAN 2.0
- Baud Rate – Default of 1 Mb/s
- CAN Standard: CAN 2.0B
- Transfer Priority – Default of 24
- Source Node ID – Default ID 32
- Node Status Message
  - Data type ID: 341
  - Broadcasting in 1 Hz
- Range Sensor Measurement
  - Data type ID: 1050
  - Broadcasting in 20 Hz
  - Sensor ID
    - Default of 1
    - Configuration Range: 0-255

Compatible with Ardupilot and PX4 DroneCAN driver. Follow the official instructions to make the autopilot configuration.

## 5.2.1 DroneCAN Node Status

**Table 5.3: Public CAN (DroneCAN) Node Status Data Format Definition**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d43f42a0cf2115c1c87bb0b9d3f76ea6dd4e7e776cbf205a382d7c3e5663b438-Screenshot_2026-01-27_at_3.51.50_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d36a21f1aa431ac0ad8bce51e1b3e61fee2bc370aac8a8b39c8390c179f97506-Screenshot_2026-01-27_at_3.52.22_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## 5.2.2 DroneCAN Sensor Measurement

**Table 5.4: Public CAN (DroneCAN) Sensor Measurement Data Format Definition**

[block:parameters]
{
  "data": {
    "h-0": "US-D1 Pro DroneCAN sensor  \nmeasurement spec",
    "h-1": "DroneCAN message field",
    "h-2": "Setting",
    "0-0": "Timestamp for synchronization",
    "0-1": "timestamp",
    "0-2": "US-D1 Pro is a Time Slave node; it synchronizes the timestamp with the Time Master node on the bus.  \nIf there is no master clock node, it reports 0",
    "1-0": "Sensor ID",
    "1-1": "sensor_id",
    "1-2": "Default in 1;  \nConfigurable",
    "2-0": "Beam Orientation",
    "2-1": "beam_orientation_in_body_  \nframe",
    "2-2": "N.A. Fixed in 0",
    "3-0": "Field of View",
    "3-1": "field_of_view",
    "3-2": "**Note:**   \n  \n- US-D1 Pro ‘SNR’ data in dB  \n  filled in this field  \n- It may be changed to  \n  ‘Confidence’ in the future firmware as it is a more reliable parameter for the  \n  user to determine the validity of the radar’s detection",
    "4-0": "Radar’s Sensor Type",
    "4-1": "sensor_type",
    "4-2": "3",
    "5-0": "Radar’s Reading Type",
    "5-1": "reading_type",
    "5-2": "It is fixed as 1 in all cases",
    "6-0": "Range",
    "6-1": "Range",
    "6-2": "US-D1 Pro range data in meters"
  },
  "cols": 3,
  "rows": 7,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

## 5.2.3 DroneCAN Configuration Option

**Table 5.5: DroneCAN Configurable Parameter**

[block:parameters]
{
  "data": {
    "h-0": "No.",
    "h-1": "Parameter",
    "h-2": "Configurable Range",
    "h-3": "Default",
    "0-0": "1",
    "0-1": "Transfer Priority",
    "0-2": "0~31",
    "0-3": "24",
    "1-0": "2",
    "1-1": "Node ID",
    "1-2": "0~127    \n  \n- 0 - Reserved for DNA  \n- 126, 127 - Reserved for debug",
    "1-3": "32",
    "2-0": "3",
    "2-1": "Sensor ID",
    "2-2": "0~255",
    "2-3": "1",
    "3-0": "4",
    "3-1": "Baud Rate",
    "3-2": "- CAN 2.0:  - 500 Kbps  \n- 1000 Kbps  - CAN FD:  - 500 Kbps  \n- 1000 Kbps",
    "3-3": "1000 Kbps"
  },
  "cols": 4,
  "rows": 4,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

**NOTE:**

- When connecting the US-D1 Pro to ArduPilot, users must ensure that the RNGFNDX_ADDR parameter matches the sensor ID of the radar (i.e., if Sensor ID = 1, then RNGFNDX_ADDR = 1)