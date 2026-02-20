---
title: Technical Specifications
deprecated: false
hidden: false
metadata:
  robots: index
---
## 4. LR-D1 Pro Technical Specifications:

**Table 1: Specifications of the LR-D1 Pro**

[block:parameters]
{
  "data": {
    "h-0": "Measurement",
    "h-1": "Sepcs",
    "0-0": "Frequency Band",
    "0-1": "24-24.25 GHz  \n60-64 GHz",
    "1-0": "Bandwidth",
    "1-1": "250 MHz  \n4 GHz",
    "2-0": "Power Consumption",
    "2-1": "\\< 14 W",
    "3-0": "Operating Voltage",
    "3-1": "10 ~ 32 V",
    "4-0": "Altitude Range",
    "4-1": "0.3m~500m（1）",
    "5-0": "Altitude Precision",
    "5-1": "± 0.364m (>5m)（2）  \n± 0.075m (\\<5m)（2)",
    "6-0": "Altitude Step Size",
    "6-1": "± 0.075m (>5m)  \n± 0.015m (\\<5m)",
    "7-0": "Update Rate",
    "7-1": "15 ms (66 Hz)",
    "8-0": "Detection Angle Range",
    "8-1": "Azimuth 43°， Elevation 30°（3）",
    "9-0": "Maximum Velocity",
    "9-1": "± 30 m/s in elevation",
    "10-0": "Temp. Range",
    "10-1": "\\-40℃~ +60℃",
    "11-0": "Dimensions",
    "11-1": "134mm x 134mm x 37.3mm (mounting bracket is  NOT included)",
    "12-0": "Weight",
    "12-1": "685 g",
    "13-0": "IP Rating",
    "13-1": "Built to the requirements of IP67（4)",
    "14-0": "Vibration Rating",
    "14-1": "IEC 60068-2-6.1995 Sinusoidal vibration 15g XYZ  \nthree axis",
    "15-0": "Shock Rating",
    "15-1": "IEC 68-2-27:1987 half sine shock 100g XYZ  \nthree axis",
    "16-0": "ESD Rating",
    "16-1": "IEC 61000-4-2:2008 8K/15K contact/air Class B  \ncriterion",
    "17-0": "Start Time",
    "17-1": "2 s",
    "18-0": "Maximum Ambient Pressure Altitudes",
    "18-1": "10,000 m"
  },
  "cols": 2,
  "rows": 19,
  "align": [
    "left",
    "left"
  ]
}
[/block]


<br />

**Note:**

1. Radar data may vary over different terrains when the radar is out of its detection range.  
   It is recommended to mount the LR-D1 Pro at a minimum height of 0.3m. 

We do not recommend using LR-D1 Pro at altitudes lower than 0.3m or greater than  
500m. When the actual altitude is greater than 500m over terrain that provides specular  
reflection, such as concrete, the radar can operate up to 600m. The LR-D1 Pro will report  
SNR = 0 and Altitude = 0m to indicate if there is no target detected; Therefore, when the  
SNR = 0, the detection can be considered invalid for that data frame.

2. Range detection might be limited by the terrain composition below, the pitch and roll of aircraft, and operational requirements. The range precision indicates the lab tested/calibration results in the standard case. 

LR-D1 Pro altitude data output step size is smaller than the radar’s precision because of  
the post-processing of the raw detection data.

3. Based on mm-wave radar specs, a large angle of pitch and roll can cause errors in  
   detection. Larger angles of pitch and roll will result in greater errors in LR-D1 Pro  
   output.
4. The IP rating only includes the radar itself. This rating does not cover cabling interfaces  
   or other accessories.  
   Proprietary information