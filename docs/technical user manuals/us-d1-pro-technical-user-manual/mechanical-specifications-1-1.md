---
title: Firmware & Parameter Update
deprecated: false
hidden: false
metadata:
  robots: index
---
## 8. Firmware and Parameter Update

### 8.1 Private CAN Firmware and Parameter Update

To perform the firmware and parameter update via Private CAN, Ainstein will provide  
the following tool and file.

1. US-D1 Pro OTA Updater GUI Tool
2. Firmware Flash File for Firmware Update (.bin)
3. Data Identifier (DID) sheet for Parameter Configuration

Users should have the following tools.

1. CAN-FD Adapter
2. PC in Windows OS

Note:

- The CAN transceiver in US-D1 Pro hardware is CAN-FD, and it is compatible  
  and can be configurable to CAN 2.0.
  - The interface between this US-D1 Pro OTA Updater GUI Tool and US-D1  
    Pro is fixed in CAN-FD, instead of CAN2.0. Therefore a CAN-FD Adapter  
    is required.

Please see the configurable parameter in Section 5.1.2, and contact Ainstein for more  
assistance.

<br />

### 8.1.1 ‘US-D1Pro OTA Updater’ and Firmware Update Instruction

US-D1 Pro OTA Updater is the GUI tool to perform the firmware and parameter update  
via Private CAN, here are the steps:

1. Open the tool and enter the tool configuration window
2. Select the connection interface, and click ‘OK’ to enter the main window

Note:

- The interface between this GUI and US-D1 Pro is fixed in CAN-FD,  
  instead of CAN2.0, please select ‘CANFD-XX’ in Baudrate option. This  
  doesn’t have the impact on the US-D1 Pro streaming data’s interface and  
  baud rate. Example:
  - If US-D1 Pro has been configured to 500Kbps in Baud rate, select  
    CANFD-500k; while in the detection data stream export, it can be in  
    CAN-FD or CAN 2.0 at 500Kbps.
  - If US-D1 Pro has been configured to 1Mbps in Baud rate, select  
    CANFD-1M; while in the detection data stream export, it can be in  
    CAN-FD or CAN 2.0 at 1Mbps.
- CAN type depends on the user's setting. In this example, CAN type is  
  selected as ‘PCAN-USB0’

![](https://files.readme.io/4def6524c8400b366ee32bf432dd4f0ae170f2e1707dd267efa00dbb7ec429e1-image.png)

3. In the main window, click ‘Refresh’ to inquire about US-D1 Pro’s current status and firmware version

![](https://files.readme.io/0f59474ff8894fe4c5be7d109580f2be4db882510ead0d9fa3851ad6e490f840-image.png)

Note:

- Status - Working: US-D1 Pro is operating in the Application
- Type - USD1-Pro: GUI recognize the device as US-D1 Pro correctly
- Bin Ver - 0.1.0: Current application firmware version is v0.1.0 (or v0.1)

4. Perform firmware update  
   a. Selecting Application firmware file  
   b. Click ‘Start’  
   c. Wait until the firmware update process completes. Once it completes and succeeds, it will show the messages.

![](https://files.readme.io/438077fc9e75f19cf52183981e994d7b2afbb2e1d1cba45c279d7ff79d508b2e-image.png)

5. Click  ‘Refresh’ to inquire about US-D1 Pro’s new status

![](https://files.readme.io/e7b205dd13248df6cec3ecbb50e9d9f541f97523684230fc661d909ac13ae795-image.png)

6. Power cycle the US-D1 Pro

<br />

### 8.1.2 Parameter Configuration Instruction

Under private CAN protocol, the configurable parameter information can be found in Section 5.1.2. To perform the parameter configuration, simply use the same GUI tool and follow the steps below.

1. Perform parameter update.  
   a. Caution: Clear the content in the App blank, if there is any.  
   b. Select the Data Identifier (DID) sheet file  
   c. Click ‘Start’  
   d. Wait until the parameter update process completes. Once it completes and succeeds, it will show the messages.

![](https://files.readme.io/0a5889a85303d76b4d5e451324452722e694f5e775f304d9ad5792f98373cd5d-image.png)

2. Power cycle the US-D1 Pro

### 8.1.3 Data Identifier (DID) sheet

In the DID sheet, the mapping between the values in cells and configurable parameters can be found below.

![](https://files.readme.io/ea91fd2ef2cfcaadc7c5a04e886a8df0229bf83a9e230ff3f6c249427a1d34d9-image.png)

Note:

1. Only above 5 cells are supported in US-D1 Pro parameter configuration
2. The Cell of 1~5 in above figure is mapping to the No. in the Section 5.1.2 table
3. Number 1,2,4,5 has the drop-down menu, users can select it from there.
4. For CAN 2.0, select the same value for Cell 4 and 5; while for CAN FD, they can be either same value or different.

### 8.2 DroneCAN Firmware and Parameter Update

As DroneCAN is the public communication protocol in UAV industry, Ainstein recommend users to use DroneCAN GUI Tool (cross-platform free open source application for DroneCAN bus management and diagnostics) or Mission Planner (versatile ground control station (GCS) software developed by ArduPilot) to perform the firmware and parameter update. Refer to the official instruction for details of steps.

Please see the configurable parameter in Section 5.2.3, and contact Ainstein for more assistance.

### 8.2.1 DroneCAN GUI tool Firmware Update  Instruction

Here is an example of using DroneCAN GUI tool to perform the firmware update.

1. Launch the DroneCAN GUI tool
2. Click US-D1 Pro Node and check all information

![](https://files.readme.io/571b983a8af3f659fa46a25155c869821acaf0faa5733e14da82827526a6e676-image.png)

3. Perform firmware update  
   a. Click ‘Update Firmware’  
   b. Selecting Application firmware file (.bin)  
   c. Wait until the firmware update process completes. GUI shows ‘FIRMWARE UPDATE’.

![](https://files.readme.io/29806c84cb3ded4095b54509dc2384edb30c24435ff92c188f6867cfa0742f28-image.png)

4. Once it completes and succeeds, it will automatically reboot and operate.

![](https://files.readme.io/113d9adc0740ded19ebe1581fc692de90e26eff28440962c959744c164088d8a-image.png)