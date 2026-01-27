---
title: Setting up the US-D1 with ArduPilot
deprecated: false
hidden: false
metadata:
  robots: index
---
# Notice

**The US-D1 is supported on Arudpilot versions v4.00 and newer. For US-D1 setup instructions, visit the US-D1 Ardupilot page. A short summary of the instructions is provided below. For more details, visit the Ardupilot website.**

To set up the US-D1 with Ardupilot, please follow the below instructions:

1. Fit the US-D1 with a serial port-compatible connector. Note: the US-D1 is available for purchase with a 4-pin JST_GHR connector to plug directly into any unused 4-pin serial port.
2. Connect the US-D1 to any unused serial port (UART), e.g., SERIAL4, etc. For UART units, set the following parameters:  
   [SERIAL4_PROTOCOL](https://ardupilot.org/copter/docs/parameters.html#serial4-protocol) = 9 (Rangefinder)  
   [SERIAL4_BAUD](https://ardupilot.org/copter/docs/parameters.html#serial4-baud) = 115 (115200 baud)  
   [RNGFND1_TYPE](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-type) = 11 (USD1-Serial)  
   [RNGFND1_MIN_CM](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-min-cm) = 50  
   [RNGFND1_MAX_CM](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-max-cm) = 5000  
   [RNGFND1_GNDCLEAR](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-gndclear) = 10, or more accurately, the distance in centimeters from the rangefinder to the ground when the vehicle is landed. This value depends on how you have mounted the rangefinder.
3. For the CAN version, connect via CAN to the autopilot and set the following parameters:  
   [CAN_P1_DRIVER](https://ardupilot.org/copter/docs/parameters.html#can-p1-driver) = 1 (first can port driver set to driver 1)  
   [CAN_D1_PROTOCOL](https://ardupilot.org/copter/docs/parameters.html#can-d1-protocol) = 7 (USD1 protocol for driver 1)  
   [RNGFND1_TYPE](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-type) = 33 (USD1_CAN)  
   [RNGFND1_MIN_CM](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-min-cm) = 50  
   [RNGFND1_MAX_CM](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-max-cm) = 4500  
   [RNGFND1_GNDCLEAR](https://ardupilot.org/copter/docs/parameters.html#rngfnd1-gndclear) = 10 or, more accurately, the distance in centimeters from the range finder to the ground when the vehicle is landed. This value depends on how you have mounted the rangefinder.
4. For further instructions or questions, visit the [Ardupilot US-D1 page](https://ardupilot.org/copter/docs/common-aerotenna-usd1.html) or the [Ardupilot support forum](https://discuss.ardupilot.org/).