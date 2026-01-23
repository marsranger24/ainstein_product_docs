---
title: Functionality Testing
deprecated: false
hidden: false
metadata:
  robots: index
---
# Required Materials

- US-D1 Pro Test Tool or DroneCAN Test Tool
- [PCAN-USB](https://www.peak-system.com/PCAN-USB.199.0.html?L=1), [PCAN-USB FD](https://www.peak-system.com/PCAN-USB-FD.365.0.html?&L=1), or DroneCAN compatible autopilot
- 9-16V Power Source
- Multimeter (if not available with Power Source)
- Misc. Wiring (Jumper Wires, etc.)

# Ground Testing

## Hardware Interface

### Table 1. Pinout Definition

<br />

| Function        | DroneCAN (Pins to be used) | Private CAN (Pins to be used) |
| --------------- | -------------------------- | ----------------------------- |
| GND             | 8                          | 8                             |
| CAN H           | 4                          | 2                             |
| CAN L           | 3                          | 1                             |
| Voltage (9-16V) | 10                         | 10                            |

![](https://files.readme.io/4c822aac42d5f8742d973a2afb53ecd9594b2682a58d81cf0294953b2cf04688-image.png)

### Figure 1. US-D1 Pro Molex Cabling Interface

## Connecting the Tool

<br />

To connect the US-D1 Pro to the Radar Altimeter Test Tool, follow the instructions below:

1. Plug either the PCAN-USB or PCAN-USB FD converter into the USB port.
2. Plug in the CAN H pin of the US-D1 Pro into the CANH port of the converter.
3. Plug in the CAN L pin  of the US-D1 Pro into the CAN L port of the converter
4. Plug the US-D1 Pro’s power (red) and ground (black) into a 9-16V power supply. 
5. Open the US-D1 Pro Radar Altimeter Test Tool. The screen that should appear is shown in Figure 2.

![](https://files.readme.io/f273c847407204ce58066a0d732be68b17104d77c93b9687344ab9938dcff3f1-image.png)

### Figure 2. Opening the US-D1 Pro Test Tool

6. Under the dropdown menu labeled “Radar Device”, select “US-D1-Pro.”
7. Under the dropdown menu labeled “Connection”, select “PCAN”.
8. Ensure the baud rate of the CAN connection is established to the known rate of the US-D1 Pro (default, 1 Mbps), as shown in Figure 3.

![](https://files.readme.io/36a44bddd607871a408ef41ac6c4626386bea37be5d79edd56db45aff9460bfa-image.png)

### Figure 3. Selection of the CAN Baud Rate

9. Click the green connect button.
10. After a successful connection has been made, click the green play button  to begin recording data.
11. The display will begin to log the timestamp, altitude, SNR, and Integrated Velocity at an update rate of 20 Hz within the Tool’s GUI, as shown in Figure 4 below.

![](https://files.readme.io/9adbda3331dc0f0d2062bd34f5d725aa4a67bd43c838100bae8a36e5f2bc27c3-image.png)

### Figure 4. Log of Parameters Displayed in the Test Tool GUI

- _**Please note that the US-D1 Pro is designed for UAS applications; therefore, it has to detect the micro-movement between the system and ground when it is mounted properly to have valid detection. To simulate these movements, test at 0.5 m or above, and apply an oscillating movement (up-and-down) with the US-D1 Pro to trigger AGL detection and report through the GUI.**_

12. Click the red stop button to end the recording. The data will be saved in the program’s “Data” folder with its corresponding timestamp.

![](https://files.readme.io/d93a9b2c6b20347be05ebb76ac2baf181d783cf7c52991a06d4c9d5b1c7e8582-image.png)

### Figure 5. Saved Data Itemized by Timestamp

# How to Read US-D1 Pro Collected Data

This section describes how to retrieve and parse data from the US-D1 Pro separately from the US-D1 Pro Test Tool. An example of data collected is presented in Figure 6.

![](https://files.readme.io/ee5bb2c8ee597cb4798bdccdecd0e33130e5ee5a1b319fca32d5121f69dc6b2f-image.png)

### Figure 6. Data Packets from the US-D1 Pro Will be in the Above Format

Data packet #1 can be read as follows:

### Table 2. Data Packet Information

| Hour | Minute | Second | Alt. (MSB) | Alt. (LSB) | SNR (MSB) | SNR (LSB) | Confidence | Velocity | Counter | Reserved |
| ---- | ------ | ------ | :--------- | :--------- | :-------- | :-------- | :--------- | :------- | :------ | :------- |
| 12   | 51     | 07     | 4          | 150        | 0         | 45        | 100        | 0        | 0       | 0        |