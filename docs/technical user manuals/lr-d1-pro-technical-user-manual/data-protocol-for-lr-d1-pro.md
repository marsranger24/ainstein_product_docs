---
title: Data Protocol for LR-D1 Pro
deprecated: false
hidden: true
metadata:
  robots: index
---
## 5. Data Protocol For LR-D1 Pro:

**UART Data Protocol:**

- I/O Standard: RS-232 (Default) and RS-422, RS-485, TTL and CAN (by  
  configuration)
- Baud Rate: 115200 b/s
- Data length: 8 bits, plus one start bit and one stop bit, and no parity bit

**CAN Data Protocol:**

The output data frame of the CAN protocol is a standard frame format with the  
following characteristics:

- Identifier (ID) length: 11 bits (Standard CAN ID frame) , following CAN V2.0A  
  standard protocol
-  CAN ID: 0x055
- Baud rate: 1 Mbps
- Data segment length (DLC) of each CAN packet: 8 bits
- LR-D1 Pro 3.0 data packet length: 32 bytes, consisting of 8 bits from 4 CAN  
  frames. See the figure below for the meaning of each bit of data of CAN data  
  frames.

**Table 2: Data Packet Definition**

[block:parameters]
{
  "data": {
    "h-0": "From (Byte)",
    "h-1": "LR-D1 Pro (Data)",
    "h-2": "To Receiver (Note)",
    "0-0": "data1",
    "0-1": "0xEB",
    "0-2": "Packet Header MSB (Most Significant Bits)",
    "1-0": "data2",
    "1-1": "0x90",
    "1-2": "Packet Header LSB (Least Significant Bits)",
    "2-0": "data3",
    "2-1": "deviceID",
    "2-2": "Device ID Byte (Default: 0x00)",
    "3-0": "data4",
    "3-1": "0x1C",
    "3-2": "Data packet length",
    "4-0": "data5",
    "4-1": "0x0000: Normal  \nOthers: Malfunction（1）",
    "4-2": "Malfunction Alert",
    "5-0": "data6",
    "5-1": "0x0000: Normal  \nOthers: Malfunction（1）",
    "5-2": "Malfunction Alert",
    "6-0": "data7",
    "6-1": "high1_h（2）",
    "6-2": "24 GHz Altitude MSB",
    "7-0": "data8",
    "7-1": "high1_l（2)",
    "7-2": "24 GHz Altitude LSB",
    "8-0": "data9",
    "8-1": "snr1",
    "8-2": "24 GHz SNR",
    "9-0": "data10",
    "9-1": "speed1_h（3）",
    "9-2": "24 GHz Velocity MSB",
    "10-0": "data11",
    "10-1": "speed1_l（3）",
    "10-2": "24 GHz Velocity LSB",
    "11-0": "data12",
    "11-1": "high2_h",
    "11-2": "60 GHz Altitude MSB（4）",
    "12-0": "data13",
    "12-1": "high2_l",
    "12-2": "60 GHz Altitude LSB",
    "13-0": "data14",
    "13-1": "snr2",
    "13-2": "60 GHz SNR",
    "14-0": "data15",
    "14-1": "speed2_h",
    "14-2": "60 GHz Velocity MSB",
    "15-0": "data16",
    "15-1": "speed2_l",
    "15-2": "60 GHz Velocity LSB",
    "16-0": "data17",
    "16-1": "high3_h",
    "16-2": "Integrated Altitude MSB",
    "17-0": "data18",
    "17-1": "high3_l",
    "17-2": "Integrated Altitude LSB",
    "18-0": "data19",
    "18-1": "snr3",
    "18-2": "Integrated SNR",
    "19-0": "data20",
    "19-1": "speed3_h",
    "19-2": "Integrated Velocity MSB",
    "20-0": "data21",
    "20-1": "speed3_l",
    "20-2": "Integrated Velocity LSB",
    "21-0": "data22",
    "21-1": "Reserved",
    "21-2": "0xFF",
    "22-0": "data23",
    "22-1": "Reserved",
    "22-2": "0xFF",
    "23-0": "data24",
    "23-1": "Reserved",
    "23-2": "0xFF",
    "24-0": "data25",
    "24-1": "Reserved",
    "24-2": "0xFF",
    "25-0": "data26",
    "25-1": "Reserved",
    "25-2": "0xFF",
    "26-0": "data27",
    "26-1": "Reserved",
    "26-2": "0xFF",
    "27-0": "data28",
    "27-1": "Reserved",
    "27-2": "0xFF",
    "28-0": "data29",
    "28-1": "Reserved",
    "28-2": "0xFF",
    "29-0": "data30",
    "29-1": "Reserved",
    "29-2": "0xFF",
    "30-0": "data31",
    "30-1": "Reserved",
    "30-2": "0xFF",
    "31-0": "data32",
    "31-1": "Checksum",
    "31-2": "Checksum:  \n(data4+data5+…+data30+data31) bitwise-AND  \nwith 0xFF"
  },
  "cols": 3,
  "rows": 32,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]