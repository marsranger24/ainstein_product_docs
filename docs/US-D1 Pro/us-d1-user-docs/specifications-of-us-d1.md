---
title: Specifications of US-D1
excerpt: >-
  Publicly shareable specifications as a result of a mature product (these are
  not requirements).
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
  pages:
    - type: basic
      slug: installation-of-us-d1
      title: Installation of US-D1
---
[block:api-header]
{
  "title": "Specifications of US-D1"
}
[/block]

[block:parameters]
{
  "data": {
    "0-0": "Frequency\nBand",
    "0-1": "24 GHz",
    "1-0": "Bandwidth",
    "2-0": "Minimum Operating Altitude",
    "3-0": "Maximum Operating Altitude",
    "4-0": "Altitude Precision",
    "5-0": "Field of View",
    "6-0": "Interface",
    "7-0": "Update Rate",
    "8-0": "Supply Voltage",
    "9-0": "Power Consumption",
    "10-0": "Operational Temperature Range",
    "11-0": "Size",
    "12-0": "Weight",
    "13-0": "Environmental Conditions",
    "1-1": "190 MHz",
    "2-1": "0.5 meters",
    "3-1": "50 meters",
    "4-1": "6.0cm (< 1m), 4.0cm (> 1m)\n­",
    "5-1": "43 °  x  30 °",
    "6-1": "UART, CAN",
    "7-1": "UART: 82 Hz \nCAN : 86 Hz\"",
    "8-1": "5V~13V DC (5.5V recommended)",
    "9-1": "2W(at 5 Volts DC input)",
    "10-1": "-20 °C ~ 65 °C*",
    "11-1": "108 x 79 x 20 millimeters",
    "12-1": "110 grams",
    "13-1": "IP67(with sealant)"
  },
  "cols": 2,
  "rows": 14
}
[/block]
  * All specs above are measured under the environment of 35 °C temperature, standard atmospheric pressure and humidity, without any Electromagnetic Interference (EMI).

  * Operational Temperature Range indicates radar works properly in this range. If operating temperature goes beyond this range, radar might not be accurate and can suffer mechanical damage. 

  * Radar unit can be shipped with either CAN or UART for it’s output data protocol.

  * Operational Temperature Range is based off of the hardware’s subcomponent specifications.  Actual operational testing is still pending.  
[block:embed]
{
  "html": "<iframe src=\"https://drive.google.com/viewerng/viewer?url=https%3A//ainstein.ai/wp-content/uploads/2020/10/US-D1-Data-Sheetv2.pdf&embedded=true\" width=\"600\" height=\"780\" style=\"border: none;\"></iframe>",
  "url": "https://ainstein.ai/wp-content/uploads/2020/10/US-D1-Data-Sheetv2.pdf",
  "title": null,
  "favicon": "https://ainstein.ai/favicon.ico"
}
[/block]