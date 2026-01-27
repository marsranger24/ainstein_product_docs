---
title: Installation Guidelines
excerpt: >-
  The following instructions are critical to the proper operation of the US-D1
  device. Failure to install the unit according to the given instructions can
  result in malfunction of the device.
deprecated: false
hidden: false
metadata:
  robots: index
---
> 📘 **Warning!**  Follow the manufacturer's regulations when mounting, modifying, repairing, and maintaining equipment. The manufacturer assumes no responsibility for any accidents caused by incorrectly mounted or incorrectly maintained equipment. The manufacturer assumes no responsibility for the system being incorrectly applied, or the system being programmed in a manner that jeopardizes safety.

<br />

## 2.1. Mounting Angle

When mounting the device, the front face of the US-D1 beam must be perpendicular to  
the ground below the aircraft. There should not be any angle of inclination in any  
direction while the device is fastened to the aircraft

**Figure 1**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/10c561735680cb210265d48b8eaafbbb43aeb3ef595e49dba81ed93241670699-Screenshot_2026-01-22_at_1.57.34_AM.png",
        "",
        ""
      ],
      "align": "left",
      "border": true
    }
  ]
}
[/block]


<br />

<br />

<br />

<br />

<br />

<br />

<br />

## 2.2 Mounting to an Aircraft

The device should be secured to the aircraft, where it is not free to move in any direction.

## 2.3. Line of Sight Clearance

Keep the face of the radar clean, and do not cover it with any additional materials. Any  
coatings, coverings, and modifications to the radome can degrade the performance of  
the radar device.  
Additionally, keep any unexpected objects out of the radar’s FoV (Field of View).  
Obstructions to the US-D1’s field of view will cause a decrease in the performance of the  
radar. It is highly recommended that the US-D1 be mounted on the underside of the  
aircraft far away from the landing gear, other aircraft structures, or other equipment.

**Figure 2**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bf32ed12f2182f0d9e8d718750bc5e3e5d88368fa730244c73eac84eafd6ee1d-Screenshot_2026-01-21_at_11.56.14_PM.png",
        "",
        ""
      ],
      "align": "left",
      "border": true
    }
  ]
}
[/block]


<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

## 2.4. Integration Requirements

The US-D1 outputs altitude measurements and signal-to-noise ratio (SNR)  
measurements when operational. When integrating the US-D1 radar altimeter, it is  
necessary to use both altitude and SNR measurements to properly filter out erroneous  
altitude values

> 📘 **Caution!** Altitude measurements associated with a SNR value of 13dB or lower are considered erroneous.

The altitude measurements should not in any circumstances be used as true measurements independently of the corresponding SNR values.

A filtering algorithm should be used to estimate vehicle position, velocity and angular orientation based on rate gyroscopes, accelerometer, compass, GPS, airspeed and barometric pressure measurements in addition to the recorded US-D1 measurements. Sensor redundancy is heavily advised for the US-D1.