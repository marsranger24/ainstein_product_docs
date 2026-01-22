---
title: Minimum and Maximum Operating Altitude
deprecated: false
hidden: true
metadata:
  robots: index
---
## 2.1. Mounting Angle

When mounting the device, the radio wave emitted from the LR-D1 must be  
perpendicular to the ground below the aircraft. There should not be any angle of  
inclination in any direction while the device is fastened to the aircraft.

<br />

`**Figure 1**`

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a8c71509d2ff632604968b76ee3696198dc47ed982126593cc1fb0344a0a0c2-Screenshot_2026-01-21_at_11.51.28_PM.png",
        "",
        ""
      ],
      "align": "left"
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

_Proprietary information_

## 2.2 Mounting to an Aircraft

The device should be secured to the aircraft, where it is not free to move in any  
direction.

## 2.3. Line of Sight Clearance

Keep the face of the radar clean, and do not cover it with any additional materials. Any  
coatings, coverings, and modifications to the radome can degrade the performance of  
the radar device.

Additionally, keep any unexpected objects out of the radar’s FoV (Field of View).  
Obstructions to the LR-D1’s field of view will cause a decrease in the performance of the  
radar. It is highly recommended that the LR-D1 be mounted on the underside of the  
aircraft far away from the landing gear, other aircraft structures, or other equipment.

**Figure 2**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d22b18edebf25c5d3650aa33a03762d6475e63145a393176ba8ab9e1cc0f81fb-Screenshot_2026-01-21_at_11.56.14_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


<br />

<br />

## 2.4. Integration Requirements

The LR-D1 outputs altitude measurements and signal-to-noise ratio (SNR)  
measurements when operational. When integrating the LR-D1 radar altimeter, it is  
Proprietary information  
Page 8  
1421 Research Park Dr  
Lawrence, KS 66049  
necessary to use SNR measurements and Out of Range Behavior Indication in  
conjunction with malfunction alerts (see appendix 1) to properly filter out erroneous  
altitude values.  
A filtering algorithm should be used to estimate vehicle position, velocity, and  
angular orientation based on rate gyroscopes, accelerometer, compass, GPS, airspeed,  
and barometric pressure measurements in addition to the recorded LR-D1  
measurements. Sensor redundancy is heavily advised for the LR-D1.  
Proprietary information