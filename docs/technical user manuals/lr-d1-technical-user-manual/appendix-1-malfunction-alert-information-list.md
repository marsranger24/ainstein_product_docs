---
title: 'Appendix 1: Malfunction Alert Information List'
deprecated: false
hidden: true
metadata:
  robots: index
---
**Caution!** If the data received for the malfunction alert code is not equal to 0x00 (Normal function) for data 5 and data 6 found in **Table 2: Data Packet Definition**, then please do not use the data packet and filter it out.

There are four types of alerts open to the end users. The type of alert can be distinguished by its special code below.

There are two Bytes of data reserved for the Malfunction Alert. All four types of alerts are represented by a bit in this Byte. For example:

- 0x0001 (0b0000000000000001) of the temperature alert is represented by the bit-0  
  of the Malfunction Alert Byte;
- 0x0002 (0b0000000000000010) of the voltage alert is represented by the bit-1 of the  
  Malfunction Alert Byte;
- 0x4000 (0b0100000000000000) of the IF signal saturation alert is represented by  
  the bit-6 of the Malfunction Alert Byte;
- 0x8000 (0b1000000000000000) of the altitude reading overflow alert is represented  
  by the bit-7 of the Malfunction Alert Byte;

Also, some of these Malfunction Alerts might be combined. For example:

- 0x0003 (0b0000000000000011) of the temperature alert and the voltage alert
- 0x4003 (0b0100000000000011) of the temperature alert, the voltage alert, and the IF signal saturation alert

For obsolete Firmware (before v18.x.x.x), please contact Ainstein for a solution.

**For Firmware from v18.X.X.X:**

[block:parameters]
{
  "data": {
    "h-0": "Malfunction Alert Info",
    "h-1": "Malfunction  \nAlert Code",
    "h-2": "Possible Reasons",
    "h-3": "Suggestion",
    "0-0": "MCU Temperature alert",
    "0-1": "0x0001",
    "0-2": "Error in the  \ndevice or  \nambient  \ntemperature is  \nout of LR-D1’s  \noperational  \ntemperature",
    "0-3": "Stop using and contact  \nAinstein",
    "1-0": "MCU Voltage alert",
    "1-1": "0x0002",
    "1-2": "Error in the device",
    "1-3": "Stop using and contact  \nAinstein for evaluation.",
    "2-0": "IF temperature alert",
    "2-1": "0x0010",
    "2-2": "Error in the  \ndevice or ambient  \ntemperature is  \nout of the LR-D1’s  \noperational  \ntemperature",
    "2-3": "Improve the heat dissipation.  \nIf the issue still remains, stop  \nusing and contact Ainstein  \n  \nNote: Long time operation in  \nthe static scenario (e.g. indoor  \ntesting) might bump the  \ntemperature significantly and  \nreport this alert code",
    "3-0": "IF signal saturation  \nalert",
    "3-1": "0x0080",
    "3-2": "The reflection  \nsignal received  \nby LR-D1 is  \noverloaded",
    "3-3": "Occurs when LR-D1 is within  \n1.4m of the ground.  \nCheck if there is any other  \ntarget within LR-D1’s FoV",
    "4-0": "Software alert",
    "4-1": "0x0100",
    "4-2": "Malfunctions  \noccur in the  \nsoftware",
    "4-3": "Stop using and contact  \nAinstein",
    "5-0": "Altitude reading  \noverflow alert",
    "5-1": "0x0400",
    "5-2": "The altitude  \nreading is  \ngreater than  \nthe maximum  \ninteger of  \n16-bit (655.35  \nmeters)",
    "5-3": "Occurs when LR-D1 detects  \nthe altitude is greater than  \n655.35 meters.",
    "6-0": "Voltage alert",
    "6-1": "0x8000",
    "6-2": "Error in device  \nby over-voltage  \nor under-voltage",
    "6-3": "Check the supply-voltage.  \nRecommended voltage range  \nis 12~28V  \n  \nNote: Minimum of 10V of  \nsupply-voltage is sufficient to  \noperate the device, however  \nit might trigger this alert code."
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