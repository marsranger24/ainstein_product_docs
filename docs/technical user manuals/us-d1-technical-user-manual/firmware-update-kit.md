---
title: Firmware Update Kit
deprecated: false
hidden: false
metadata:
  robots: index
---
## 10. US-D1 Firmware Update Kit

The US-D1 Firmware Update Kit is an external device that can update the firmware of the US-D1 radar altimeter. The Firmware Update Kit contains an update tool (the auxiliary board hardware), a USB connector, and a power cable. The Kit connects the US-D1 to the Firmware Update Tool via a USB port, which allows the user to load and flash new firmware versions onto the device. The Kit can be purchased directly from Ainstein. The US-D1 Firmware Update Kit was designed to update the existing US-D1 firmware via the serial port on a PC. The update tool hardware is required to connect to all US-D1 units, regardless of UART/CAN/DroneCAN interface and baud rate to be recognized, configured, and flashed. Once the US-D1 unit is connected to the PC through the Auxiliary Board, the US-D1’s information can be queried, including the hardware version, firmware version, interface type, and baud rate.

## 10.1 Hardware Connection and Software Installation

[Installation Overview]  
**NOTE:** _This hardware connection guide is based on installation/collaboration with a Windows PC. If you are running this on Linux, please use the OS-specific method to make the necessary connections. Please contact [support@ainstein.ai](mailto:support@ainstein.ai) for help with the Linux setup._

1. Install ‘CDM21228_Setup.exe’ as a <UART to USB> driver on Windows.
   1. **Note:** Depending on your OS, this step may not be required. If the Auxiliary Board is not recognized automatically, please perform this step.
2. Install ‘Ainstein_US-D1_Firmware_Update_Tool v2.2.0.1’ on Windows. This can be downloaded from the US-D1 product page under the “Downloads” tab.
3. Connect the firmware update board to a power source and flip the power switch on the front of the tool to “ON”.
4. Plug the US-D1 into the firmware update board with the standard 4-pin Molex connector.
5. Connect the US-D1 firmware update board to the PC through a micro-USB cable. Using Windows Device Manager, select the “Ports” dropdown. When connected to the Auxiliary Board, there are a total of four sequential USB Serial Ports listed. Of these four ports, the **third** one is the port number of the Auxiliary Board.
   1. _The port numbers are different for each computer. In this case, it is port COM13. This might not be the case in all instances._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6c1a806722cf328a6491860aca010fec6558629d80109143d4364e71368c9254-Screenshot_2026-01-27_at_2.01.38_AM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true,
      "caption": "**Figure 6: US-D1 Firmware Update Tool (Auxiliary Board) Connection**"
    }
  ]
}
[/block]


In this instance, ‘USB Serial Port (COM13)’ is the port that is connected to the Auxiliary Board that we will use the software tool to connect to.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f41340046e0cf4f2e230abbfa2096001954ea21131dc3238ebd4391db16551f4-Screenshot_2026-01-27_at_2.02.51_AM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true,
      "caption": "**Figure 7: Windows Device Manager - USB Serial Ports**"
    }
  ]
}
[/block]


After establishing the power and USB connection as instructed above, launch the ‘Ainstein_US D1_Firmware_Update_Tool’ App.

## 10.2 Software -- Ainstein US-D1 Firmware Update Tool

The software tool titled ‘Ainstein US-D1 Firmware Update Tool’ is designed for updating firmware and configuring the parameters of the US-D1 via a PC.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed9997ac856ecd7f26148260cd1b5fb844481406715166f302d4519082d2de2e-Screenshot_2026-01-27_at_2.04.47_AM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true,
      "caption": "**Figure 8: Main Window of the US-D1 Firmware Update Tool**"
    }
  ]
}
[/block]


**Caution: Admin Mode should remain “Off”. If looking to use it for any configuration, please reach out to Ainstein previous to turning “On”.**

**Table 5: Software Tool Button Labels - First Row**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9334940eaaa9daa9f725010b22e7f99a0fdf284ceaf36923f8f2c17ed8b5cb6d-Screenshot_2026-01-27_at_2.07.03_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9ae9e30eba69ff2c64de7300f4c97cd874ef79b2023ffa91980c58b196534af-Screenshot_2026-01-27_at_2.07.33_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


**Table 6: Software Tool Button Labels - Second Row**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e58b77163e20a336e373ba8a3e6752c69a28e55b342cfb96cf53df4df713944-Screenshot_2026-01-27_at_2.08.17_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


**Table 7: Software Tool Button Labels - US-D1 Parameter Selection**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed076174cc05c5b4cb37ea905b87dcf46b6347ca3f753f35c15656d67ba3da14-Screenshot_2026-01-27_at_2.10.45_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/15414bc370db618c407d86b15cd995b8d2067ab805e7572d68315a5f9955248c-Screenshot_2026-01-27_at_2.11.11_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


**Caution:**

- **Ensure that the values selected are compatible with the hardware version of the US-D1 device. If a UART US-D1 is selected, the format must be USTD and the interface must be UART. For a CAN/DroneCAN US-D1, the format must be MNKJ or USTD_DroneCAN, and the interface must be CAN.**
- **Admin Mode should remain “Off”. If looking to use it for any configuration, please reach out to Ainstein previous to turning “On”. Improper activation of Admin Mode might result in the US-D1 ‘Bricking’.**

## 10.3 Firmware Update Tool Instructions

**Caution: Please confirm the hardware interface of the US-D1 unit, then follow the instructions accordingly. Some steps differ for UART, CAN, and DroneCAN units.**

<br />

## 10.3.1 Connecting the Firmware Update Kit (Auxiliary Board)

1. Power on the firmware update kit and connect it to the host PC via a micro-USB cable.
2. Select the serial port (COM) that corresponds to the 3rd serial port in **Windows Device Manager** and click the “Open Port” icon (green play button) to connect to the serial port, then click the “Connect” icon to connect the firmware update kit.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/078bb5905ac62443859b123c0cd5728289a8e848b0cf322619c4069887195713-Screenshot_2026-01-27_at_2.14.15_AM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true,
      "caption": "**Figure 9: How to Connect the Auxiliary Board over the Serial Port**"
    }
  ]
}
[/block]


If the operation is performed successfully, the following pop-up window will be displayed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b7b0f13bf9fe233b884c76e2a69c951d474a4a11b26f080cba3bea35533cfdf4-Screenshot_2026-01-27_at_2.15.15_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 10: Firmware Update board Connection**"
    }
  ]
}
[/block]


The “Connect” button will turn green.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a5a4acbdf9ea3c22cd551b250340cc523b1cb129d7e344ef5f57a9b365105921-Screenshot_2026-01-27_at_2.15.56_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 11: ”Connect” Button Before Connection**"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e909d489f96283859b8e8c5e7d4d2c49a20206613090965d9304238285f40ce9-Screenshot_2026-01-27_at_2.16.35_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 12: ”Connect” Button After Connection**"
    }
  ]
}
[/block]


## 10.3.2 Connecting the US-D1

1. Plug the US-D1 into the firmware update board with the standard 4-Pin Molex connector, then press the circular, green power button to power on the US-D1 radar from the firmware update board.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a453e983cebe96976e9112ba65bdcba05feb2cbfa2b1e2e3d4b9a50c5bf0f8c5-Screenshot_2026-01-27_at_2.17.38_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 13: US-D1 Firmware Update Board Connection**"
    }
  ]
}
[/block]


2. When the US-D1 hardware is connected to the programming tool port, press the “Connect Radar” button as shown in Figure 14 below.

**Note:** The **“Connect Radar”** button must be pressed within **6 seconds** of pressing the green power button on the programming board, otherwise the US-D1 connection will fail. When the US-D1 is connected, the current displayed on the firmware update board should read ~170 mA. When the US-D1 is fully powered and cannot connect to the firmware update board, the current will be ~300 mA.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ca62fd6b537e8f94add163637097dc4ccdcabfe6dd4d5303ccef6e82b97133fb-Screenshot_2026-01-27_at_2.20.12_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 14: ”Connect Radar” Button**"
    }
  ]
}
[/block]


If the connection is successful, the following window will pop up with a message showing the current US-D1 interface type and baud rate. Any other parameters will be displayed on the main window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3d9ffb1d50a2609a10120d0b52d4721f57ded47d104aa45567ae0a4c97ebd66-Screenshot_2026-01-27_at_2.21.14_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 15: Current US-D1 Interface Type and Baud Rate**"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/babf5c3e3d197c4f9aa410818cb71dbaa79b306956f8585a44c6d4c1873341e2-Screenshot_2026-01-27_at_2.21.52_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 16: Current US-D1 Parameters**"
    }
  ]
}
[/block]


3. Check the Software Version.

**Note:** The software version is displayed in the last highlighted field of Figure 16. Depending on the current software version, the US-D1 must be updated to the proper generation of firmware. (see Section 10.4 for details). Therefore, follow the instructions below to update the US-D1 to the correct firmware version depending on the existing firmware version on the unit. 

- If the “Software Version Current Value” displays “V1.8.3”, please update to V2.4.0.
- If the “Software Version Current Value” displays “V1.5.3” or later, please update to V2.4.0.
- If the “Software Version Current Value” displays “V1.8.2”, please contact Ainstein.
- If the “Software Version Current Value” displays “V1.5.2” or earlier, please contact Ainstein

## 10.3.3 Configuring the US-D1 Parameters

**Note: For units preflashed with UART or CAN, if users wish to continue using the same interface, then no parameter change is recommended or required.**

For DroneCAN users or CAN to DroneCAN users:

**Note: To support DroneCAN configuration, please update the US-D1 firmware to >= v2.4.0. Refer to Section 10.4 for firmware update instructions.**

1. Make sure the current parameter of ‘Interface Type’ is CAN or DroneCAN.
2. Press the “Select File” button and choose a “.json” file.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dfd305617bc1c6855ebb9bfc6875ff7759b2a57bca85435846e1fa94210832b2-Screenshot_2026-01-27_at_2.25.29_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 17: “Select File” Button**"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c72e9bedc077cf592f1b2b2d99f4e7431d8f1afc5f2b568b52d30a886d3257dc-Screenshot_2026-01-27_at_2.26.19_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 18: Selecting the “.json” File**"
    }
  ]
}
[/block]


3.  Select the .json file and click “Open”. The selected parameter values will be updated on the main window under the “Setting Value” column.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f322bacdfc8e02fd27f8ae0a02f376f15f616dd55d1d7f79fed426da37bfc2f8-Screenshot_2026-01-27_at_2.28.08_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 19: “Setting Value” Parameters**"
    }
  ]
}
[/block]


4. Confirm that the desired parameters are selected and displayed in the “Change Value” column, particularly the Format Type, Interface Type, Baud Rate, and CAN ID.
5. Click the “Configure Parameter” button. If the operation is successful, the following message will be displayed. Select ”OK”.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3266834322d5a165c11bb0118508eb73a466495411bee6f18fb7a40adbf00f81-Screenshot_2026-01-27_at_2.29.33_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 20: Successful Parameter Configuration Pop-Up Window**"
    }
  ]
}
[/block]


6. Perform the Following Steps for configuration to DroneCAN only. **Note:** The US-D1’s DroneCAN protocol does not support full-stack DroneCAN. It only supports fixed DroneCAN ID nodes and transmits DroneCAN messages from the US-D1 node to other nodes. Receiving any DroneCAN messages from other nodes to the US-D1 node is not supported.

- 1. Confirm the interface is CAN and the firmware has been  
     upgraded to at least 2.4.0.
- 2. Ainstein provides two DroneCAN configuration .json files, which configure the DroneCAN node ID as 32 and 33, respectively.
     1. USTD_DroneCAN_NodeID_32.json
     2. USTD_DroneCAN_NodeID_33.json
  3. For US-D1 range detection data, the data type will be the  
     DroneCAN data type of uavcan.equipment.range_sensor.Measurement. For US-D1 SNR detection, it will be filled with the uavcan.equipment.range_sensor.Meaurement.range.field_of_view

7. Verify that the parameters and software version are correct after performing the parameter configuration.
8. Switching the interface from DroneCAN back to CAN, simply choose ‘MNKJ_StdCAN.json’ at step 1.

## 10.4 Firmware and Parameters Update Instructions

> 📘 Caution! Before performing any firmware update, please consult the firmware installation guide to understand how to determine which generation your device is (1 or 2)! Failure to upload the correct firmware file can cause damage to the US-D1 unit.

From December 1, 2020, Ainstein only supports US-D1 Generation 2 hardware and firmware. The latest version for Generation 2 firmware is version 2.4.0. A table detailing the firmware versions can be found below

**Table 8: US-D1 Hardware Generation Changelog**

## US-D1 Generation 2

Purchase Date After Dec 1, 2020 - Firmware Changelog

[block:parameters]
{
  "data": {
    "h-0": "Firmware Version",
    "h-1": "Features",
    "h-2": "Firmware Release Date",
    "0-0": "v1.5.3",
    "0-1": "Add support for the new MCU model.\\*",
    "0-2": "11/20/2020",
    "1-0": "v1.5.3N",
    "1-1": "1. Optimize FM bandwidth to comply with  \n   FCC certificate\n2. Fix for minor offset bugs.",
    "1-2": "3/13/2021",
    "2-0": "v1.8.3",
    "2-1": "Optimize the boot sequence to fix an altitude hang issue",
    "2-2": "8/16/2021",
    "3-0": "v2.4.0",
    "3-1": "Improve the CAN bus recovery. DroneCAN compatible protocol support (limited feature)",
    "3-2": "3/01/2025"
  },
  "cols": 3,
  "rows": 4,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

**Table 9: US-D1 Firmware and Parameter Definitions**

[block:parameters]
{
  "data": {
    "h-0": "File Name",
    "h-1": "File Type",
    "h-2": "Description",
    "0-0": "USTD_StdUART.json",
    "0-1": "Data Format Configuration File",
    "0-2": "Data Format file for Standard UART  \nprotocol",
    "1-0": "MNKJ_StdCAN.json",
    "1-1": "Data Format Configuration File",
    "1-2": "Data Format file for Extended CAN  \nprotocol",
    "2-0": "US-D1_v153.bin",
    "2-1": "Firmware File",
    "2-2": "Revised firmware of FCC version  \nfor Model V MCU",
    "3-0": "US-D1_v153N.bin",
    "3-1": "Firmware File",
    "3-2": "The latest firmware for Model V MCU",
    "4-0": "US-D1_v183.bin",
    "4-1": "Firmware File",
    "4-2": "Fixed the issue of occasional reading  \nstuck after booting for Model V  \nMCU",
    "5-0": "US-D1_v240.bin",
    "5-1": "Firmware File",
    "5-2": "Improve the CAN bus recovery. DroneCAN compatible protocol support (limited feature)",
    "6-0": "USTD_DroneCAN_NodeID  \n\\_32.json",
    "6-1": "Data Format  \nConfiguration  \nFile",
    "6-2": "Data Format file for DroneCAN  \ncompatible protocol. Uses Node ID  \n32",
    "7-0": "USTD_DroneCAN_NodeID  \n\\_33.json",
    "7-1": "Data Format  \nConfiguration  \nFile",
    "7-2": "Data Format file for DroneCAN  \ncompatible protocol. Uses Node ID  \n33"
  },
  "cols": 3,
  "rows": 8,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

1. Press the “Select File” button and choose a “.bin” file. The selected firmware information will be displayed in the main window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc8bd50d8398cdec6d13a4c8f64681c567f8cb575b2fbd5bbbbdbf140e9d7a3a-Screenshot_2026-01-27_at_2.40.53_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 21: Select the “.bin” Firmware File**"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/05fcba982f78ad564f35898edd35a7ceb1e26377eb2582a390e722555fbfd4e4-Screenshot_2026-01-27_at_2.41.24_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 22: Firmware Information**"
    }
  ]
}
[/block]


2. Click the “Upload” button. The software tool will begin to update the US-D1 firmware. Once completed, a pop-up message will be displayed, indicating that the process was successful.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b9d883fc0f1100404c5ff67bf1704a27dd7877848170b2a10cd82ed3f18a8232-Screenshot_2026-01-27_at_2.42.17_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 23: “Upload” Button**"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d09ee14b7a221ef0c5a157a2b39e6fcf9b467dbb53acfd877dac532abd12c4e-Screenshot_2026-01-27_at_2.42.44_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 24: Successful Firmware Update Pop-Up Message**"
    }
  ]
}
[/block]


3. Power cycle the US-D1 by pressing the green button on the programming board twice. The current displayed on the programming board should decrease to 0 mA, and back up to 300 mA when the US-D1 is fully booted. Ensure that the radar is operating at a current of 300 mA for at least 5 seconds before proceeding to the next step.
   1. Alternatively, you can unplug the 4-pin connector and plug it back into the firmware update board.
4. Connect the US-D1 and verify that the parameters and software version are correct after power cycling the US D1. If successful, the “Software Version” will be updated.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e9d746f3291e6e5103e5a9980a7d415113a236af2856548ad46eb222b6056d33-Screenshot_2026-01-27_at_2.44.16_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 25: Updated Software Version and Parameters**"
    }
  ]
}
[/block]


**Note: Please contact Ainstein to request the .json file with the desired BAUD rate, CAN ID, and other parameters. Once received, the following sections help describe how to conduct the changes.**

## 10.4.1 Applying CAN changes through MNKJ_StdCAN.json

**CAUTION: These instructions are for CAN US-D1 units. _DO NOT_ Change the “Interface Type” to UART in any case**, as it may cause damage to the US-D1. 

1. Connect the US-D1 through the software tool. Ensure that all the info in the “Current Value” and “Change Value” tabs are properly displayed.  
   a. The current values for the software version, CAN BAUD rate, and CAN ID should be V2.4.0, 1 Mbps, and 0x00090002, respectively.
2. Ensure Admin Mode is “off” before continuing.
3. Select the MNKJ_StdCAN.json file, click “Open”, and then ”Configure Parameter” button. **Caution: DO NOT click the “Upload Firmware” button.**
4. Upon seeing the pop-up window, wait for 2 seconds and then close by clicking “OK”.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/889711c592585e6fcf1aefb8d8e3e455bbd6d575d63bbeda3a3e4a4478db7e4e-Screenshot_2026-01-27_at_2.48.55_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 26: Successful Parameter Configuration**"
    }
  ]
}
[/block]


5. **Power cycle the US-D1 by hitting the green button. DO NOT click anything on the software tool during this step. Keep the radar on for at least 10 seconds. Make sure the current doesn't stay at 120 mA but reaches 300+ mA. Then turn the radar off by hitting the green button.**
6. Turn the radar on by hitting the green button again and connect US-D1 to the software tool in the same way as in step 1. You should see the updated information displayed.  
   a. “Current Value” for the CAN BAUD rate should display the requested BAUD rate, and the software version should remain the same.

## 10.4.2 Applying DroneCAN changes through either USTD_DroneCAN_NodeID_32.json or USTD_DroneCAN_NodeID_33.json

**CAUTION: These instructions are for DroneCAN US-D1 units. _DO NOT_ Change the “Interface Type” to UART in any case**, as it may cause damage to the US-D1. 

1. Connect the US-D1 through the software tool. Ensure that all the info in the “Current Value” and “Change Value” tabs are properly displayed.  
   a. The current values for the software version, CAN BAUD rate, and DroneCAN node ID should be V2.4.0, 1 Mbps, and node ID 32 or 33, respectively.
2. Ensure Admin Mode is “off” before continuing.
3. Select the USTD_DroneCAN_NodeID_32.json or  
   USTD_DroneCAN_NodeID_33.json file, click “Open”, and then ”Configure Parameter” button. Caution: DO NOT click the “Upload Firmware” button.
4. Upon seeing the pop-up window, wait for 2 seconds and then close by  
   clicking “OK”

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5343eeb7b2658621ace9e8edf6b24f35fe6e60aa4b9242e326005b74aa3d372f-Screenshot_2026-01-27_at_2.55.46_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 27: Successful Parameter Configuration**"
    }
  ]
}
[/block]


5. Power cycle the US-D1 by hitting the green button. DO NOT click anything on the software tool during this step. Keep the radar on for at least 10 seconds. Make sure the current doesn't stay at 120 mA but reaches 300+ mA. Then turn the radar off by hitting the green button.
6. Turn the radar on by hitting the green button again and connect US-D1 to the software tool in the same way as in step 1. You should see the updated information displayed.  
   a. “Current Value” for the CAN BAUD rate should display the requested BAUD rate, and the software version should remain the same.