---
title: Technical Specifications
deprecated: false
hidden: true
metadata:
  robots: index
---
## 4. US-D1 Pro Technical Specifications

**Table 1: Specifications**

[block:parameters]
{
  "data": {
    "h-0": "Measurement",
    "h-1": "Specs",
    "0-0": "Operating Altitude  \n(Minimum ~ Maximum)",
    "0-1": "The Minimum Range～120m (1\\*)",
    "1-0": "Altitude Accuracy",
    "1-1": "±0.1m(@≤10m); 1% (@>10m)",
    "2-0": "Operating Velocity (Vertical)",
    "2-1": "\\-6.9 ~ +6.9m/s (2\\*)",
    "3-0": "Field of view (FOV)",
    "3-1": "Azimuth ±20°  \nElevation ±20°",
    "4-0": "Frequency Band",
    "4-1": "24 GHz ISM Band",
    "5-0": "Transmit ERIP",
    "5-1": "13 dBm (3\\*)",
    "6-0": "Update Rate",
    "6-1": "20Hz",
    "7-0": "Recommended Supply Voltage",
    "7-1": "DC 12~14V",
    "8-0": "Supply Voltage Range",
    "8-1": "DC 9~16V",
    "9-0": "Harness/Connector",
    "9-1": "MOLEX-349671001",
    "10-0": "Power consumption",
    "10-1": "3.5W (4\\*)",
    "11-0": "Temperature Range",
    "11-1": "\\-40℃～85℃ (Operational)  \n-55℃～85℃ (Storage)",
    "12-0": "Weight",
    "12-1": "140 g",
    "13-0": "Size",
    "13-1": "101 mm x 76mm x 24.71 mm",
    "14-0": "Reliability",
    "14-1": "Total lifetime operating time: 6,000 hours, reliability: 0.98, operating failure rate: 3.5E-06 per hour.  \n  \nTotal lifetime storage time: 60,000 hours, reliability: 0.98, storage failure rate: 3.8E-07 per hour.  \n  \nTotal lifetime start-up cycles: 4,000 cycles, reliability: 0.98.",
    "15-0": "Interface",
    "15-1": "Two CAN-FD channels  \n  \n- 1st channel for Private CAN message and OTA upgrade  \n  (5\\*)\n- 2nd channel for DroneCAN message and features (6\\*)",
    "16-0": "OTA Upgrade Method",
    "16-1": "- Private CAN by Ainstein’s GUI\n- DroneCAN by tools supports it (DroneCAN GUI, Mission Planner, etc)",
    "17-0": "Protection level",
    "17-1": "IP69K",
    "18-0": "Time Synchronization",
    "18-1": "- DroneCAN - Supported in the node status reporting\n- Private CAN - NOT supported"
  },
  "cols": 2,
  "rows": 19,
  "align": [
    "left",
    "left"
  ]
}
[/block]


**Notes:**

1. This is the Recommended AGL (Above Ground Level) altitude range. The minimum range depends on the actual mounting height and radar’s minimum detection. For now, this minimum range is set as 0.65 meter.
2. This is the maximum unambiguous velocity range. It is recommended to use the velocity detection when the vehicle’s vertical velocity within this range.
3. EIRP is the total transmitter power from US-D1 Pro, including the Transmitting Antenna Gain.
4. This is the mean power consumption in steady operation. The peak power consumption might be greater than it.
5. OTA upgrade via Private CAN is performed by Aintein GUI via wired method.
6. Supported DroneCAN feature and functionality includes, but is not limited to (See details in Section 6.2):  
   a. Export Node Status message  
   b. Export Sensor Measurement message  
   c. Time synchronization  
   d. Node parameter configuration  
   e. Firmware update