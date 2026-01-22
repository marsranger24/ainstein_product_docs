---
title: Hardware Interface
deprecated: false
hidden: true
metadata:
  robots: index
---
## 8. Hardware Interface

There are 4 supported interfaces in the LR-D1 Pro. All 4 interfaces share the same pin  
definition as indicated in the table below.

**Table 4: Pin Out Definition**

<br />

[block:parameters]
{
  "data": {
    "h-0": "Pin",
    "h-1": "Wire Color",
    "h-2": "Pin Name",
    "h-3": "Function",
    "h-4": "Note",
    "0-0": "1",
    "0-1": "Red",
    "0-2": "VCC",
    "0-3": "Input Voltage",
    "0-4": "10 - 32 V  \nPower \\< 14W",
    "1-0": "2",
    "1-1": "Red",
    "1-2": "VCC",
    "1-3": "Input Voltage",
    "1-4": "10 - 32 V  \nPower \\< 14W",
    "2-0": "3",
    "2-1": "Blue",
    "2-2": "RS-422 T+ /  \nRS-232_T",
    "2-3": "RS422: TX+  \nRS232: TX  \nCAN_H  \nTTL: TX  \nRS485: TX",
    "2-4": "Default Setting:  \nRS232",
    "3-0": "4",
    "3-1": "Brown",
    "3-2": "RS-422 T- /  \nRS-232 R",
    "3-3": "RS422: TX-  \nRS232: RX  \nCAN_L  \nTTL: RX  \nRS485: RX",
    "3-4": "Default Setting:  \nRS232",
    "4-0": "5",
    "4-1": "White",
    "4-2": "RS-422 R-",
    "4-3": "RS422: RX-",
    "4-4": "Leave unwired  \nfor RS232",
    "5-0": "6",
    "5-1": "Green",
    "5-2": "RS-422 R+",
    "5-3": "RS422: RX+",
    "5-4": "Leave unwired  \nfor RS232",
    "6-0": "7",
    "6-1": "Black",
    "6-2": "GND",
    "6-3": "Ground",
    "6-4": "",
    "7-0": "8",
    "7-1": "Black",
    "7-2": "GND",
    "7-3": "Ground",
    "7-4": ""
  },
  "cols": 5,
  "rows": 8,
  "align": [
    "left",
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

**Figure 5: LR-D1 Pro Hardware Pinout Diagram**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9735460fe48333dd9ee3d97411fa9250252a9036ebd9e42585765bf200cdf818-Screenshot_2026-01-22_at_2.54.58_AM.png",
        "",
        ""
      ],
      "align": "left",
      "border": true
    }
  ]
}
[/block]


<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

**Note:** Power input pins 1 and 2 share continuity and therefore a diode must be added to isolate PWR-IN-A and PWR-IN-B from each other, if isolating PWR-IN-A and PWR-IN-B is required.