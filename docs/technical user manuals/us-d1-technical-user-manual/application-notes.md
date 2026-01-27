---
title: Application Notes
deprecated: false
hidden: false
metadata:
  robots: index
---
## 11. US-D1 Application Notes

Table 10 lists the application notes that will be addressed in future revisions.

**Table 10: US-D1 Application Notes**

[block:parameters]
{
  "data": {
    "h-0": "Issue ID",
    "h-1": "Description",
    "h-2": "Notes",
    "0-0": "1",
    "0-1": "If US-D1 is used outside of its Maximum  Operational Altitude (Table 1), inconsistent,  small readings of ~0.51m will be output,   because 0.51m is the edge of the US-D1’s blind zone. (See Figure 26 below).",
    "0-2": "For full confidence, only consider US-D1’s data when used within its operating range",
    "1-0": "2",
    "1-1": "Altitude data from US-D1 may have various step sizes, since a post-processing algorithm is implemented after radar processing, e.g. averaging, filtering.",
    "1-2": "No action needed",
    "2-0": "3",
    "2-1": "Altitude data from US-D1 may give  \nunexpected or incorrect measurements under operation in an indoor environment. Multipath reflections of the sensor’s radio waves are complicated in enclosed environments and may introduce errors in the radar’s processing.",
    "2-2": "DO NOT rely on US-D1 in an indoor, tightly enclosed   environment",
    "3-0": "4",
    "3-1": "When the US-D1 is operated at altitudes of  ~1m, there may be rare unstable readings, potentially due to multipath reflections of reflective surroundings or inaccuracies due to nearness to the radar’s blind zone.",
    "3-2": "",
    "4-0": "5",
    "4-1": "When transitioning from normal detection to out-of-range detection, the US-D1 will toggle between outputting correct measurements at the highest altitude of the operating range and reporting ~0.51m when out-of-range, instead of smoothly transitioning to out-of-range behavior.",
    "4-2": "",
    "5-0": "6",
    "5-1": "When the US-D1 is close to the blind zone (\\<1m) and a highly reflective object is placed in between the US-D1 and the ground and then is removed, the US-D1 output may get stuck outputting erroneous values until another object enters the FOV.",
    "5-2": "",
    "6-0": "7",
    "6-1": "SNR may not be perfectly representative of the accuracy of the altitude measurement near the minimum operating range, because multipath reflections can have high SNR when operating close to the blind zone.",
    "6-2": ""
  },
  "cols": 3,
  "rows": 7,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

**Figure 26: US-D1 Altitude Drop-off Example**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a16dafdea6ea615261f3323f39e9425341ebab9d702a02edc45305d7584be242-Screenshot_2026-01-27_at_3.02.56_AM.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]