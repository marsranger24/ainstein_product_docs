---
title: Software Support FAQs
deprecated: false
hidden: false
metadata:
  robots: index
---
> 📘 Note that customer questions are **bolded** and _italicized_ while Ainstein responses are not.

## LR-D1 Communication Interface

**_I. Can the communication type be changed from RS232 to RS422 (firmware update or by Program)?_**

Since RS232 and RS422 require different hardware, they can not be changed through a firmware update.

## LR-D1 Interface (Error/Alert Warnings)

**_I. Is it possible to receive alert information from the radar altimeter, and are any messages displayed?_**

The LR-D1 outputs alert information about the following alerts over the serial port:

[block:parameters]
{
  "data": {
    "h-0": "Malfunction Alert Code",
    "h-1": "Malfunction Alert Info",
    "h-2": "Possible Causes",
    "h-3": "Suggestion",
    "0-0": "0x0001",
    "0-1": "Processor Temperature Warning",
    "0-2": "The device has an error or the device is being used beyond environmental limits.",
    "0-3": "Confirm whether the environmental state is limited, or contact customer service for maintenance.",
    "1-0": "0x0002",
    "1-1": "Processor Voltage Warning",
    "1-2": "The device has an error or the device is being used beyond environmental limits.",
    "1-3": "Stop using and contact customer service for repair.",
    "2-0": "0x0010",
    "2-1": "RF Temperature Warning",
    "2-2": "The device has an error or the use of environmental limits.",
    "2-3": "Confirm whether the environmental state is limited, or contact customer service for maintenance.",
    "3-0": "0x0080",
    "3-1": "IF Signal Saturation Warning",
    "3-2": "The reflected radar signal is too high. Multipath reflections will cause erroneous measurements.",
    "3-3": "It is normal if the height above the ground is less than 20 meters.  \nCheck if there are obstacles on the radar surface.",
    "4-0": "0x0100",
    "4-1": "Software Operational Status Warning",
    "4-2": "The software is malfunctioning.",
    "4-3": "Stop using and contact customer service for repair.",
    "5-0": "0x0400",
    "5-1": "Out-of-Range Warning",
    "5-2": "The aircraft is above 655m in altitude.",
    "5-3": "Set overflow alarm when target 1 height is greater than 655.35 meters.  \nAfter detecting this alarm, the actual altitude needs to be the reported altitude value + 655.35 meters.",
    "6-0": "0x8000",
    "6-1": "Voltage Warning",
    "6-2": "The device has an error or the device is being used beyond environmental limits.",
    "6-3": "Stop using and contact customer service for repair."
  },
  "cols": 4,
  "rows": 7,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

## Malfunction Code Questions

**\_II. What is the 16-bit integer representation seen in this text from the user manual:**"

**“Velocity Data Parse for Integrated: Velocity = (high3_h \* 256) + high3_l, unit: 0.01 m (cm)?      A 16-bit integer is used to indicate the LR-D1’s altitude reading in centimeters; therefore, the maximum valid altitude would be 65535 cm (655.35 m). If the actual altitude is greater than 655.35 m, an altitude reading overflow error would occur.”_**

**_Is it using 2’s complement representation?_**

It is using 2's complement. The 16-bit integer is the number of selected bits for the 2's complement. It works for marking the maximum and minimum possible altitude and velocity that the radar system can read.

**_1. Should the radar altimeter not be used and considered unhealthy when the following errors are reported?_**

From firmware v19.0.0.1, two data sections in the LR-D1 are related to the Radar Measurement’s validity (Please see an example in the flow chart):

1. Data 12 Altitude Health: This is an absolute criterion. Users MUST NOT use the radar’s measurement if this data reports ‘Invalid.’
2. Data 5~6 Malfunction: This is a relative criterion. Users SHOULD consider the application to determine whether to keep using the radar’s measurement or discard it.  For example:
   1. ‘Altitude reading overflow’ - Users might discard the altitude reading or consider the altitude reading plus 65535 cm.
   2. ‘Voltage alert’ - Users might discard the radar’s measurement reading or keep using it temporarily and contact Ainstein for more details.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5cc5509a5e3fa5a041a4fd1be344e0e3ebd74aafa3a71655a8a4c0ec8bb6a4a2-Screenshot_2026-01-26_at_7.14.50_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


**_2. When the following error is detected, can the measurement be discarded, but the equipment be considered healthy?_**

- 0x0080 IF Signal Saturation Warning
- 0x0400 Altitude Reading Overflow Warning

Yes, users can assign the matching altitude and velocity as invalid.

## LR-D1 Low SNR

**_What could be the cause of the LR-D1 providing incorrect altitude values and an unhealthy SNR? Reflashing the firmware did not resolve the issue._**

There could potentially be something wrong with the radar configuration. After updating the firmware, the RF parameters should be reset to the default values by clicking the “Read” button followed by the “Reset” button. Once the message "Reset default parameter success" is displayed, power cycle the radar and test it again.

## LR-D1 No Communication with Unit

**_I. What is the first step in an instance where bad behavior is observed?_**

The first step would be to check the device’s SN and interface type (RS-232 or RS-422).

**II. The LR-D1 can be read using the Drone GUI Tool, but it is not possible to check its firmware or communicate with the unit using the FW GUI. What could be the cause of this?**

Because data can be received from the unit but cannot connect to the GUI, it is possible that the radar's RX cable is damaged, but the TX is operating correctly. The recommendation is to open the unit and inspect the interior wires, specifically ensuring that pin 4, the white wire, is not damaged. Performing a reflash could potentially fix the issue as well.