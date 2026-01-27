---
title: Hardware Support FAQs
deprecated: false
hidden: true
metadata:
  robots: index
---
> 📘 Note that customer questions are **bolded** and _italicized_, while Ainstein responses are not.

## US-D1 Functionality

_**When determining the altitude reading, how does the radar determine which surface will be used?**_

The terrain surface is a distributed target (over a substantial amount of the US-D1s field of view).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cfe647c9f325ac3193627388aa903fa796412c783c2570649d28fefe8bc3e684-Screenshot_2026-01-26_at_5.14.19_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


The shortest distance to the ground from the altimeter is generally the one providing the strongest SNR return, and the signal fades as users radiate outwards from that point.

## US-D1 Low altitude discrepancy/Multipath Reflections

**_I. What are common causes of noisy or incorrect data from the US-D1?_**

1. An indoor scenario may not be the ideal case to test the US-D1 radar, because there are too many unexpected objects that might affect the radar's performance (multi-path reflection). Moving to the outdoor scenario would be helpful.
2. If there is material within the radar's FOV that is metal or other strong reflection materials, it can possibly affect the radar's performance. Even if it is out of the 43-degree window, there is a possibility of affecting the performance.
3. If the material on the airframe on which the Radar is mounted is metallic or other strong reflection materials, it could also affect the performance, especially in the indoor scenario.

## US-D1 Cable Length

**_I. What is the maximum allowable cable length for the US-D1?_**

Only the offered options are 0.5m and 1m. Maximum length depends on the communication protocol. UART TTL allows for a maximum of 15 m, while CAN has a recommended maximum of 40 m.

## US-D1 Connector/Connection

**_I. What connector is used on the US-D1, and what is the suggested mating connector?_**

Connectors available for the US-D1, including mates:

- Molex
  - Molex 4-pin 2.54mm connector
  - The Molex fits into PCB-mounted 2.54mm Molex Connector Headers, or can be simply used with jumper wires
- JST
  - JST 4-pin 1.25mm female socket connector
  - JST 4-pin 1.25mm outer shroud contact connector

It is recommended to use any 22 AWG shielded cabling.

<br />

**_II. How is the radar properly connected to the test tool to receive output from the software?_**

To use the US-D1 Bench Test Tool GUI, a US-D1 with UART protocol is required, and it should be connected to a PC using a USB-UART TTL converter. Here are the steps to connect the USB-UART TTL converter:

1. Plug in the USB-TTL converter to the USB port.
2. Plug in the TX (green) of the US-D1 into the RX of the USB-TTL converter.
3. Plug in the RX (white) of the US-D1 into the TX of the USB-TTL converter.
4. Connect the power (red) and ground (black) of the US-D1 to a 5V power supply.  
   Note: Ensure that the ground of the US-D1 is shared with the ground of the USB-TTL.  
   When connected to power, the US-D1 should boot at a current of 120 mA  
   for ~6 seconds. After this, the US-D1 will operate at a current of 330 mA at 5V.
5. Open the US-D1 Radar Altimeter Test Tool.

For Firmware Update Tool Instructions and Configuring the US-D1 Parameters, please refer to that section of the US-D1 Technical User Manual.