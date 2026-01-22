---
title: Software Instructions
excerpt: >-
  The settings of the LR-D1 Pro can be modified using the LR-D1 Pro Software
  Tool. The Software Tool can be downloaded on the “Downloads” tab of the LR-D1
  Pro product page on Ainstein’s website. Instructions for connecting the LR-D1,
  updating the LR-D1 firmware, and changing the interface standard of the serial
  port are detailed below.
deprecated: false
hidden: true
metadata:
  robots: index
---
## 10.1 Connecting the LR-D1

1. After downloading the LR-D1 Pro Software Tool, open its containing folder and  
   launch the executable, “LR-D1-PRO_V97.237.1.0”.

**Figure 5: LR-D1 Pro Software Tool Executable**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a9f6687933c112486aebec0af0e23516ef6fea0fc2c4287340fb586bd0d78cc-Screenshot_2026-01-22_at_3.03.26_AM.png",
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

<br />

<br />

<br />

<br />

<br />

2. Once launched, navigate to the upper-left corner of the interface. In the “PORT”  
   dropdown, select the serial port the radar is using.
3. In the “BAUD” dropdown, select a baud rate of 115200 Kbps.
4. In the “RVER” dropdown, select the version of your device. Note: If using the  
   LR-D1 Pro, select “Gen3”, if using LR-D1, select “Gen2”.
5. After ensuring the connection between the radar device and your computer over  
   the selected serial port, click “Connect”.

**Figure 6: LR-D1 Pro Software Tool - Successful Connection**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/545eedacdc2f6ad35237a1a52e8d0eb7f870122057a7d88deb364878097241a6-Screenshot_2026-01-22_at_3.05.40_AM.png",
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

<br />

<br />

<br />

<br />

The “BL.Ver.” text field displays the bootloader version of the radar. The “PS.Ver.” text field displays the firmware version of the radar. The “Status” field on the left side of the window shows information about the radar’s temperature, voltage, current, and attitude angle. Select the “Read” button to display the current “Status” information.

**Figure 7: LR-D1 Pro Software Tool - Interface & Status Information**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d6a73bbc674f61bfbde4f71a30da946a9d0e011caba9c41570c21d746566985-Screenshot_2026-01-22_at_3.07.22_AM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


## 10.2 Firmware Update Instructions

To update the firmware version of your LR-D1 Pro device to the latest release, follow the instructions below.

1. Connect the LR-D1 Pro to the LR-D1 Pro Software Tool as described in Section 9.1.
2. Navigate to the “Firmware” tab of the main window of the tool.
3. In the “TYPE” dropdown box, select which component of the radar you would like to update. For the 24 GHz radar, select “24G”, for the 60 GHz radar component, select “60G”.

**Figure 8: LR-D1 Pro Software Tool - Firmware Window**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af4c6c30dbeb15f59246b0d06d92c075795e274972bdd13b12c7dac4567417d7-Screenshot_2026-01-22_at_3.11.30_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


4. Once selected, click the “Browse” button to select your firmware binary flash file in your PC’s directory.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9410efe5e40f556dd2b270a141a04dd41ef6fbcdd4f9767f167f1186a0c8c78a-Screenshot_2026-01-22_at_3.12.32_AM.png",
        "",
        ""
      ],
      "align": "left",
      "border": true
    }
  ]
}
[/block]


**Figure 9: LR-D1 Pro Software Tool - Firmware Selection**