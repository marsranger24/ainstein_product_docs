---
title: QuickStart Guide - Setting up the US-D1 with PX4
deprecated: false
hidden: false
metadata:
  robots: index
---
# Notice

**The US-D1 is supported on PX4 versions v1.10 and newer. For US-D1 setup instructions, visit the [US-D1 PX4 page](https://docs.px4.io/main/en/sensor/ulanding_radar.html). For v1.10 instructions, visit the [PX4 v1.10 US-D1 instructions](https://docs.px4.io/v1.10/en/sensor/ulanding_radar.html). A short summary of the instructions is provided below. For more details, visit the PX4 website.**

To set up the US-D1 with Pixhawk, please follow the below instructions:

1. Fit the US-D1 with a Pixhawk-compatible connector.  
   **Note: The US-D1 is available for purchase with a 4-pin JST_GHR connector, which can be used to plug directly into any unused 4-pin serial port.**  
   **Note:  Within configuration the US-D1 is referred to as uLAND or uLANDING.**
2. Connect the US-D1 to any unused serial port (UART), e.g., TELEM2, TELEM3. I2C, GPS2, etc. Be sure to connect CAN protocol US-D1 units to an unused CAN port.
3. [Configure the serial port](https://docs.px4.io/main/en/peripherals/serial_configuration.html) on which the rangefinder will run using [SENS_ULAND_CFG.](https://docs.px4.io/main/en/advanced_config/parameter_reference.html#SENS_ULAND_CFG) There is no need to set the baud rate for the port, as this is configured by the driver.

_If the configuration parameter is not available in QGroundControl, then you may need to [add the driver to the firmware](https://docs.px4.io/main/en/peripherals/serial_configuration.html#parameter_not_in_firmware):_

CONFIG_DRIVERS_DISTANCE_SENSOR_ULANDING_RADAR=y

For further instructions or questions, visit the [PX4 US-D1 page](https://docs.px4.io/main/en/sensor/ulanding_radar.html) or the [PX4 support forum](https://docs.px4.io/main/en/contribute/support.html).