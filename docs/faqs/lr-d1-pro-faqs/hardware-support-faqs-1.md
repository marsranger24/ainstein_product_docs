---
title: Hardware Support FAQs
deprecated: false
hidden: false
metadata:
  robots: index
---
> 📘 Note that customer questions are **bolded** and _italicized_ while Ainstein responses are not.

## Velocity/Altitude/Pitch/Roll Parameters

**_I. For the integration of the LR-D1 to a fixed-wing operation, what are the capabilities of the following parameters?_**

- Operational Velocity:  
  The LR-D1 Pro has been tested in flights with horizontal speeds of up to 200 m/s. The LR-D1 Pro is designed for vertical speeds of up to 30 m/s.
- Altitude Range:  
  The LR-D1 Pro has a range of 0.3 - 500 m.
- Pitch:  
  The LR-D1 Pro supports up to a pitch of ±21.5 deg.
- Roll:  
  The LR-D1 Pro supports a roll of up to ±15 degrees.  
  Exceeding the angles may cause the performance of the LR-D1 Pro to worsen. Sensitivity increases with altitude

## Installation Orientation

**_I. What is the recommended installation orientation for a fixed-wing aircraft?_**

For a fixed-wing aircraft, the LR-D1 Pro should be mounted on the belly of the aircraft perpendicular to the ground, allowing the radar to be unobstructed in its 43° x 30° field of view. The recommendation is that customers do not mount the LR-D1 Pro with tilt angles in excess of 10°. The device should be secured to the aircraft, where it is not free to move in any direction, or exposed to vibration in excess of 15 g’s.

**_II. What are the guidelines and operations for the installation and operation of side-by-side units?_**

It is not recommended. However, if it is a necessity, then Ainstein recommends mounting the two units as far as possible, given the allowable surface area on the hull of the aircraft. The greater the distance between the two units, the less the likelihood there is of interference between the two.

## LR-D1 Flight Over Terrain

**_I. What causes the altitude of the radar to change when transitioning between different terrains?_**

Various terrains have different levels of reflectivity, causing the readings of the altitude to vary slightly. Additionally, transitioning between terrains with different densities of their foliage, such as a grass field to a forest, can cause the radar to change its readings. Depending on the density, the radar can vary between detecting the top and bottom of the foliage.

## Altitude Accuracy

**_I. Based on the user manual of the LR-D1 Pro, is the +/- 0.075m (\< 5m) the maximum error? Can better accuracy be achieved under 2-meter heights?_**

±0.075 m is the variation between readings in which the radar collects data and reports in steps of this size. For the maximum error, it depends on the flight scenario and conditions.

## LR-D1 Pro Altimetry for Seaplanes

**_I. What are the capabilities of the LR-D1 Pro being mounted on the landing gear of a manned aircraft for both water and land takeoffs and landings?_**

The LR-D1 Pro is, like any sensor, subject to error when used improperly or on rare occasions when circumstances are unfavorable. For example, all radar sensors are subject to multipath propagation, which can result in erroneous measurements in altitude. Therefore, any application that can be life-threatening should not be reliant on one sensor alone. The LR-D1 Pro is ultimately a reference altimeter. Please consider using multiple sensors and/or sensor fusion to provide redundancy in altitude measurements and to account for adverse circumstances.

Second, when operating in conditions that require precision, caution is advised, and it is recommended that users perform thorough in-flight testing to validate its performance prior to normal use. Although radar outperforms laser altimeters in measuring AGL altitude while flying over water, it is still subject to error in those circumstances.

Third, the LR-D1 Pro has not yet been FAA-approved and is therefore not adherent to 14 CFR § 135.160 requirements. Although the manufacturing facility adheres to ISO-9001 standards, Ainstein is not AS9100 compliant. The LR-D1 Pro is designed for use in UAS applications, not manned flight.

## Ground Test Procedure

A proper way to ground test could include attaching the radar to an extendable tripod, facing the ground, and raising it to the desired altitude.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/906881008fda0db4da4a21db16c02cb71b855b5e853edb6e3a09e715c5134acf-Screenshot_2026-01-26_at_6.30.42_PM.png",
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
        "https://files.readme.io/e774e609a48db12bc12cd08b6f3d53507966dc1e4df3aae3f06187ed2f41855a-Screenshot_2026-01-26_at_6.31.38_PM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]