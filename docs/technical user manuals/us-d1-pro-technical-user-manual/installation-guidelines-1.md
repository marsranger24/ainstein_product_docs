---
title: Installation Guidelines
deprecated: false
hidden: false
metadata:
  robots: index
---
## 2. Installation Guidelines

> 📘 **Warning!** Follow the manufacturer's regulations when mounting, modifying, repairing, and maintaining equipment. The manufacturer assumes no responsibility for any accidents caused by incorrectly mounted or incorrectly maintained equipment. The manufacturer assumes no responsibility for the system being incorrectly applied, or the system being programmed in a manner that jeopardizes safety.

The following instructions are critical to the proper operation of the US-D1 Pro device. Failure to install the unit according to the given instructions can result in the malfunction of  
the device.

## 2.1. Mounting Angle and Position

When mounting the device, the front face of the US-D1 Pro beam must be **perpendicular** to the ground below the aircraft. There should not be any angle of inclination in any direction while the device is fastened to the aircraft. 

In addition to the mounting angle, it is recommended that the angle between the radar beam and other obstacles (e.g. landing gear) is greater than 50° and the material is low permittivity type, to achieve the optimal performance.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6ad5af9f2e2e0cc999b10f1871e303251e0fab016aa3ae0649f6ab91b541bfc2-Screenshot_2026-01-27_at_3.20.54_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 2.1**"
    }
  ]
}
[/block]


## 2.2 Mounting to an Aircraft

The device should be secured to the aircraft, where it is not free to move in any direction.

## 2.3. Line of Sight Clearance

Keep the face of the radar clean, and do not cover it with any additional materials. Any coatings, coverings, and modifications to the radome can degrade the performance of the radar device.

Additionally, keep any unexpected objects out of the radar’s FoV (Field of View). Obstructions to the US-D1 Pro’s field of view will cause a decrease in the performance of the radar. It is highly recommended that the angle between the radar beam and expected objects (e.g. landing gear) is greater than 50° and the material is a low permittivity type, to achieve the optimal performance.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c770bd7d338adeba06412008f72cf9686478ce10362467b97690f04540d7c3b-Screenshot_2026-01-27_at_3.22.54_AM.png",
        "",
        ""
      ],
      "align": "center",
      "caption": "**Figure 2.2**"
    }
  ]
}
[/block]


## 2.4. Integration Requirements

The US-D1 Pro outputs altitude (AGL) measurements, vertical speed measurement, signal-to-noise ratio (SNR), Measurement Confidence when operational. When integrating the US-D1 Pro radar altimeter, it is recommended to use Measurement Confidence to properly filter out erroneous altitude values.

A filtering algorithm should be used to estimate vehicle position, velocity and angular orientation based on rate gyroscopes, accelerometer, compass, GPS, airspeed and barometric pressure measurements in addition to the recorded US-D1 Pro measurements. Sensor redundancy is heavily advised for the US-D1 Pro.