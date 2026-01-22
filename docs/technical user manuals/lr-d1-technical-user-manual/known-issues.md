---
title: Known Issues
deprecated: false
hidden: true
metadata:
  robots: index
---
## 10. LR-D1 Known Issues

LR-D1 is a product still in development. Table 4 lists the known issues that will be  
addressed in later revisions.

**Table 4: LR-D1 Known Issues**

<br />

[block:parameters]
{
  "data": {
    "h-0": "Issue ID",
    "h-1": "Description",
    "h-2": "Notes",
    "0-0": "1",
    "0-1": "If the LR-D1 is mounted at the position of \\<  1.4m, it would report ‘Unhealthy’ in the Out of  Range Indication Byte or 1.4 m of range reading",
    "0-2": "- Ignore all radar  \n  detection readings if  \n  Out of Range  \n  Indication reports  \n  Unhealthy  \n- DO NOT consider  \n  altitude data while on  \n  the ground in this case  \n- If the altitude is too  \n  close, it means the  \n  radar reported altitude  \n  health is close to the  \n  surface or target.  \n  Please consider it as an ‘Invalid’ report.",
    "1-0": "2",
    "1-1": "Altitude data from radar may have unexpected or incorrect readings if the application scenario is indoors. The reason is the multipath reflection of radar is complicated indoors, it may give unexpected or incorrect readings under this circumstance.",
    "1-2": "- DO NOT apply radar in any indoor application scenario",
    "2-0": "3",
    "2-1": "Altitude data from radar may have unexpected or incorrect readings if aircraft pitch and/or roll are beyond the radar’s detection angle (Azimuth 43°, Elevation 30°). The ideal case is keeping the radar perpendicular to the ground.",
    "2-2": "- Add a gimbal with radar mounting  \n- DO NOT consider any altitude data as valid if the aircraft’s pitch and/or roll are beyond the radar’s detection angle.",
    "3-0": "4",
    "3-1": "Voltage alert is monitoring multiple node voltage on the radar’s hardware, some of their thresholds might be set too stringent and trigger alerts frequently in some scenarios, we are evaluating to extend the acceptable thresholds to resolve it",
    "3-2": "- Check the input  \n  voltage \n- Cool down the device  \n  and improve the heat  \n  dissipation  \n- Notify Ainstein if this  \n  alert still reports  \n  frequently after trying  \n  out above solutions",
    "4-0": "5",
    "4-1": "Overflowed Reading",
    "4-2": "- The altitudes for the two spots in the figure below are:  \n  a) 655.35 + 0.43 = **655.78 m**  \n  b) 655.35 + 143.89 = **799.24 m**  \n- It is user’s decision to discard or accept the overflowed reading"
  },
  "cols": 3,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/502c7973c2be191aaf27308380c68b011081325c7dc74bd03c16a01b725ac99a-Screenshot_2026-01-22_at_1.12.43_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]