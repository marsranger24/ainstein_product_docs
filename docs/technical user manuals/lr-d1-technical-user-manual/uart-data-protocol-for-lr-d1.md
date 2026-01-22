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