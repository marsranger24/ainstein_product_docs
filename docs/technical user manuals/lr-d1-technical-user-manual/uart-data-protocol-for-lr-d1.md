---
title: UART Data Protocol for LR-D1
deprecated: false
hidden: true
metadata:
  robots: index
---
## 5. UART Data Protocol For LR-D1:

- Protocol: UART 
- I/O Standard: RS-232 (Default) and RS-422 (Per Request)
- Baud Rate: 115200 b/s
- Data length: 8 bits, plus one start bit and one stop bit, and no parity bit  
  Caution! If the data received for the malfunction alert code is not equal to 0x0000 (Normal  
  function) for data 5 and data 6 in the table below, then please check the malfunction alert  
  code table in the Appendix 1 for details.

**Caution!** If the data received for the malfunction alert code is not equal to 0x0000 (Normal  
function) for data 5 and data 6 in the table below, then please check the malfunction alert  
code table in the Appendix 1 for details.

**Table 2: Data Packet Definition**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc27eb1164e796b22c5b9a2a6ad0dcef83de591be9eeeb945b1b2fb34c67c53d-Screenshot_2026-01-22_at_12.32.25_AM.png",
        "",
        ""
      ],
      "align": "left"
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

<br />

<br />

<br />

<br />

<br />

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1460749ff2b05769e39818d027af762290953847ab8f20c259e6c72e93b5d641-Screenshot_2026-01-22_at_12.32.55_AM.png",
        "",
        ""
      ],
      "align": "left"
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

**Note:**

1. Please see Appendix 1 for details about malfunction information.
2. Altitude Data Parse: Altitude = (high_h \* 256) + high_l; unit: 0.01 m (cm); Type: Unsigned  
   \*\*\_Note_:\*\* If ‘Out of Range Indication’ is 0, the altitude will show ‘0.’
3. Velocity Data Parse: Velocity = (speed _h \* 256) + speed \_l; unit: 0.01m/s; Type: Signed  
   SNR Data Parse: SNR = snr1; unit: dB; Type: Unsigned  
   \*\*\_Note_\*\*: If ‘Out of Range Indication’ is 0, the velocity and SNR will show ‘0.’
4. Out of Range Behavior (Radar Measurement Health):
   - 0: Invalid Altitude, the radar reported altitude health is ‘Invalid’.
   - 1: Valid Altitude, the radar reported altitude health is ‘Valid’.
5. Reserved Byte: Not applied in current version and default as 0xFF.  
   **_Note_**: In the Beta version firmware, Reserved Bytes may be filled with values other than  
   0xFF for evaluation purposes.
6. We use a 16-bit integer to indicate the LR-D1’s altitude reading in centimeters, therefore  
   the maximum valid altitude would be 65535 cm (655.35 m). If the actual altitude is  
   greater than that, altitude reading overflow would occur, and will report ‘Altitude  
   reading overflow’ Malfunction Alert.
7. There are two data sections in the LR-D1 that are related to the Radar Measurement’s  
   validity (See the example in the flow chart):

a. Data 12 Altitude Health: This is an absolute criteria. Users _MUST NOT_ use radar’s measurement if this data reports ‘_Invalid_’.

b. Data 5~6 Malfunction: This is a relative criteria. Users _SHOULD_ consider the application to determine whether to keep using radar’s measurement or discard it. 

**For example:**

i. ‘Altitude reading overflow’ - Users might discard the altitude reading or  
consider the altitude reading plus 65535 cm.

ii. ‘Voltage alert’ - Users might discard the radar’s measurement reading or  
keep using it temporarily and contact Ainstein for more details.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ee8d45a3fcf19f5c89f73b33c9c8316d1d33b1dbcb5b77b5c4f7bfc21361fc18-Screenshot_2026-01-22_at_12.39.47_AM.png",
        "",
        ""
      ],
      "align": "left",
      "border": true
    }
  ]
}
[/block]