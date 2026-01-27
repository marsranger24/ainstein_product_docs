---
title: Hardware Interface
deprecated: false
hidden: true
metadata:
  robots: index
---
## 6. US-D1 Pro Hardware Interface

US-D1 Pro’s connector and its receptacle are automotive grade and have the IP69K rating.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7c27ffe3c95326038c4666ad282cc9b07d0337a528530dc04b9eb1235d2c8283-Screenshot_2026-01-27_at_4.01.47_AM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true,
      "caption": "**Figure 5.1: US-D1 Pro connector**"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fec24848504196ec2a44ef3c1ef1a91fa30a444e84a8f71608022bd69ee313a9-Screenshot_2026-01-27_at_4.02.21_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 6.2: US-D1 Pro Connector’s Receptacle - MOLEX-349671001**"
    }
  ]
}
[/block]


<br />

**Table 6.1: Pinout Definition**

[block:parameters]
{
  "data": {
    "h-0": "Pin",
    "h-1": "Definition",
    "h-2": "Function",
    "h-3": "Remark",
    "0-0": "1",
    "0-1": "CANL_PRI",
    "0-2": "Private CAN-L  \nlow",
    "0-3": "For Private CAN channel, an  \nexternal 120Ω resistor is required",
    "1-0": "2",
    "1-1": "CANH_PRI",
    "1-2": "Private CAN-H high",
    "1-3": "For Private CAN channel, an  \nexternal 120Ω resistor is required",
    "2-0": "3",
    "2-1": "CANL_PUB",
    "2-2": "Public CAN-L low",
    "2-3": "For the DroneCAN channel; 120Ω resistor requirement is up to the bus setting",
    "3-0": "4",
    "3-1": "CANH_PUB",
    "3-2": "Public CAN-H  high",
    "3-3": "For the DroneCAN channel; 120Ω resistor requirement is up to the bus setting",
    "4-0": "5",
    "4-1": "NC",
    "4-2": "none",
    "4-3": "",
    "5-0": "6",
    "5-1": "NC",
    "5-2": "none",
    "5-3": "",
    "6-0": "7",
    "6-1": "NC",
    "6-2": "none",
    "6-3": "",
    "7-0": "8",
    "7-1": "GND_IN",
    "7-2": "Power ground",
    "7-3": "The power ground and signal ground are short-circuited and isolated from the shell (to improve ESD anti-interference ability)",
    "8-0": "9",
    "8-1": "NC",
    "8-2": "none",
    "8-3": "",
    "9-0": "10",
    "9-1": "DC_IN",
    "9-2": "Power input",
    "9-3": "9V～16V DC Input"
  },
  "cols": 4,
  "rows": 10,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]