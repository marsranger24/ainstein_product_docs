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
   ● The interface between this GUI and US-D1 Pro is fixed in CAN-FD,  
   instead of CAN2.0, please select ‘CANFD-XX’ in Baudrate option. This  
   doesn’t have the impact on the US-D1 Pro streaming data’s interface and  
   baud rate. Example:  
   ■ If US-D1 Pro has been configured to 500Kbps in Baud rate, select  
   CANFD-500k; while in the detection data stream export, it can be in  
   CAN-FD or CAN 2.0 at 500Kbps.  
   1421 Research Park Dr  
   Lawrence, KS 66049  
   ■ If US-D1 Pro has been configured to 1Mbps in Baud rate, select  
   CANFD-1M; while in the detection data stream export, it can be in  
   CAN-FD or CAN 2.0 at 1Mbps.  
   ● CAN type depends on the user's setting. In this example, CAN type is  
   selected as ‘PCAN-USB0’