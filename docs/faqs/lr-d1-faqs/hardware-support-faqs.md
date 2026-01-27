---
title: Hardware Support FAQs
deprecated: false
hidden: true
metadata:
  robots: index
---
> 📘 Note that customer questions are **bolded** and _italicized_ while Ainstein responses are not.

<br />

## Velocity/Altitude/Pitch/Roll Parameters

I. For the integration of the LR-D1 to a fixed-wing operation, what are the capabilities of the following parameters?

- Operational Velocity:  
  The LR-D1 has been tested in flights with horizontal speeds of up to 200 m/s. The LR-D1 is designed for vertical speeds of up to 30 m/s.
- Altitude Range:  
  The LR-D1 has a range of 1.4 - 500 m.
- Pitch  
  The LR-D1 supports up to a pitch of ±21.5 deg.
- Roll:  
  The LR-D1 supports a roll of up to ±15 degrees.  
  Exceeding the angles may cause the performance of the LR-D1 to worsen. Sensitivity increases with altitude.

## LR-D1 Connection

**_I. Can the LR-D1 be connected to an autopilot using the RS-232 interface with either the I2C2 (I2C_2_SCL/I2C_2_SDA) or GPS2 (MCU_TX/MCU_RX) ports?_**

The I2C2 port has the following pins:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d0eaf8a0c069128cc683b16be4adfd98c0316ff1fef14649cc8a52bbfb95645e-Screenshot_2026-01-26_at_6.37.20_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


The GPS2 port has the following pins:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/afe9243f91697830cac9c539131a248638ba8002271227557ea0b3fb7635016f-Screenshot_2026-01-26_at_6.37.53_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


The LR-D1 has the following pins:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce3c920a65994adaa89e9025ba0fa98cc30cdc17667edc896920fc4e1e8917a3-Screenshot_2026-01-26_at_6.38.25_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


RS-232 was selected as the default communication protocol of the LR-D1 because the higher voltages of the RS-232 signal make it less susceptible to noise, interference, and degradation, which is advantageous for the altimeter.

<br />

**_II. What is the process of creating a physical connection between an LR-D1 RS-232 unit and an autopilot?_**

To interface with any flight controller featuring ArduPilot, it is recommended to use an RS-232 to TTL converter to convert the signal to TTL serial. Then the LR-D1 can be connected to any spare serial/UART port, such as the UART4 GPS2 port (MCU_TX/MCU_RX). Any converter module using a MAX232 chip should work.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d6279f2bfab6d3f570b391211459c2e95cba30c91b73691f6972151819a93845-Screenshot_2026-01-26_at_6.39.38_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


**_III. Considering the LR-D1-422 has two dedicated power input pins allocated on its connector, is one power pin sufficient to power the unit? Does it contain internal diodes for powering, or is an external diode module required?_**

One power pin is sufficient to power the unit.  
The LR-D1 does have hardware that prevents backflow current. This includes an ESD, an anti-reverse current diode, and a 2A fuse.

## Installation Orientation/Mounting/FOV

**_I. What is the recommended installation orientation for a fixed-wing aircraft?_**

For a fixed-wing aircraft, the LR-D1 should be mounted on the belly of the aircraft perpendicular to the ground, allowing the radar to be unobstructed in its 43° x 30° field of view. Ainstein recommends that users not mount the LR-D1 with tilt angles in excess of 10°. The device should be secured to the aircraft, where it is not free to move in any direction, or exposed to vibration in excess of 5 Gs.

**_II. What are the guidelines and operations for the installation and operation of side-by-side units?_**

It is not recommended. However, if it is a necessity, then Ainstein recommends mounting the two units as far as possible, given the allowable surface area on the hull of the aircraft. The greater the distance between the two units, the less the likelihood there is of interference between the two.

**_III. What is the maximum recommended angle for radar altimeter mounting to still achieve robust measurements?_**

Generally speaking, it is recommended that customers do not mount the LR-D1 with tilt angles in excess of 10°, but depending on the use case, angles beyond that range may still be able to provide valid detection.

**_IV. How does the radar perform when propeller blades pass directly through its field of view?_**

Because radar is sensitive to detecting high-velocity objects, Ainstein anticipates that mounting above the propeller blades would significantly disrupt the LR-D1's detection.

**_V. If a skid is in the field of view, is there a robust way to make the radar altimeter ignore that?_**

It may be possible to implement an algorithm to avoid detecting a skid that is always at the same distance from the LR-D1. This would most likely involve collecting raw radar data from the LR-D1 as it is mounted on the UAV in a variety of flight scenarios.

The preferred option would be to find a way to mount the radar to be free from any FOV blockage and maintain a small tilt angle.

<br />

**_VI. The LR-D1 is listed as able to see through a fiberglass laminate. Is there a suggested thickness of the laminate to allow the unit to still function properly? What materials can be in the LR-D1’s field of view, and what is the recommended installation?_**

Providing a hole for the altimeter to directly face the terrain without any obstacles in the field of view is preferred for the performance of the radar. It is strongly suggested to use this method. 

The LR-D1 could potentially see through a fiberglass laminate, but the radar performance is dependent on three factors: the type of material used, the distance away from the radome of the radar, and the thickness of the laminate. If the plan is to install the LR-D1 behind a material such as glass fiber, the suggestion is to empirically test how to optimize the performance in the specific installation scenario.

**_VII. Is there a cone that could be drawn to visualize the field of view of the LR-D1?_**

To visualize the field of view of the LR-D1, draw a 43-degree x 30-degree field of view, as shown below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b9f15f72c25719aac36fa52af70a8bfaca62237c47b9a89e907395c4b6fa5c78-Screenshot_2026-01-26_at_6.44.02_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/408fcd80d1943a097558d66fa5e57fde55740c160f3eecb87e04402258cde70a-Screenshot_2026-01-26_at_6.44.39_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


**_VIII. How do the view distances change for different angles? For example, if the radar is placed at a 90-degree angle to the nose._**

The radar altimeter was designed to be mounted forward-facing and parallel to the terrain below. The LR-D1’s maximum distance reading is ~500m, but this has not been tested with objects in front of the aircraft.

**_IX. Does the radar altimeter system warn users about natural obstacles (i.e., mountains, birds, etc.) and aircraft such as UAVs or airplanes?_**

The LR-D1 does not provide classification for natural obstacles or other aircraft.

**_X. Why is there a block of data with an irregular reading of 21 feet and SNR greater than 50 dB when facing the sky?_**

Usually, when the radar is out of range,

- Starting from Firmware v19.0.0.1, an altitude and SNR of 0 will be displayed, as well as an out-of-range indicator, which will be set to 0 for an invalid altitude.
- In firmware prior to v19.0.0.1, the minimum altitude of 1.4 will be displayed, and there is no out-of-range indicator.

The LR-D1 has a highly sensitive radio frequency receiver that allows for accurate altitude readings when the radar is oriented towards a distributed target. When the radar is pointed to the sky, however, there is no distributed target within its field of view. This, in turn, causes the peak detection algorithm to improperly function. Aside from flight tests, a simple way to field test the radar is to point the radar at a large target, such as a building or wall, and fluctuate the distance from the target to validate the “altitude change.”

With the release of FW v19.0.0.1, an out-of-range indicator was added to data byte 12.

**_XI. What is the recommended mounting position to improve thermal conduction?_**

The radar’s custom housing design is good for supporting its thermal conduction and toleration. To help improve the dissipation, it is recommended to mount the radar on any surface that is good for thermal conductivity.

## Ground Test Procedure

A proper way to ground test could include attaching the radar to an extendable tripod, facing the ground, and raising it to the desired altitude.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a16f099345d937e3d3667237e3195420c6799c00f393b95ee9d2668f293bce6-Screenshot_2026-01-26_at_6.30.42_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Another way could be to mount the radar on an extendable tripod, oriented horizontally at a large object. Raise the radar above 3m to avoid false readings to the ground or other shorter objects.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a6ebcf9fc23d94fa16582c1546d0303c5541c4afe106a1d48470fb997f271d6e-Screenshot_2026-01-26_at_6.31.38_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## LR-D1 Flight Over Terrain

**_I. Is there any performance information when flying over water for the LR-D1 model? How much does the accuracy and range typically lose?_**

Accuracy over water is a specific strength of radar altimeters compared with alternative telemetry equipment at lower altitudes.  Whereas light-based beams tend to penetrate through water, radar performance maintains high accuracy over water as on regular terrain. It is uncommon for radars to lose range fidelity over water.  Ainstein's radar altimeter capable of ranges 500m (LR-D1) often serves as complementary telemetry at lower altitudes under 200-300m where GPS, Baro, or Optical technology may have difficulty.  Lower sea state levels offer optimum accuracy.

**_II. What are the capabilities of the LR-D1 being mounted on the landing gear of a manned aircraft for both water and land takeoffs and landings?_**

The LR-D1 is, like any sensor, subject to error when used improperly or on rare occasions when circumstances are unfavorable. For example, all radar sensors are subject to multipath propagation, which can result in erroneous measurements in altitude. Therefore, any application that can be life-threatening shall not be reliant on one sensor alone. The LR-D1 is ultimately a reference altimeter. Please consider using multiple sensors and/or sensor fusion to provide redundancy in altitude measurements and to account for adverse circumstances.

Second, when operating in conditions that require precision, caution is advised, and it is recommended that users perform thorough in-flight testing to validate its performance prior to normal use. Although radar outperforms laser altimeters in measuring AGL altitude while flying over water, it is still subject to error in those circumstances.

Third, the LR-D1 has not yet been FAA-approved and is therefore not adherent to 14 CFR § 135.160 requirements. Although the manufacturing facility adheres to ISO-9001 standards, Ainstein is not AS9100 compliant. The LR-D1 is designed for use in UAS applications, not manned flight.

**_III. What causes the altitude of the radar to change when transitioning between different terrains?_**

Various terrains have different levels of reflectivity, causing the readings of the altitude to vary slightly. Additionally, transitioning between terrains with different densities of their foliage, such as a grass field to a forest, can cause the radar to change its readings. Depending on the density, the radar can vary between detecting the top and bottom of the foliage.