---
title: 'Technical Specifications '
deprecated: false
hidden: false
metadata:
  robots: index
---
**Table 1: Specifications**

[block:parameters]
{
  "data": {
    "h-0": "Measurement",
    "h-1": "Specs",
    "0-0": "Frequency Band",
    "0-1": "24 GHz",
    "1-0": "Bandwidth",
    "1-1": "190 MHz",
    "2-0": "Minimum Operating Altitude",
    "2-1": "0.5 meters",
    "3-0": "Maximum Operating Altitude",
    "3-1": "50 meters",
    "4-0": "Altitude Precision",
    "4-1": "6.0cm (0.5m - 1m), 4.0cm (>1m), 2% (>10m)",
    "5-0": "Field of View",
    "5-1": "43 ° x 30 °",
    "6-0": "Interface",
    "6-1": "UART, CAN, DroneCAN",
    "7-0": "Update Rate",
    "7-1": "100 Hz (UART and Private CAN), 10 Hz (DroneCAN)",
    "8-0": "Supply Voltage",
    "8-1": "5V~13V DC (5.5V recommended)",
    "9-0": "Power Consumption",
    "9-1": "2W",
    "10-0": "Operational Temperature Range",
    "10-1": "\\-20 °C ~ +65 °C\\*",
    "11-0": "Size",
    "11-1": "108 x 79 x 20 millimeters",
    "12-0": "Weight",
    "12-1": "110 grams",
    "13-0": "Environmental Conditions",
    "13-1": "IP67 (with sealant applied during the manufacturing  \nprocess)"
  },
  "cols": 2,
  "rows": 14,
  "align": [
    "left",
    "left"
  ]
}
[/block]


**Notes:**

- All specs above are measured under the environment of 35 °C temperature, standard atmospheric pressure and humidity, without any Electromagnetic Interference (EMI).
- Operational Temperature Range indicates radar works properly in this range. If operating temperature goes beyond this range, radar might not be accurate and can suffer mechanical damage.
- The radar unit can be shipped with either CAN, DroneCAN or UART for its output data protocol.
- \*Operational Temperature Range is based on the hardware’s subcomponent specifications. Actual operational testing is still pending.