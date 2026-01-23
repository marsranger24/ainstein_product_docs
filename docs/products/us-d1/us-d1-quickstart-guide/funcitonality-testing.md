---
title: Funcitonality Testing
deprecated: false
hidden: false
metadata:
  robots: index
---
# Required Materials

- US-D1 and LR-D1 Radar Altimeter Test Tool
- USB-TTL Converter
- 5 ~ 12V Power Source
- Multimeter (if not available with Power Source)
- Misc. Wiring (Jumper Wires, etc.)

# Using the PC Test Tool

## Hardware Interface

<br />

| Wire Color | UART            | CAN             |
| ---------- | --------------- | --------------- |
| Black      | Ground          | Ground          |
| White      | RX (Radar)      | CAN_Low         |
| Green      | TX (Radar)      | CAN_HI          |
| Red        | Voltage (5~13V) | Voltage (5~13V) |

![](https://files.readme.io/3ead600ecf68e5940285d125caeeae7c2aff9825d81de92e2792abb7cd15c9db-image.png)

### Figure 1: US-D1 Molex Cabling Interface

## Connecting to the Tool

<br />

To connect the US-D1 to the Radar Altimeter Test Tool, follow the instructions below:

1. Plug the USB-TTL converter into the USB port.
2. Plug in the TX (green) of the US-D1 into the RX of the USB-TTL converter.
3. Plug in the RX (white) of the US-D1 into the TX of the USB-TTL converter.
4. Plug the US-D1's power (red) and ground (black) into a 5V power supply. Ensure that the US-D1's ground is shared with the USB-TTL's ground as well. _When connected to power, the US-D1 should boot at a current of 120 mA for ~6 seconds. After this, the US-D1 will operate at a current of 330 mA. Use a multimeter to test that this is the case._
5. Open the US-D1 Radar Altimeter Test Tool. Note: Both Windows and Linux test tool versions are available for download upon request to [support@ainstein.ai.](mailto:support@ainstein.ai.) The screen that should appear is shown in Figure 2.

![](https://files.readme.io/c35f9919e21fc2bddc28048383dd660edda2372af899133599516018f05e5fe1-image.png)

### Figure 2. GUI of the Test Tool

6. Under the dropdown menu labeled “Radar Device” (Shown as “Radar D” in Figure 2 due to window sizing), select “US-D1.”
7. Under the dropdown menu labeled “Connection Method” (Shown as “Connection M” in Figure 2 due to window sizing), select “Serial Port”.
8. Select the corresponding serial port through which the device has been connected. This process has been demonstrated in Figure 3.

![](https://files.readme.io/2d7095f52d53353ff799ec1f877821a5937e4374959c4d3cb589fa6b3da2fe2e-image.png)

### Figure 3. Note the Dropdown being Selected for Determining Serial Port

9. Select a Baud Rate of 115250 kbps.
10. Click the green connect button. After a successful connection has been made, click the green play button to begin recording data.
11. The display will begin to log the timestamp, altitude, and SNR at an update rate of 100 Hz within the Tool’s GUI, as shown in Figure 4 below.

![](https://files.readme.io/dfc587859eedf070897ad38c9cd6d1e91bcc1ce664d07135f01b140498e1412a-image.png)

### Figure 4. Log of Parameters Displayed in the Tool's GUI

12. Click the red stop button to end the recording. The data will be saved in the program’s “Data” folder with its corresponding timestamp.

![](https://files.readme.io/706b5b9e34faef96ba4f23f59e7266739543a733a1092b35047d241116878cf2-image.png)

### Figure 5. Saved Data will be Itemized by the Timestamp

# How to Read US-D1's Collected Data

This section describes how to retrieve and parse data from the US-D1 separately from the US-D1 Test Tool. An example of data collected has been presented in Figure 6.

![](https://files.readme.io/df278b201c4872c6dbf17c9e4349ffe24a6214cc34350a169b32d63832ab4434-image.png)

### Figure 6. Data Packets from the US-D1 will be in the Above Format

The data packet can be read as follows:

### Data Packet Information

| Hour | Minute | Second | Version ID | Alt 1 | Alt 2 | SNR | Checksum |
| ---- | ------ | ------ | :--------- | :---- | :---- | :-- | :------- |
| 06   | 18     | 24     | 2          | 68 cm | 0 cm  | 22  | 92       |

The altitude in the data packet is calculated through the following formula:  
alt m=Alt2 ×28+Alt1×0.01

alt (m) = \[(Alt2 x 2<sup>8</sup>) + Alt1] x 0.01