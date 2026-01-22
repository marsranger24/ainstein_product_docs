---
title: LR-D1 Technical User Manual
deprecated: false
hidden: true
metadata:
  robots: index
---
1421 Research Park Dr 

Lawrence, KS 66049 

**Long Range Radar Altimeter** 

**LR-D1** 

**User Manual** 

**D00.01.13** 

**10/29/2025** 

**Proprietary information**  

**Page 1**  
1421 Research Park Dr 

Lawrence, KS 66049 

**Revision History** 

| Version Number | Date               | Authors                           | Notes                                                                                      |
| -------------- | ------------------ | --------------------------------- | ------------------------------------------------------------------------------------------ |
| D00.00.01      | Sep 13, 2018       | Hao Liu,  Liqiang Ren,  Zhenyu Hu | Initial Draft                                                                              |
| D00.00.03      | Oct 17, 2018       | Zhenyu Hu                         | Add section 7 \-  Known Issues                                                             |
| D00.01.01      | Nov 5, 2018        | Andrew Megaris                    | Technical Revision                                                                         |
| D00.01.02      | Dec 6, 2018        | Zhenyu Hu                         | Spec updates                                                                               |
| D00.01.03      | Jan 14, 2019       | Zhenyu Hu                         | Data protocol update                                                                       |
| D00.01.04      | May 17, 2021       | Zhenyu Hu                         | From the original  version of V2.2                                                         |
| P00.01.04      | June 2, 2021       | Ethan Perrins                     | Public Version                                                                             |
| D00.01.05      | June 18, 2021      | Zhenyu Hu                         | From the original  version of V2.4                                                         |
| D00.01.06      | September 17, 2021 | Camron Myers                      | Added 8\. Firmware Change Log, 9\.  Firmware Update  Instructions, and 10\. Test Tool GUI. |
| D00.01.07      | Oct 7, 2021        | Zhenyu Hu                         | From original version of V3.0 for firmware 3.223.7/3.0.7                                   |
| D00.01.08      | Feb 20, 2023       | Camron Myers                      | V2.2 Hardware  Changes                                                                     |
| D00.01.09      | July 12, 2023      | Zhenyu Hu  Camron Myers           | Alert Information  Changes; HW2.2  Changes                                                 |
| D00.01.10      | Aug 16, 2024       | Zhenyu Hu                         | Update info by the                                                                         |

**Proprietary information**  

**Page 2**  
1421 Research Park Dr 

Lawrence, KS 66049 

|           |               |                                      | released hardware and software on Aug 2024                          |
| :-------- | :------------ | :----------------------------------- | :------------------------------------------------------------------ |
| D00.01.11 | Oct 11, 2024  | Pedro Lopez,  Zhenyu Hu              | Update info by only supporting released firmware for  hardware V2.2 |
| D00.01.12 | July 10, 2025 | Nash Sloan,  Pedro Lopez,  Zhenyu Hu | Update info by  Adding Out of Range behavior indication Byte        |

D00.01.13 October 29, 2025 Zhenyu Hu Update the firmware to v19.0.0.1 

**Proprietary information**  

**Page 3**  
1421 Research Park Dr 

Lawrence, KS 66049 

**Copyright 2019 © Ainstein AI, Inc. All rights reserved. No part of this work may be reproduced, published, or distributed in any form or by any means (electronically, mechanically, photocopying, recording, or otherwise), or stored in a database retrieval system, without the prior written permission of Ainstein AI, Inc. in each instance.** 

| Warning\!  FAILURE OR IMPROPER SELECTION OR IMPROPER USE OF THE PRODUCTS AND/OR SYSTEMS DESCRIBED HEREIN OR RELATED ITEMS CAN CAUSE DEATH, PERSONAL INJURY AND PROPERTY DAMAGE.  • This document and other information from Ainstein AI Inc, its subsidiaries and authorized distributors provide product and/or system options for further investigation by users having technical expertise.  • The user, through its own analysis and testing, is solely responsible for making the final selection of the system and components and assuring that all performance, endurance, maintenance, safety and warning requirements of the application are met. The user must analyze all aspects of the application, follow applicable industry standards, and follow the information concerning the product in the current product catalog and in any other materials provided from Ainstein or its subsidiaries or authorized distributors.  • To the extent that Ainstein or its subsidiaries or authorized distributors provide component or system options based upon data or specifications provided by the user, the user is responsible for determining that such data and specifications are suitable and sufficient for all applications and reasonably foreseeable uses of the components or systems. • The Buyer and/or end-user will be solely responsible for final disposal of all products. |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

**Proprietary information**  

**Page 4**  
1421 Research Park Dr 

Lawrence, KS 66049 

**Table of Contents** 

**Long Range Radar Altimeter 1 LR-D1 1 User Manual 1 Revision History 2 Table of Contents 5 1\. Product Description 7** 

1.1 LR-D1 7 1.2 Compliances 7 **2\. Installation Guidelines 7** 2.1. Mounting Angle 7 2.2 Mounting to an Aircraft 8 2.3. Line of Sight Clearance 8 2.4. Integration Requirements 8 **3\. Operational Requirements 10** 3.1 Obstruction to the LR-D1 Field of View 10 3.2 Excessive Pitch/Roll 10 3.3 Terrain 10 3.4 Power Source 10 3.5 Orientation of LR-D1 10 3.6 Minimum and Maximum Operating Altitude 11 **4\. Technical Data: 11 5\. UART Data Protocol For LR-D1: 13 6\. Mechanical Drawing: 16 7\. Radiated Emissions 17 8\. Hardware Interface: 18 9\. Cabling Diagram: 19 10\. Known Issues 20 11\. Firmware Change Log: 21 12\. Firmware Update Instructions: 23** Remote Firmware Update 23 **13\. LR-D1 Altimeter Test Tool GUI : 24** Operating the Test Tool GUI 24 

**Proprietary information**  

**Page 5**  
1421 Research Park Dr 

Lawrence, KS 66049 

**14\. Contact US 26 Appendix 1: Malfunction Alert Information List 27** 

**Proprietary information**  

**Page 6**  
1421 Research Park Dr 

Lawrence, KS 66049 

**1\. Product Description** 

**1.1 LR-D1** 

The LR-D1 Radar Altimeter uses the principles of radio detection and ranging to determine the altitude of the aircraft. A microwave signal is transmitted out of the sensor, reflects off the target, and is received by the sensor. Distance and horizontal velocity from the sensor to the terrain (altitude) are derived by the difference in time from when the signal is sent from the sensor to when the signal is received by the sensor. 

The LR-D1 is enclosed in a black metallic case, the radome, which is conducive to radar telemetry. 

**1.2 Compliances** 

FCC and CE certifications pending. 

**2\. Installation Guidelines** 

**2.1. Mounting Angle** 

When mounting the device, the radio wave emitted from the LR-D1 must be **perpendicular** to the ground below the aircraft. There should not be any angle of inclination in any direction while the device is fastened to the aircraft. ![][image1]  
Figure 1 

**Proprietary information**  

**Page 7**  
1421 Research Park Dr 

Lawrence, KS 66049 

**2.2 Mounting to an Aircraft** 

The device should be secured to the aircraft, where it is not free to move in any direction. 

**2.3. Line of Sight Clearance** 

Keep the face of the radar clean, and do not cover it with any additional materials. Any coatings, coverings, and modifications to the radome can degrade the performance of the radar device. 

Additionally, keep any unexpected objects out of the radar’s FoV (Field of View). Obstructions to the LR-D1’s field of view will cause a decrease in the performance of the radar. It is highly recommended that the LR-D1 be mounted on the underside of the aircraft far away from the landing gear, other aircraft structures, or other equipment. 

![][image2]![][image3]

Figure 2 

**2.4. Integration Requirements** 

The LR-D1 outputs altitude measurements and signal-to-noise ratio (SNR) measurements when operational. When integrating the LR-D1 radar altimeter, it is 

**Proprietary information**  

**Page 8**  
1421 Research Park Dr 

Lawrence, KS 66049 

necessary to use SNR measurements and Out of Range Behavior Indication in conjunction with malfunction alerts (see appendix 1) to properly filter out erroneous altitude values. 

A filtering algorithm should be used to estimate vehicle position, velocity, and angular orientation based on rate gyroscopes, accelerometer, compass, GPS, airspeed, and barometric pressure measurements in addition to the recorded LR-D1 measurements. Sensor redundancy is heavily advised for the LR-D1. 

**Proprietary information**  

**Page 9**  
1421 Research Park Dr 

Lawrence, KS 66049 

**3\. Operational Requirements** 

The LR-D1 will perform optimally if the operational requirements below are fully satisfied. Failure to meet the operational requirements may cause a decrease in performance, accuracy, or reliability of the LR-D1 altimeter and is not advised. 

**3.1 Obstruction to the LR-D1 Field of View** 

Objects or aircraft structures that are located within the LR-D1’s conical field of view which obstruct the radar’s view of the ground may cause multipath reflections or other degradative phenomena to occur. The LR-D1 should be mounted a safe distance away from the landing gear and any other components of the aircraft below it. 

**3.2 Excessive Pitch/Roll** 

Pitch and roll angles that exceed 21.5° and 15° respectively may also cause the performance of the LR-D1 to worsen. This sensitivity increases with altitude. 

**3.3 Terrain** 

Terrain with poor reflectivity may cause the performance of the LR-D1 to worsen. Flying at the limit of the LR-D1’s range over dry, loose soil, such as tilled farmland, or sand is not recommended. 

Terrain with high reflectivity may cause the LR-D1 to output abnormally high values at low altitudes due to high saturation. 

**3.4 Power Source** 

Any power source used to operate the LR-D1 that does not provide the minimum power and voltage can worsen the performance of the device or cause its operation to stop altogether. 

**3.5 Orientation of LR-D1** 

The LR-D1 must be mounted upon the aircraft in such a manner as to be fully horizontal, its radome directly facing the ground. Any angle of inclination may degrade performance. 

**Proprietary information**  

**Page 10**  
1421 Research Park Dr 

Lawrence, KS 66049 

**3.6 Minimum and Maximum Operating Altitude** 

Operating the LR-D1 at altitudes below 1.4 meters and above 500 meters will result in a degradation of performance and potentially erroneous measurements. Also, any reading at an altitude of greater than 655.35m would be considered an error or overflowed reading (see appendix 1). **When the actual altitude is too high or too low, for example, above concrete, the radar can operate normally up to 800m or even higher. It can also operate normally below than 1.4m, for example, when the mounting height on some aircrafts are on the surface or at low heights. The LR-D1 will report data12 (Out of Range Indication, see Table 2 in the Section 5 for details) is invalid to indicate there is no valid target detected.** 

**4\. Technical Data:** 

**Table 1: Specification** 

|        Frequency Band |            24 GHz            |
| --------------------: | :--------------------------: |
|             Bandwidth |            250 MHz           |
|     Power Consumption |          \< 11.00 W          |
|     Operating Voltage |          10 \- 30 V          |
|        Altitude Range |         1.4m\~500m（1）        |
|    Altitude Precision |          ±0.3644m（2）         |
|           Update Rate |             40Hz             |
| Detection Angle Range | Azimuth 43°，Elevation 30°（3） |
|      Maximum Velocity |     ± 30 m/s in elevation    |
|           Temp. Range |         \-40℃\~ \+60℃        |

Dimensions\<112mm\*102.5mm\*31mm (mounting bracket is NOT included) 

Weight 315 g (excluding external connector cable) IP RatingBuilt to the requirements of IP67 (Test pending)（4 ） 

Vibration RatingIEC 60068-2-6.1995 sine vibration 5g XYZ three axis  
Shock RatingIDT IEC 68-2-27:1987 half sine shock 20g XYZ three axis 

**Proprietary information**  

**Page 11**  
1421 Research Park Dr 

Lawrence, KS 66049 

| ESD Rating | IEC 61000-4-2.2008 8K/15K contact/air B class |
| ---------: | :-------------------------------------------- |

Note: 

1\. Radar data may vary over different terrains when the radar is out of its detection range. Usually, we recommend mounting the LR-D1 at a minimum height of at least 1.4m. 

2\. Range detection might be limited by terrains, pitch, and roll of aircraft, etc. The range precision here only indicates the lab experiment/calibration result in the ideal case. 

LR-D1 altitude data report step size could be smaller than this precision because of the post-processing. 

3\. Based on mm-wave radar specs, a large angle of pitch and roll would bring error for detection. Under the same measurement circumstance, larger angles by aircraft bring more error. 

4\. IP rate here only focuses on the radar itself. This rating does not cover any cabling interface. 

**Proprietary information**  

**Page 12**  
1421 Research Park Dr 

Lawrence, KS 66049 

**5\. UART Data Protocol For LR-D1:** 

● Protocol: UART 

● I/O Standard: RS-232 (Default) and RS-422 (Per Request) 

● Baud Rate: 115200 b/s 

● Data length: 8 bits, plus one start bit and one stop bit, and no parity bit 

**Caution\!** If the data received for the malfunction alert code is not equal to 0x0000 (Normal function) for data 5 and data 6 in the table below, then please check the malfunction alert code table in the Appendix 1 for details. . 

**Table 2: Data Packet Definition** 

| From                           | LR-D1                                                                                | To                                                                                         | Receiver |
| ------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | :------: |
| Byte                           | Data                                                                                 | Note                                                                                       |          |
| data1                          | 0xEB                                                                                 | Packet Header MSB (Most Significant Bits)                                                  |          |
| data2                          | 0x90                                                                                 | Packet Header LSB (Least Significant Bits)                                                 |          |
| data3                          | deviceID                                                                             | Device ID Byte (0x00)                                                                      |          |
| data4                          | 0x1C                                                                                 | Data packet length; Fixed as 28 Bytes                                                      |          |
| data5                          | 0x00: Normal  Others: Malfunction（1）                                                 | Malfunction Alert MSB                                                                      |          |
| data6                          | 0x00: Normal  Others: Malfunction                                                    | Malfunction Alert LSB                                                                      |          |
| data7                          | high1\_h（2）（6）                                                                       | Object 1 Altitude MSB                                                                      |          |
| data8                          | high1\_l（2）（6）                                                                       | Object 1 Altitude LSB                                                                      |          |
| data9                          | snr1                                                                                 | Object 1 SNR                                                                               |          |
| data10  data11  data12  data13 | speed1\_h（3） speed1\_l（3）  Out of Range Indication (Altitude Health)（4）  Reserved（5） | Object 1 Velocity MSB  Object 1 Velocity LSB  0: Invalid Altitude  1: Valid Altitude  0xFF |          |
| data14  data15  data16         |                                                                                      | 0xFF  0xFF  0xFF                                                                           |          |
| data17  data18  data19         |                                                                                      | 0xFF  0xFF  0xFF                                                                           |          |
| data20  data21                 |                                                                                      | 0xFF  0xFF                                                                                 |          |
| data22                         |                                                                                      | 0xFF                                                                                       |          |
| data23                         |                                                                                      | 0xFF                                                                                       |          |
| data24                         |                                                                                      | 0xFF                                                                                       |          |

**Proprietary information**  

**Page 13**  
1421 Research Park Dr 

Lawrence, KS 66049 

| data25 |          |                              0xFF                              |
| -----: | -------- | :------------------------------------------------------------: |
| data26 |          |                              0xFF                              |
| data27 |          |                              0xFF                              |
| data28 |          |                              0xFF                              |
| data29 |          |                              0xFF                              |
| data30 |          |                              0xFF                              |
| data31 |          |                              0xFF                              |
| data32 | checksum | Checksum:  (data4+data5+…+data29+data31) bitwise-AND with 0xFF |

Note: 

1\. Please see Appendix 1 for details about malfunction information. 

2\. Altitude Data Parse: Altitude \= (high\_h \* 256\) \+ high\_l; unit: **0.01 m (cm)**; Type: **Unsigned** 

**Note:** If ‘Out of Range Indication’ is 0, the altitude will show ‘0.’ 

3\. Velocity Data Parse: Velocity \= (speed \_h \* 256\) \+ speed \_l; unit: **0.01m/s**; Type: **Signed** SNR Data Parse: SNR \= snr1; unit: dB; Type: Unsigned 

**Note:** If ‘Out of Range Indication’ is 0, the velocity and SNR will show ‘0.’ 4\. Out of Range Behavior (Radar Measurement Health): 

● 0: Invalid Altitude, the radar reported altitude health is ‘Invalid’. ● 1: Valid Altitude, the radar reported altitude health is ‘Valid’. 

5\. Reserved Byte: Not applied in current version and default as 0xFF. 

**Note:** In the Beta version firmware, Reserved Bytes may be filled with values other than 0xFF for evaluation purposes. 

6\. We use a 16-bit integer to indicate the LR-D1’s altitude reading in centimeters, therefore the maximum valid altitude would be 65535 cm (655.35 m). If the actual altitude is greater than that, altitude reading overflow would occur, and will report ‘Altitude reading overflow’ Malfunction Alert. 

7\. There are two data sections in the LR-D1 that are related to the Radar Measurement’s validity (See the example in the flow chart): 

a. Data 12 Altitude Health: This is an absolute criteria. Users MUST NOT use radar’s measurement if this data reports ‘Invalid’ 

b. Data 5\~6 Malfunction: This is a relative criteria. Users SHOULD consider the application to determine whether to keep using radar’s measurement or discard it. For example: 

i. ‘Altitude reading overflow’ \- Users might discard the altitude reading or consider the altitude reading plus 65535 cm. 

ii. ‘Voltage alert’ \- Users might discard the radar’s measurement reading or keep using it temporarily and contact Ainstein for more details. 

**Proprietary information**  

**Page 14**  
1421 Research Park Dr 

Lawrence, KS 66049 

**Proprietary information**  

**Page 15**  
1421 Research Park Dr 

Lawrence, KS 66049 

**6\. Mechanical Drawing:** 

**Figure 3: Dimensions of LR-D1 (Units: mm)** 

**Proprietary information**  

**Page 16**  
1421 Research Park Dr 

Lawrence, KS 66049 

**7\. Radiated Emissions** 

| Maximum Transmit Power (EIRP) | 32 dBm |
| :---------------------------- | :----- |

**Proprietary information**  

**Page 17**  
1421 Research Park Dr 

Lawrence, KS 66049 

**8\. Hardware Interface:** 

**Table 3: Pin Out Definition** 

| Pin | Wire Color | Pin Name              | Function              | Note                     |
| --- | ---------- | --------------------- | --------------------- | ------------------------ |
| 1   | Red        | VCC                   | Input Voltage         | 10 \- 30 V  Power \< 11W |
| 2   | Red        | VCC                   | Input Voltage         | 10 \- 30 V  Power \< 11W |
| 3   | Blue       | RS-422 T+ /  RS-232 T | RS422: TX+  RS232: TX | Default Setting: RS232   |
| 4   | Brown      | RS-422 T- /  RS-232 R | RS422: TX  RS232: RX  | Default Setting: RS232   |
| 5   | White      | RS-422 R+             | RS422: RX \+          | Leave unwired for RS232  |
| 6   | Green      | RS-422 R-             | RS422: RX-            | Leave unwired for RS232  |
| 7   | Black      | GND                   | Ground                |                          |
| 8   | Black      | GND                   | Ground                |                          |

**Note:** 

LR-D1's default hardware interface is RS-232. If the RS-422 interface is required, please contact Ainstein for assistance. 

**Figure 4: LR-D1 Pinout Diagram** 

**Proprietary information**  

**Page 18**  
1421 Research Park Dr 

Lawrence, KS 66049 

**9\. Cabling Diagram:** 

The default mating connector used for the LR-D1 is the BINDER 99-0425-10-08 circular connector, pictured below in Figure 4\. 

**Figure 4: 6-Wire Cable with BINDER 99-0425-10-08 Connector** 

The BINDER 99-0425-75-08 90° connector can be provided for an additional cost at the time of purchase. See Figure 5\. 

**Figure 5: 6-Wire Cable ith BINDER 99-0425-75-08 Connector** 

**Figure 6: BINDER 99-0425-10-08 & BINDER 99-0425-75-08 Connector Dimensions.** 

**Proprietary information**  

**Page 19**  
1421 Research Park Dr 

Lawrence, KS 66049 

**10\. Known Issues** 

LR-D1 is a product still in development. Table 4 lists the known issues that will be addressed in later revisions. 

**Table 4: LR-D1 Known Issues** 

| Issue ID | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Notes                                                                                                                                                                                                                                                                                                                           |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1        | If the LR-D1 is mounted at the position of \< 1.4m, it would report ‘Unhealthy’ in the Out of Range Indication Byte or 1.4 m of range reading                                                                                                                                                                                                                                                                                                                                                    | ● Ignore all radar  detection readings if  Out of Range  Indication reports  Unhealthy  ● DO NOT consider  altitude data while on  the ground in this case  ● If the altitude is too  close, it means the  radar reported altitude  health is close to the  surface or target.  Please consider it as an  **‘Invalid’** report. |
| 2  3     | Altitude data from radar may have unexpected or incorrect readings if the application scenario is indoors. The reason is the multipath reflection of radar is complicated indoors, it may give unexpected or incorrect readings under this circumstance.  Altitude data from radar may have unexpected or incorrect readings if aircraft pitch and/or roll are beyond the radar’s detection angle (Azimuth 43°， Elevation 30°). The ideal case is keeping the radar perpendicular to the ground. | ● DO NOT apply radar in any indoor  application scenario  ● Add a gimbal with  radar mounting  ● DO NOT consider any altitude data as valid if  the aircraft’s pitch  and/or roll are beyond  the radar’s detection  angle.                                                                                                     |
| 4        | Voltage alert is monitoring multiple node voltage on the radar’s hardware, some of their                                                                                                                                                                                                                                                                                                                                                                                                         | ● Check the input  voltage                                                                                                                                                                                                                                                                                                      |

**Proprietary information**  

**Page 20**  
1421 Research Park Dr 

Lawrence, KS 66049 

|    | thresholds might be set too stringent and trigger alert frequently in some scenario, we are evaluating to extend the acceptable thresholds to resolve it | ● Cool down the device and improve the heat  dissipation  ● Notify Ainstein if this alert still reports  frequently after trying  out above solutions |
| :- | :------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |

5 Overflowed Reading ● The altitude for the two spots in the below 

figure are: 

○ 655.35 \+ 0.43 \= 

**655.78 m** 

○ 655.35 \+ 143.89 \= 

**799.24** m 

● It is user’s decision to 

discard or accept the 

overflowed reading 

**Proprietary information**  

**Page 21**  
1421 Research Park Dr 

Lawrence, KS 66049 

**11\. Firmware Change Log:** 

The LR-D1 current firmware version is 19.0.0.1. Its development is noted in the following table. For older FW versions, reach out to Ainstein. 

**Table 5: LR-D1 Firmware Change Log** 

|    Firmware Version    | Release Date | Notes                                                                                       |
| :--------------------: | :----------: | ------------------------------------------------------------------------------------------- |
| 18.0.1.1  \[Obsolete\] |  01/29/2023  | ● First released firmware on LR-D1 hardware V2.2                                            |
| 18.0.1.2  \[Obsolete\] |  02/02/2023  | ● Maintain performance from 18.0.1.1  ● Add production mode for manufacturing               |
|        18.0.1.3        |  05/11/2023  | ● Maintain performance from 18.0.1.2  ● Fixes the voltage monitor reading consistency issue |

● Add Out of Range Indication in Data 12  
19.0.0.0 

\[Obsolete\] 6/30/2025 

● Fixed a bug of serial port stop reporting data in 

v19.0.0.0  
19.0.0.1 10/29/2025 

**Proprietary information  Page 22**  
1421 Research Park Dr 

Lawrence, KS 66049 

**12. Firmware Update Instructions:** 

**Remote Firmware Update** 

To update the firmware: 

1\. Open the GUI application 

2\. Select the Serial Port connected to the LR-D1. 

3\. Set the Baud Rate to 115200\. 

4\. Select the version to “Gen2”, it indicates LR-D1 V2.2 

5\. Click Browse and select the desired .bin file. 

**Note:** From firmware v18.x.x.x, both RS-232 and RS-422 units use the same firmware bin file. 

6\. Click Load to update the firmware on the LR-D1. 

7\. Upon successful completion of the firmware update, the device will automatically restart. 

**Figure 7: LR-D1 “main” Firmware Update GUI** 

**Proprietary information**  

**Page 23**  
1421 Research Park Dr 

Lawrence, KS 66049 

**13\. Contact US** 

**ADDRESS:** 

1421 Research Park Dr., 

Lawrence, KS 66049 USA 

EMAIL: 

[hi@ainstein.ai](mailto:hi@ainstein.ai) 

PHONE: 

785-424-7194 

**Proprietary information**  

**Page 24**  
1421 Research Park Dr 

Lawrence, KS 66049 

**Appendix 1: Malfunction Alert Information List** 

**Caution\!** If the data received for the malfunction alert code is not equal to 0x00 (Normal function) for data 5 and data 6 found in **Table 2: Data Packet Definition**, then please do not use the data packet and filter it out. 

There are four types of alerts open to the end users, the type of alert can be distinguished by its special code below. 

There are two Bytes of data reserved for the Malfunction Alert. All four types of alerts are represented by a bit in this Byte. For example: 

● 0x0001 (0b0000000000000001) of the temperature alert is represented by the bit-0 of the Malfunction Alert Byte; 

● 0x0002 (0b0000000000000010) of the voltage alert is represented by the bit-1 of the Malfunction Alert Byte; 

● 0x4000 (0b0100000000000000) of the IF signal saturation alert is represented by the bit-6 of the Malfunction Alert Byte; 

● 0x8000 (0b1000000000000000) of the altitude reading overflow alert is represented by the bit-7 of the Malfunction Alert Byte; 

Also, some of these Malfunction Alerts might be combined. For example: ● 0x0003 (0b0000000000000011) of the temperature alert and the voltage alert ● 0x4003 (0b0100000000000011) of the temperature alert, the voltage alert, and the IF signal saturation alert 

For obsolete Firmware (before v18.x.x.x), please contact Ainstein for a solution. 

For Firmware from v18.X.X.X: 

| Malfunction Alert Code | Malfunction Alert  Info | Possible  Reasons                                                                        | Suggestion                       |
| ---------------------- | ----------------------- | ---------------------------------------------------------------------------------------- | -------------------------------- |
| 0x0001                 | MCU Temperature alert   | Error in the  device or  ambient  temperature is out of LR-D1’s operational  temperature | Stop using and contact  Ainstein |

**Proprietary information**  

**Page 25**  
1421 Research Park Dr 

Lawrence, KS 66049 

|                 0x0002 | MCU Voltage alert                                                            |                                                                                                                                                                                     | Error in device Stop using and contact Ainstein for evaluation.                                                                                                                                                                      |
| ---------------------: | :--------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                 0x0010 | IF Temperature alert                                                         | Error in the  device or  ambient  temperature is out of LR-D1’s operational  temperature                                                                                            | Improve the heat dissipation. If the issue still remain, stop using and contact Ainstein  Note: Long time operation in the static scenario (e.g. indoor testing) might bump the temperature significantly and report this alert code |
| 0x0080  0x0100  0x0400 | IF signal saturation alert  Software alert  Altitude reading  overflow alert | The reflection signal received by LR-D1 is  overloaded  Malfunctions occur in the  software  The altitude  reading is  greater than  the maximum integer of  16-bit (655.35 meters) | Occurs when LR-D1 is within 1.4m of the ground.  Check if there is any other target within LR-D1’s FoV Stop using and contact  Ainstein  Occurs when LR-D1 detects the altitude is greater than 655.35 meters.                       |
|                 0x8000 | Voltage alert                                                                | Error in device by  over-voltage or  under-voltage                                                                                                                                  | Check the supply-voltage. Recommended voltage range is 12\~28V  Note: Minimum of 10V of supply-voltage is sufficient to operate the device, however it might trigger this alert code.                                                |

**Proprietary information**  

**Page 26** 

[image1]: data:image/png;base64,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y5ZBjxspJObNmye1Hr0/gs0+xm2okHDffu2118pllIYOHo8h4bueApokERA48dBuANFmgPKf//znYlpamunZs2fYyw07JFS0E8CpU6ea06dPB0ICXagIgXCiexJBhZPd/XgIiUWLFon278IlwqxZszyPZattCtmFhIoeELhhw4aQ4USTqqeAJkmGBEMij+gpoEn0mmuu8ZQhLGCjRo3EcuXKibitbNmygeNw0tv3ta1SpUogdAoVKmRq164d1rvvvluq+/ZjIMxuu+020b4N3nrrraZWrVqi/Zjqr3/9axGPDzW48Jzsx3OLRs9q1ap5ymlS9RRQSqlbTwGllLr1FFBKqVtPAaWUuvUUUEqpW08BpZS69RRQSqlbTwGllLr1FFBKqVtPAaWUuvUUUEqpW08BpZS69RRQSqlbTwGllLr1FFBKqVtPAaWUuvUUUEqpW08BpZS69RRQSqlbTwGllLr1FFBKqVtPAaWUuvUUUEqpW08BpZS69RRQSqlbTwGllLr1FFBKqVtPAaWUuvUUUEqpW08BpZS69RRQSqlbTwGllLr1FFBKqVtPAaWUuvUUUEqpW08BpZQG/B9gum6TbodZLgAAAABJRU5ErkJggg==

[image2]: data:image/png;base64,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

[image3]: data:image/png;base64,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