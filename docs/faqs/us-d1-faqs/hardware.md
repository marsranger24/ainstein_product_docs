---
title: Hardware Support FAQs
deprecated: false
hidden: false
metadata:
  robots: index
---
> 📘 Note that customer questions are **bolded** and _italicized_, while Ainstein responses are not.

## US-D1 Functionality

_**When determining the altitude reading, how does the radar determine which surface will be used?**_

The terrain surface is a distributed target (over a substantial amount of the US-D1s field of view).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cfe647c9f325ac3193627388aa903fa796412c783c2570649d28fefe8bc3e684-Screenshot_2026-01-26_at_5.14.19_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


The shortest distance to the ground from the altimeter is generally the one providing the strongest SNR return, and the signal fades as users radiate outwards from that point.

## US-D1 Low altitude discrepancy/Multipath Reflections

**_I. What are common causes of noisy or incorrect data from the US-D1?_**

1. An indoor scenario may not be the ideal case to test the US-D1 radar, because there are too many unexpected objects that might affect the radar's performance (multi-path reflection). Moving to the outdoor scenario would be helpful.
2. If there is material within the radar's FOV that is metal or other strong reflection materials, it can possibly affect the radar's performance. Even if it is out of the 43-degree window, there is a possibility of affecting the performance.
3. If the material on the airframe on which the Radar is mounted is metallic or other strong reflection materials, it could also affect the performance, especially in the indoor scenario.

## US-D1 Cable Length

**_I. What is the maximum allowable cable length for the US-D1?_**

Only the offered options are 0.5m and 1m. Maximum length depends on the communication protocol. UART TTL allows for a maximum of 15 m, while CAN has a recommended maximum of 40 m.

## US-D1 Connector/Connection

**_I. What connector is used on the US-D1, and what is the suggested mating connector?_**

Connectors available for the US-D1, including mates:

- Molex
  - Molex 4-pin 2.54mm connector
  - The Molex fits into PCB-mounted 2.54mm Molex Connector Headers, or can be simply used with jumper wires
- JST
  - JST 4-pin 1.25mm female socket connector
  - JST 4-pin 1.25mm outer shroud contact connector

It is recommended to use any 22 AWG shielded cabling.

**_II. How is the radar properly connected to the test tool to receive output from the software?_**

To use the US-D1 Bench Test Tool GUI, a US-D1 with UART protocol is required, and it should be connected to a PC using a USB-UART TTL converter. Here are the steps to connect the USB-UART TTL converter:

1. Plug in the USB-TTL converter to the USB port.
2. Plug in the TX (green) of the US-D1 into the RX of the USB-TTL converter.
3. Plug in the RX (white) of the US-D1 into the TX of the USB-TTL converter.
4. Connect the power (red) and ground (black) of the US-D1 to a 5V power supply.  
   Note: Ensure that the ground of the US-D1 is shared with the ground of the USB-TTL.  
   When connected to power, the US-D1 should boot at a current of 120 mA  
   for ~6 seconds. After this, the US-D1 will operate at a current of 330 mA at 5V.
5. Open the US-D1 Radar Altimeter Test Tool.

For Firmware Update Tool Instructions and Configuring the US-D1 Parameters, please refer to the [Firmware Update Tools](https://github.com/marsranger24/ainstein_product_docs/raw/refs/heads/v1.0/downloads/Ainstein_US-D1_Firmware_Update_Tool%20v2.2.0.1.zip) on Github, or visit the Firmware Files section on the left.

## US-D1 Out of Range

**_I. What is the expected sensor output in meters when the measurement is out of range, and is it normal for that reading to be non-zero?_**

Yes, this is normal. When the US-D1 is out of its maximum altitude range, the US-D1 will output its minimum measurement range at the edge of the radar blind zone, which is approximately 0.45m. In some instances, a “half height” value, which is a value between the height and 0, will be displayed. Additionally, when the US-D1 is utilized above its maximum altitude, the performance might be negatively affected by a variety of elements. One of the elements that could affect the performance is electronic feedback being received whilst out of range, which in turn provides inaccurate altitudes. The US-D1 will only be able to provide altitudes above its range when under ideal conditions.

## US-D1 Flight Over Terrain

**_I. What is the performance information when flying over water for the US-D1 model? How much does the accuracy and range typically lose?_**

Accuracy over water is a specific strength of radar altimeters compared with alternative telemetry equipment at lower altitudes.  Whereas light-based beams tend to penetrate through water, radar performance maintains high accuracy over water as on regular terrain. It is uncommon for radars to lose range fidelity over water.  Ainstein's radar altimeter, capable of ranges up to 50m (US-D1), often serves as complementary telemetry at lower altitudes under 200-300m, where GPS, Baro, or Optical technology may have difficulty.  Lower sea state levels offer optimum accuracy.

**_I. What causes the altitude of the radar to change when transitioning between different terrains?_**

Various terrains have different levels of reflectivity, causing the readings of the altitude to vary slightly. Additionally, transitioning between terrains with different densities of their foliage, such as a grass field to a forest, can cause the radar to change its readings. Depending on the density, the radar can vary between detecting the top and bottom of the foliage.

## US-D1 Radar Altimetry for Seaplanes

**_I. What are the capabilities of the US-D1 being mounted on the landing gear of a manned aircraft for both water and land takeoffs and landings?_**

The US-D1 is, like any sensor, subject to error when used improperly or on rare occasions when circumstances are unfavorable. For example, all radar sensors are subject to multipath propagation, which can result in erroneous measurements in altitude. Therefore, any application that can be life-threatening shall not be reliant on one sensor alone. The US-D1 is ultimately a reference altimeter. Please consider using multiple sensors and/or sensor fusion to provide redundancy in altitude measurements and to account for adverse circumstances.

Second, when operating in conditions that require precision, caution is advised, and it is recommended that users perform thorough in-flight testing to validate its performance prior to normal use. Although radar outperforms laser altimeters in measuring AGL altitude while flying over water, it is still subject to error in those circumstances.

Third, the US-D1 has not yet been FAA-approved and is therefore not adherent to 14 CFR § 135.160 requirements. Although the manufacturing facility adheres to ISO-9001 standards, Ainstein is not AS9100 compliant. The US-D1 is designed for use in UAS applications, not manned flight.

## US-D1 Installation Orientation/Mounting/Field of View

**_I. Is the US-D1 able to be tuned to be carried internally to the fuselage of the UAV (i.e., measuring through a 1/16" wall of polymer), or does it always need to be externally mounted?_**

Ainstein always recommends keeping the radome free from blockage to ensure optimal performance. Also, it is recommended to keep the unit's field of view free from other components on the plane, such as the landing gear, to avoid any false reflections from them.

**_II. Can the radar altimeter be used for a collision avoidance system?_**

The US-D1 was designed as a radar altimeter device and therefore provides altitude and SNR information to the user. Users are not advised to employ the US-D1 in collision avoidance applications, as they do not provide the functionality required for collision avoidance applications.

**_III. How do the view distances change for different angles? For example, if the radar is placed at a 90-degree angle to the nose._**

The radar altimeter was designed to be mounted parallel to the terrain below, facing the ground. The US-D1’s maximum distance reading is ~50m, but this has not been tested with objects in front of the aircraft.

**_IV. Does the radar altimeter system warn users about natural obstacles (i.e., mountains, birds, etc.) and aircraft such as UAVs or airplanes?_**

The US-D1 does not provide classification for natural obstacles or other aircraft. Changes in detected altitude do allow users to be aware of changes in terrain, however.

**_V. How does the return value of the radar degrade as the angle relative to the ground changes, and at what angle should the data no longer be relied upon (i.e., a drone pitches forward and changes the radar’s angle relative to the ground by up to 20 degrees)?_**

The US-D1's field of view is 43° x 30°, as pictured below. Therefore, if the intent is to tilt the aircraft to a greater degree in a particular direction, it is recommended to orient the US-D1 to account for that.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fb309eac9565003fce02995136bca0be629f32409bfbf59251368899216f119d-Screenshot_2026-01-26_at_6.26.10_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true,
      "caption": "Figure 4: Field of View Orientation of US-D1"
    }
  ]
}
[/block]


The 43° lobe width is the limit where the transmitted signal power is 25% of its maximum power (which is transmitted at the antenna's boresight). Generally, the recommendation is that the user does not exceed 21.5° of tilt for this reason. If there is a strong reflection (> 6 dB) from somewhere out of 43 degrees, it still could affect the Radar's performance.  Large bodies allow for more multipath reflections to be received. However, the US-D1's performance at angles of tilt is dependent on the terrain below the aircraft as well as the altitude above the ground.

The simplest way to verify whether users are still getting good radar detection at higher angles of tilt is to check the SNR of the altitude values. If users are able to collect the SNR values when performing these maneuvers, they could simply ensure that these values are still above 13 dB, or, to be very safe, 20-30 dB.  When mounting the radars, try to mount them near the outside of the aircraft so that there is less chance for interference from multipath reflections.

**_VI. What effects can be expected when using the radar altimeter close to propellers?_**

The radar altimeters could be impacted by the multipath reflection between the ground and the propulsion/rotor. Especially when the rotor is rotating, it will create a relative micro-movement in the multipath reflection and bring a Doppler frequency shift. It might couple with the range detection frequency and cause the wrong range reading. Some suggestions to help resolve this issue would be:

1. If possible, move the mount position of the radar altimeter further away from the rotor or to the edge of the propulsion to see whether the issue can be resolved or at least improved. The purpose of this is to reduce the multipath reflection and mitigate the Doppler frequency effect by the rotor. If possible, mount the radar outside of the path of the propeller, as seen in the image below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fd50d71dce530c877400129b82b287572803b4a24d2a3f95d3ef6d5d8b285168-Screenshot_2026-01-26_at_6.28.19_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


2. If possible, apply some foam around the radar altimeter to reduce the multipath reflection. The purpose of this is to reduce the multipath reflection. It would be better to have a microwave-absorbing form, but it is okay to use general foam first to see if any improvement occurs.

## US-D1 Temperature/Pressure/Shock/Vibration Specifications

**_I. What is the radar altimeter’s survival after exposure to storage temperature?_**

It is recommended that the radar altimeter be stored at room temperature. The US-D1's operational temperature range is -20°C to 65°C; therefore, if the RALT is stored within this range, it should not cause any damage to the unit.

**_II. Has the operation of the US-D1 been verified at temperatures lower than -20 degrees Celsius?_**

The US-D1's operational temperature range is -20°C to 65°C, as some of the components on the radar are commercial-grade components. Prolonged usage of the radar below -20°C is not recommended.

**_III. Is the RALT designed to withstand salt atmosphere exposure? To prevent corrosion?_**

The US-D1 has an IP rating of IP67. It is, therefore, highly protected against dust and water exposure to the electronics. The enclosure of the US-D1 is resistant to corrosion by various salts. The US-D1 is well protected against surface corrosion.

## Ground Test Procedure

A proper way to ground test could include attaching the radar to an extendable tripod, facing the ground, and raising it to the desired altitude. When the radar is mounted, moving it forward, backward, and to the sides will help users view “altitude” changes and validate data.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b527dabd9acd79461a477fec4af710e94f90aa4c57d4659c45519fffd0dc196-Screenshot_2026-01-26_at_6.30.42_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Another way could be to mount the radar on an extendable tripod, oriented horizontally at a large object. Raise the radar above 3 m to avoid false readings to the ground or other shorter objects. When the radar is mounted, moving it forward, backward, and to the sides will help users view “altitude” changes and validate data.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3354fba6a89247a074a75f4c18787c2bbed5418b6c6ab0ce50880ea288fd033e-Screenshot_2026-01-26_at_6.31.38_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]