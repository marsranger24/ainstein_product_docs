---
title: >-
  QuickStart Guide - Appendix A: US-D1 Specifications and Performance
  Limitations
deprecated: false
hidden: false
metadata:
  robots: index
---
| Parameter                     | Value                                     |
| ----------------------------- | ----------------------------------------- |
| Frequency Band                | 24 GHz                                    |
| Bandwidth                     | 190 MHz                                   |
| Minimum Operating Altitude    | 0.5 meters                                |
| Maximum Operating Altitude    | 50 meters                                 |
| Altitude Precision            | 6.0 cm (\< 1m), 4.0 cm (> 1m), 2% (> 10m) |
| Field of View                 | 43° x 30°                                 |
| Compatible Interfaces         | UART, CAN, DroneCAN                       |
| Update Rate                   | 100Hz                                     |
| Supply Voltage                | 5V ~ 13V DC (5.5V recommended)            |
| Power Consumption             | 2W                                        |
| Operational Temperature Range | \-20 °C ~ 65°C                            |
| Size                          | 108 x 79 x 20 millimeters                 |
| Weight                        | 110 Grams                                 |
| Environmental Tolerance Grade | IP67 (with sealant)                       |

_All specifications above are measured in an environment with 35 °C temperature, standard atmospheric pressure, and humidity without electromagnetic interference (EMI).  
The Operational Temperature Range indicates that radar works properly in this range. If the operating temperature goes beyond this range, the radar might not be accurate and can suffer mechanical damage.  
The radar unit can be shipped with either CAN or UART for its output data protocol._

- **Operational Temperature Range is based on the hardware’s subcomponent specifications. Actual operational testing is still pending.**

The US-D1 will support accurate data within its 0.5 to 50 m altitude range. However, if the radar is mounted and operated below or above this range, its operation may vary.

If the US-D1 is mounted below 0.5m, RF saturation may occur. This can lead to unexpected, unreliable readings. An example of this reading can be found in the Figure below. 

During installation, testing, and observation, if similar behavior is observed, revise the distance between the US-D1 and the ground. If the distance is below the range of operation of the US-D1 , the behavior is caused by the explanation above. Following all safety measurements, you can continue testing and operating the US-D1 in its designed range. If the unexpected behavior continues within the range, contact Ainstein’s Technical Support team.

Similarly, when the US-D1 is operating above its designed range of operation, unexpected readings may become present. The figure below illustrates an example of US-D1 recorded altitude in operation above 50 m. 

This behavior is due to the US-D1 signal being unable to find a return due to the out-of-range target. If a similar behavior is encountered while using the Radar Altimeter, verify the altitude at which the behavior and unexpected reading occur. If they appear within the 0.5 – 50 m range, contact Ainstein’s Technical Support team.