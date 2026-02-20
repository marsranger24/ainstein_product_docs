---
title: QuickStart Guide - Setting up the US-D1 Pro with DroneCAN
deprecated: false
hidden: false
metadata:
  robots: index
---
# Notice

The US-D1 Pro is supported on both ArduPilot and PX4 autopilot software via DroneCAN. For additional DroneCAN rangefinder setup instructions, visit the [ArduPilot DroneCAN forum](https://ardupilot.org/copter/docs/common-uavcan-setup-advanced.html) or the [PX4 DroneCAN forum](https://docs.px4.io/main/en/dronecan/).

# Setting up PX4 with DroneCAN

To connect the US-D1 Pro to PX4 via DroneCAN, please follow the instructions below:

1. Fit the US-D1 Pro with a PX4-compatible connector.  
   Note: The US-D1 Pro is compatible with both private CAN and DroneCAN interfaces upon purchase. Please refer to section 2.2.1 for the pinout requirement for DroneCAN compatibility.
2. Connect the US-D1 Pro to any unused CAN port.
3. Set the UAVCAN_ENABLE parameter to either option 2 or 3. Option 2 enables the DroneCAN driver for sensors with the DNA server enabled, and option 3 enables the DroneCAN driver for sensors and ESCs with the DNA server enabled.
4. Enable the UAVCAN_SUB_RNG parameter, setting the UAVCAN_RNG_MIN and UAVCAN_RNG_MAX values to the user-specified minimum altitude (0.5 m to 2 m) and 120 m, respectively.

For further instructions or questions, please visit the [PX4 DroneCAN Page](https://docs.px4.io/main/en/dronecan/) or the [PX4 Support Forum](https://docs.px4.io/main/en/contribute/support.html).

# Setting up ArduPilot with DroneCAN

<br />

To connect the US-D1 Pro to ArduPilot via DroneCAN, please follow the instructions below:

1. Fit the US-D1 Pro with an ArduPilot-compatible connector.  
   _**Note: The US-D1 Pro is compatible with both private CAN and DroneCAN interfaces upon purchase. Please refer to section 2.2.1 for the pinout requirement for DroneCAN compatibility.**_
2. Connect the US-D1 Pro to any unused CAN port.
3. Set the following parameters:  
   [CAN_P1_DRIVER](https://ardupilot.org/copter/docs/parameters.html#can-p1-driver) = 1 (first can port driver set to driver 1)  
   [CAN_D1_PROTOCOL](https://ardupilot.org/copter/docs/parameters.html#can-d1-protocol) = 1 (DroneCAN protocol for driver 1)  
   [RNGFND1_TYPE](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-type) = 24 (DroneCAN)  
   [RNGFND1_MIN_CM](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-min-cm) = 50-200 (Minimum altitude determined by user)  
   [RNGFND1_MAX_CM](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-max-cm) = 12000 (Maximum altitude set to 120 m)

_**NOTE:**_

- _**When connecting the US-D1 Pro to a public-facing autopilot, users must ensure that the RNGFNDX_ADDR parameter matches the sensor ID of the radar (i.e., if Sensor ID = 1, then RNGFNDX_ADDR = 1)**_
- _**When multiple devices with the same ID are swapped on the same CAN database of a flight controller, a duplicate node prearm message can pop up. The [CAN_D1_UC-OPTION](https://ardupilot.org/plane/docs/parameters.html#can-d1-uc-parameters) parameter can be utilized to clear this message. When looking at the forum, users can see that option 0 will clear the DNA database. In Mission Planner, the option to clear the DNA database is a troubleshooting step to resolve network conflicts when replacing or swapping CAN devices. However, if users do not want to clear the DNA database, option 1 allows for the DNA node conflicts to be ignored. Please note that the flight controller must be power cycled for the changes to be implemented.**_

For further instructions or questions, visit the [Ardupilot DroneCAN Page](https://ardupilot.org/copter/docs/common-uavcan-setup-advanced.html) or the [Ardupilot support forum](https://discuss.ardupilot.org/).