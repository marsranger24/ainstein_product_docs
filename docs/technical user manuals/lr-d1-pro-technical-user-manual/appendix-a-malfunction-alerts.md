---
title: Appendix A - Malfunction Alerts
deprecated: false
hidden: true
metadata:
  robots: index
---
The alarm code is designed as 2 bytes– a total of 16 bits– each bit representing an alarm  
mode. If all bits are 0, the radar is operating normally. The following 16 types of alarms  
exist. Data5 and data6 in the 32 bytes of data output by the device are alarm data, where  
data5 is the MSB and data6 is the LSB. The received two-byte alarm data needs to be  
converted into 8-bit hexadecimal data, respectively, then compared with the  
hexadecimal alarm code in the table below to determine the alarm definition

**Table 5: Malfunction Alert Information**

[block:parameters]
{
  "data": {
    "h-0": "Malfunction Alert Code",
    "h-1": "Malfunction Alert Info",
    "h-2": "Possible Causes",
    "h-3": "Suggestion",
    "0-0": "0x0001",
    "0-1": "FPGA Temperature Warning",
    "0-2": "Error in the device  \nor ambient  \ntemperature is out  \nof LR-D1 Pro’s  \noperational  \ntemperature  \nrange",
    "0-3": "Confirm whether the  \nambient temperature is  \nbeyond the LR-D1 Pro’s  \nlimit, or contact Ainstein  \nto confirm whether  \nmaintenance is needed",
    "1-0": "0x0002",
    "1-1": "FPGA Voltage Warning",
    "1-2": "The device has an error",
    "1-3": "Stop use and contact Ainstein for repair",
    "2-0": "0x0004",
    "2-1": "60G-SOC Temperature  \nWarning",
    "2-2": "Error in the device  \nor ambient  \ntemperature is out  \nof LR-D1 Pro’s  \noperational  \ntemperature  \nrange.",
    "2-3": "Confirm whether the  \nambient temperature is  \nbeyond the LR-D1 Pro’s  \nlimit, or contact Ainstein  \nto confirm whether  \nmaintenance is needed",
    "3-0": "0x0008",
    "3-1": "60G-SOC Voltage  \nWarning",
    "3-2": "The device has an  \nerror.",
    "3-3": "Stop use and contact  \nAinstein for repair -- He needs a new folder",
    "4-0": "0x0010",
    "4-1": "24G RF Temperature  \nWarning",
    "4-2": "Error in the device  \nor ambient  \ntemperature is out  \nof LR-D1 Pro’s  \noperational  \ntemperature  \nrange",
    "4-3": "Confirm whether the  \nambient temperature is  \nbeyond the LR-D1 Pro’s  \nlimit, or contact Ainstein  \nto confirm whether  \nmaintenance is needed",
    "5-0": "0x0020",
    "5-1": "24G RF Transmit  \nPower Warning",
    "5-2": "The device has an  \nerror",
    "5-3": "Stop use and contact  \nAinstein for repair",
    "6-0": "0x0040",
    "6-1": "Whole Board  \nOvercurrent Warning",
    "6-2": "The device has an  \nerror",
    "6-3": "Stop use and contact  \nAinstein for repair",
    "7-0": "0x0080",
    "7-1": "IF Signal Saturation Warning",
    "7-2": "May be caused by obstacles  \nobstructing the  \nsurface of the  \nradar or the  \nequipment being  \nvery close to the  \nground.",
    "7-3": "Confirm whether obstacles are blocking the surface of the radar. When very close to the ground this alert may be reported even though the device is fully functional. ",
    "8-0": "0x0100",
    "8-1": "24G Software Failure  \nWarning",
    "8-2": "The device has an error.",
    "8-3": "Stop use and contact Ainstein for repair.",
    "9-0": "0x0200",
    "9-1": "60G Software Failure  \nWarning",
    "9-2": "The device has an error.",
    "9-3": "Stop use and contact Ainstein for repair.",
    "10-0": "0x0400",
    "10-1": "Altitude Reading  \nOverflow Warning",
    "10-2": "Altitude reading  \nis greater than the max. integer  \nof 16-bit (655.35 m)",
    "10-3": "Occurs when LR-D1  \ndetects the altitude is  \ngreater than 655.35  \nmeters",
    "11-0": "0x0800",
    "11-1": "Excessive Attitude  \nAngle Warning",
    "11-2": "The radar tilt  \nangle exceeds 20°",
    "11-3": "Adjust the installation  \nangle of the radar and  \nensure that the radar is  \nperpendicular to the  \nground",
    "12-0": "0x1000",
    "12-1": "60G Frame Error  \nWarning",
    "12-2": "The device has an  \nerror",
    "12-3": "Stop use and contact  \nAinstein for repair",
    "13-0": "0x2,000",
    "13-1": "Invalid Altitude  \nWarning",
    "13-2": "Indicates that the  \nradar has not  \ndetected a valid  \npeak value",
    "13-3": "Ensure the LR-D1 Pro is  \nbeing used within  \noperational requirements",
    "14-0": "0x4,000",
    "14-1": "24G & 60G Altitude  \nInconsistency  \nWarning",
    "14-2": "The altitudes of  \nthe 24G and 60G  \nantennas are  \ninconsistent,  \nwhich may be  \ncaused by RF  \ninterference",
    "14-3": "Ensure the LR-D1 Pro is  \nbeing used within  \noperational requirements",
    "15-0": "0x8,000",
    "15-1": "Whole Board Voltage  \nWarning",
    "15-2": "The device has an  \nerror",
    "15-3": "Stop use and contact  \nAinstein for repair.  \nProprietary information"
  },
  "cols": 4,
  "rows": 16,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]