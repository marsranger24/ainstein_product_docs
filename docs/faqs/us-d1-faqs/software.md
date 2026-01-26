---
title: Software Support FAQs
deprecated: false
hidden: true
metadata:
  robots: index
---
**Note that customer questions are bolded and italicized while Ainstein responses are not.** 

## US-D1 Data Processing

**_I. What does the firmware do to process raw data? Is the raw data filtered or averaged in any way?_**

The US-D1 has a single-input and single-output antenna design for measuring range.  The radar altimeter transmits a frequency-modulated continuous wave throughout the entire FOV.  This beam is reflected off the terrain and received by the altimeter. The received data is used to construct a fast Fourier transform, where the result of the FFT is a set of amplitudes of certain frequencies, such as in the figure shown below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/72107b316c4e500daf3b195280a8650c2b5e4c47743ac359155ecb704de66f86-Screenshot_2026-01-26_at_4.38.00_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Each frequency on the FFT spectrum is representative of a particular distance from the altimeter. In general, the frequency of the highest amplitude is representative of the true distance from the sensor.

Therefore, the strongest peak within a given sample is selected and recorded by the US-D1.  The result is then output as the single altitude reading with its corresponding signal-to-noise ratio value.

The value of the FFT spectrum that has the highest amplitude is dependent on several factors:

- Distance to the radar
- Reflected angles of transmission
- RCS (Radar Cross Section)

The single altitude reading of the sensor is filtered with a simple moving average and median filter to avoid excessive noise. 

When the radar is out of the 50m range, it will output a measurement of the minimum range of detection (the edge of the blind zone of the radar). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1869eac7ff5425d4e0dbe9dfeab0206d1f576b723ba624619bd09c40ff609852-Screenshot_2026-01-26_at_4.40.35_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


## US-D1 Altitude Readings out of the Recommended Window

**_I. What happens when the US-D1 is below its minimum range of 0.5 meters?_**

The US-D1 has been designed to output measurements below 0.5m. Furthermore, it can output data from 0.0m to 50.0 m, with some customers displaying valid detection up to 140m.

The US-D1 has a blind zone that is ~0.43m in length, meaning that its measurements below 0.43m are less reliable and will often be reported with a low SNR value. When it is in use below the minimum altitude of 0.5 m, the close proximity of the surface can cause saturation of the signal in the US-D1, which leads to reported altitudes higher than expected. 

**_II. What happens when the US-D1 is above its maximum range of 50 meters?_**

When the US-D1 is utilized above its maximum altitude, the performance might be negatively affected by a variety of elements. One of the elements that could affect the performance is electronic feedback being received whilst out of range, which in turn provides inaccurate altitudes. The US-D1 will only be able to provide altitudes above its range when under ideal conditions. 

## US-D1 Power

**_I. What is the approximate time it takes between applying power to the radar and the display of the initial readings?_**

It takes 6 seconds for the booting to start and run before readings are output.

**_II. It is written on the datasheet that 5.5V is the recommended power. What are the drawbacks of using 12V?_**

There aren't any drawbacks to using 12V as the operating voltage for the US-D1. It will function properly when given an input voltage within the range of 5V - 12V.

**_III. Does the US-D1 have a command to turn off radiation?_**

The US-D1 radiates as soon as it is powered on and does not have a command to turn the radiation off.

**_IV. What happens if the supply voltage is less than or greater than the recommended range of 5 - 13 V?_**

If the supply voltage is consistently below 5 V, the radar will not function properly. If there is a temporary small drop (4.9 V), then the radar’s function will most likely still suffice.

Exceeding the recommended voltage of 13 V could potentially cause issues and even harm the unit.

## US-D1 CAN

**_I. The technical manual mentions that US-D1 can be configured to standard CAN IDs instead of extended, but that is not seen as an option in the Firmware Update Tool, and the manual does not provide a reference on how to change this._**

Ainstein’s US-D1 radar only works with an extended CAN ID currently, which has the default of 0x00090002, but if needed, it is possible to change the ID, which is still extended. The steps for this are in the User Manual on our website: <https://ainstein.ai/us-d1-all-weather-radar-altimeter/>.

**_II. In the instance that the CAN bus is working at 250 kbps, can it be connected to a US-D1 with a baud rate of 1 Mbps? How can the baud rate of the US-D1 be changed?_**

If the baud rate is 1 Mbps, it can not be connected to a CAN bus at 250 kbps. The baud rate of the US-D1 can be configured by the firmware update kit, which can be purchased online here: [US-D1 Firmware Update Kit](https://sensing.ai/collections/ainstein-radar-products/products/us-d1-firmware-programming-kit).

<br />

## US-D1 Auto Pilot Connection

**_I. Is the US-D1 plug and play with ArduPilot, and what are the setup instructions?_**

Yes, the US-D1 can easily be used with ArduPilot via CAN, DroneCAN, and UART. The parameter configuration for doing this is provided on the Ardupilot US-D1 page.  
To set up the US-D1 CAN interface with Mission Planner, perform the following steps:

1. Once the US-D1 is connected, open Mission Planner and connect to the flight controller.
2. Edit the following parameters, then restart the flight controller:

- CAN_P1_DRIVER = 1 (first can port driver set to driver 1)
- CAN_D1_PROTOCOL = 7 (USD1 protocol for driver 1)
- RNGFNDx_TYPE = 33 (USD1_CAN)
- RNGFNDx_MIN_CM = 50
- RNGFNDx_MAX_CM = 4500
- RNGFNDx_GNDCLEAR = 0.1, \_or more accurately, the distance in centimeters from the range finder to the ground when the vehicle is landed. This value depends on how the rangefinder is mounted._

To set up the US-D1 DroneCAN interface with Mission Planner, perform the following steps:

1. Once the US-D1 is connected, open Mission Planner and connect to the flight controller.
2. Edit the following parameters, then restart the flight controller:

- CAN_P1_DRIVER = 1 (first can port driver set to driver 1)
- CAN_D1_PROTOCOL = 1 (DroneCAN protocol for driver 1)
- RNGFNDx_TYPE = 24 (enable DroneCAN rangefinder type)
- RNGFNDx_MIN_CM = 50
- RNGFNDx_MAX_CM = 4500

To set up the US-D1 UART interface with Mission Planner, perform the following steps:

1. Once the US-D1 is connected, open Mission Planner and connect to the flight controller.
2. Edit the following parameters, then restart the flight controller:

- SERIALx_PROTOCOL = 9 (Rangefinder)
- SERIALx_BAUD = 115 (115200 baud)
- RNGFNDx_TYPE = 11 (USD1-Serial)
- RNGFNDx_MIN = 0.5
- RNGFNDx_MAX = 45
- RNGFNDx_GNDCLR = 0.1 \_or more accurately the distance in centimeters from the range finder to the ground when the vehicle is landed. This value depends on how the rangefinder is mounted_.

**_II. Is the US-D1 plug and play with PX4, and what are the setup instructions?_**

Yes, the US-D1 can easily be used with PX4 via DroneCAN and UART. The parameter configuration for UART can be found on the [PX4 US-D1 Page](https://docs.px4.io/main/en/sensor/ulanding_radar).

To set up the US-D1 DroneCAN interface with PX4, perform the following steps:

1. Once the US-D1 is connected, open QGroundControl and perform the following steps:

- UAVCAN_ENABLE= 2 or 3 (Option 2 enables the DroneCAN driver for sensors with the DNA server enabled, and option 3 enables the DroneCAN driver for sensors and ESCs with the DNA server enabled)
- Enable the UAVCAN_SUB_RNG parameter
- UAVCAN_RNG_MIN = 0.5 m
- UAVCAN_RNG_MAX = 50 m

Additionally, the following [link](https://docs.px4.io/main/en/dronecan/) provides an in-depth description of DroneCAN and its compatibility with PX4, along with a guide on how to enable a rangefinder via DroneCAN.

## US-D1 Datasheet

**_I. The SNR (byte 5) never changes, always showing as 00, and there is a variance from 63 to 101 cm at a static position of 100 cm. Is that an expected behavior on a proper functional unit?_**

This would suggest there is an issue present with the US-D1 unit received. Fully-functional units do not typically output an SNR value of 0 while displaying altitude measurements or a wide variance of altitudes when in a static position. Ainstein recommends power cycling the unit and reflashing the firmware if possible. If the issue persists, please contact Ainstein for assistance.

**_II. Does the MSB of the SNR in the CAN frame need to be inspected, considering it is not in the UART data packet?_**

The SNR should not go above the maximum value of the LSB, so the MSB of the SNR in the CAN frame can be disregarded.

## US-D1 Filtering

**_I. In the user manual, the update rate is listed as 100 Hz, but is there a low-pass filter applied to the received values?_**

Yes, a moving-averaging filter and a low-pass median filter are applied to smooth the radar detection.

**_II. What is an estimate of how much low-pass filtering is applied in terms of an equivalent bandwidth (e.g., 1 Hz)? In the sense that if the sensor is moved up and down faster than 1 Hz, the changes will not be seen?_**

The time delay due to the moving average filter of the US-D1, or "lag" in the following diagram, is approximately 170 ms.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/109c09715b1fe4b131ec08996acfcfea7a9b41179cd8bd451a4edf9e31ac5ba7-Screenshot_2026-01-26_at_5.05.23_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


## US-D1 Multi-Integration

**_I. When two US-D1s are mounted under a UAV, how can users be sure that the signal received by an altimeter is the one that was sent by this same altimeter and not by the other radar altimeter? Thus, is there a minimum distance between the two altimeters that must be implemented? Is it possible to configure the frequency of the signal?_**

The US-D1 sensor uses a slowchirp configuration that makes it very difficult for two sensors mounted side-by-side to exhibit interference with one another. Even if both sensors are directly next to each other, there is less than a 1% chance that they share the same signal phase with one another upon startup. Although the radars may be mounted as close together as desired, it is recommended to separate two radars by as much space as possible to avoid small chances of interference.