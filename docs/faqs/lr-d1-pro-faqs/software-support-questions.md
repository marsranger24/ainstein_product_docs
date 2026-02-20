---
title: Software Support Questions
deprecated: false
hidden: false
metadata:
  robots: index
---
> 📘 Note that customer questions are in **bolded** and _italicized_ while Ainstein responses are not.

## Communication Protocol

**_I. Can the interface type be changed?_**

Yes, but the interface type is not configurable from the user's end. Users must select the interface when placing their order. Ainstein will pre-flash and pre-configure the LR-D1 Pro from the manufacturing line. Users are suggested to reach out to [support@ainstein.ai](mailto:support@ainstein.ai) if they have any inquiries regarding the interface of their current units.

## Serial connection/Installation/Calibration (CAN/TTL)

**_I. Setup:  
The Serial (TTL) communication using pins 3 and 4 to the flight controller is being used.  
The serial baud rate is 115200 Kbps.  
The Voltage to the radar is 11 V and the current it is deriving is 1.05 A.  
The data packets being available over the serial from the radar are seen._**

**_Issue:  
All of the data packets have the value 0x77._**

**_Questions:_**

- **_Does the radar need an acknowledgement over the serial on connection?_**
- **_Is there an initialization stage/calibration setup for the radar?_**
- **_Are there any suggestions regarding why this might be?_**
- **_When examining the data packets, what could be the cause for all of them having the value of 0x77?_** 
- **_Does the radar need an acknowledgement over the serial on connection?_** 
- **_Is there an initialization stage/calibration setup for the radar?_**

The LR-D1 Pro is ready for use upon receipt, so there will be no need for an initialization stage/calibration setup.

Check that pin 3 (Tx) is connected to the Rx of the controller and pin 4 (Rx) is connected to the Tx. Use Ainstein’s GUI and test tool to check the performance.

**_II. What is the connection setup through both CAN and TTL?_**

Connection of the LR-D1 Pro with the CAN protocol:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e061fa368534b0fc9d72f3263095bc294e5106d6ec2a785b765ea1d763e4a24b-Screenshot_2026-01-26_at_7.36.01_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/52b516aea2028a74f5dbd03a30deb8e92f882c3706690c65f5806811cb32e5f6-Screenshot_2026-01-26_at_7.36.15_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


As seen in the image above, there is a resistor in the Peak CAN between pins 2 and 7. It is required to have the 120-Ohm resistor in the system, as the US-D1 does not have one internally.

In the past, there have been instances of having some missing files to use the Peak CAN with the radars. Ainstein suggests reinstalling PEAK and selecting PCAN-Basic in the install.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/348c9b51213da7b9f81e31a9adb6e8d4dd9111f4d5cf0544ad245d2fb027f9d6-Screenshot_2026-01-26_at_7.37.16_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Connection via TTL:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f3311b5338a51ae53da85f376e192e186e982e7deecc38c16fcc8d73474e138-Screenshot_2026-01-26_at_7.38.13_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


In this instance, the system was compatible with the RS-232 communication protocol, so it is very important to verify the correct communication protocol when receiving a unit.