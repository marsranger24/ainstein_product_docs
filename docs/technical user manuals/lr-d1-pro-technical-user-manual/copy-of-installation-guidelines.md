---
title: Installation Guidelines
deprecated: false
hidden: false
metadata:
  robots: index
---
## 2.1. Mounting Angle

When mounting the device, the front face of the LR-D1 Pro must be perpendicular to  
the ground below the aircraft. There should not be any angle of inclination in any  
direction while the device is fastened to the aircraft.

<br />

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7088cfebd75cc180c253b6b8e2a13a20d9d2d719fa38343cf5993ab0707c53ac-Screenshot_2026-01-22_at_1.57.34_AM.png",
        "",
        "**Figure 1: Mounting Angle of the LR-D1 Pro**"
      ],
      "align": "center",
      "sizing": "400px",
      "border": true,
      "caption": "Figure 1: Mounting Angle of the LR-D1 Pro"
    }
  ]
}
[/block]


## 2.2 Mounting to an Aircraft

The device should be secured to the aircraft, where it is not free to move in any  
direction.

## 2.3. Line of Sight Clearance

Keep the face of the radar unobstructed and do not cover it with any additional  
materials. Any coatings, coverings, and modifications to the radome can degrade the  
performance of the radar device.

Additionally, keep any unexpected objects out of the radar’s FoV (Field of View).  
Obstructions to the LR-D1 Pro’s field of view will cause a decrease in the performance  
of the radar. It is highly recommended that the LR-D1 Pro be mounted on the underside  
of the aircraft far away from the landing gear, other aircraft structures, or other  
equipment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3c612ab24e9b0e290fed4345137f0b14c8692423020d2267de6c819533d92e80-Screenshot_2026-01-21_at_11.56.14_PM.png",
        "",
        "Figure 2: Line of Sight Clearance of the LR-D1 Pro"
      ],
      "align": "center",
      "caption": "Figure 2: Line of Sight Clearance of the LR-D1 Pro"
    }
  ]
}
[/block]


## 2.4. Integration Requirements

The LR-D1 Pro outputs altitude measurements and signal-to-noise ratio (SNR)  
measurements when operational. When integrating the LR-D1 Pro radar altimeter, it is  
recommended to use SNR measurements in conjunction with malfunction alerts (see  
Appendix 1) to properly filter out erroneous altitude values.

> 📘 **Caution!** Altitude measurements associated with an **SNR value of 13 dB or lower** are considered **erroneous**.

A fusion algorithm should be used to estimate vehicle position, velocity, and  
angular orientation based on rate gyroscopes, accelerometer, compass, GPS, airspeed,  
and barometric pressure measurements in addition to the recorded LR-D1 Pro  
measurements. Sensor redundancy is strongly advised for use of the LR-D1 Pro in  
mission-critical application