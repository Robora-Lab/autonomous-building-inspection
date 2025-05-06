---
layout: post
title: "Autonomous Building Inspection"
author: Nick Chodura, Derek Boase, Joshua Woods and Melissa Greeff
---
Welcome to the Autonomous Building Inspection project! This page covers the progress made on this project to date by members of [Robora Lab](https://roboralab.com/).

---
### <span style="color: #4568ff;">Background</span>


---
### <span style="color: #4568ff;">Evaluation of Flight Parameters in UAV-based 3D Reconstruction for Rooftop Infrastructure Assessment </span>
##### Accepted as a contributing paper at the 42nd International Symposium on Automation and Robotics in Construction (ISARC). Check out the paper [here](https://arxiv.org/abs/2504.02084)

In prior rooftop inspection work using UAV photogrammetry, practitioners have relied on very high image overlap and long flight times to ensure model accuracy—constraints that limit operational efficiency in commercial assessments. Recognizing the need to balance flight duration, image capture volume, and reconstruction fidelity, this study systematically explores how ground sampling distance (GSD) and image overlap (OL) affect 3D model quality for complex rooftop infrastructure.

We conducted nine autonomous flights over a multi‐segment rooftop on Queen’s University’s Ellis Hall with a DJI Phantom 4 Pro V2, varying GSD (0.51–1.49 cm) and OL (60–90%). Photogrammetric reconstructions were generated in Reality Capture, and compared via cloud‑to‑cloud (C2C) metrics—precision, recall, and F‑score—against ground‑truth point clouds from a UAV‑based LiDAR (Zenmuse L2) validated by terrestrial laser scanning (TLS).

Our experiments show that a GSD of 0.75–1.26 cm combined with 85% overlap delivers the optimal trade‑off: it achieves the highest mean F‑score across five roof sections while reducing image counts (233 captures) and compute time (3 min 31 s). Flights at 90% OL yielded no further gains and sometimes lower quality, and lower overlaps (<80%) produced significant distortions. We also confirm that UAV‑LiDAR provides an effective surrogate for TLS ground truth, with an 85% F‑score at a 2 cm threshold in C2C comparisons.

These findings yield three practical guidelines for autonomous rooftop photogrammetry:

1. Use 0.75–1.26 cm GSD with 85% OL to maximize accuracy per image captured.
2. Avoid overlaps above 85%, which offer diminishing returns.
3. Supplement flights with targeted manual captures around thin‑walled details (e.g., fencing) and lower sections prone to occlusion.

Together, these recommendations enable efficient, high‑fidelity UAV flight plans for rooftop infrastructure assessment.

{% raw %}
<div style="display: flex; justify-content: center; margin: 30px 0;">
  <figure style="text-align: center; width: 60%; margin: 0 auto;">
    <img src="assets/f7.png" alt="Figure 1" style="width: 100%; border-radius: 8px;">
    <figcaption style="width: 100%; margin: 8px auto 0 auto; font-style: italic; color: #555;">
      Two multirotor paths using two different MPC strategies. On the left the "Track Position" strategy guides the multirotor to the center of the platform where it lands with a significant rotational error. On the right the "Combination" strategy reduces the rotational error but introduces positional error as the multirotor translates to match the rotation of the platform.
    </figcaption>
  </figure>
</div>

<div style="display: flex; flex-wrap: wrap; justify-content: space-between;">
<figure style="flex: 1; min-width: 250px; text-align: center;">
  <img src="assets/f8.png" alt="Figure 2" style="width: 100%; border-radius: 8px;">
  <figcaption style="width: 80%; margin: 8px auto 0 auto; font-style: italic; color: #555;">
    Experimental landing success rates of the three MPC strategies. "Track Position" (left), "Match Rotation" (center), "Combination" (right).
  </figcaption>
</figure>
</div>
{% endraw %}

---

### <span style="color: #4568ff;">Cold Region Building Inspection using UAV-based Three-dimensional Reconstruction </span>
##### Submitted as a contributing paper to the ISPRS International Workshop on Unmanned Aerial Vehicles in Geomatic and Remote Sensing (UAV-g).
Building inspections in cold climates are essential to prevent structural damage caused by snow accumulation and identify thermal inefficiencies due to thermal bridging. Traditional inspection methods are costly, time-consuming, and hazardous. This research explores UAV-based inspection methods leveraging photogrammetry and infrared thermography for efficient, safe, and accurate assessment.

The study utilizes UAV-based photogrammetry to measure rooftop snow depth and infrared thermography for thermal reconstruction of building envelopes. UAV flights employed standardized parameters to capture RGB, thermal, and LiDAR data, processed using Reality Capture and CloudCompare software.

Key contributions and findings:

Developed a UAV-based method for accurately measuring rooftop snow depth with an average error under 1 cm, validated against LiDAR and manual measurements.

Proposed an RGB-thermal 3D reconstruction technique that avoids complex image alignment methods, achieving high geometric and radiometric accuracy, validated with radiometric control points and thermal imagery comparison.

The results confirm that UAV-based inspections provide highly accurate, cost-effective alternatives to traditional methods. Challenges remain in managing temperature variability and reflections from low-emissivity surfaces. Future work includes further testing across varied snow conditions and improving temperature accuracy in dynamic environmental conditions.


{% raw %}
<!-- Top Row: Image + Video Side by Side -->
<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px; margin-bottom: 5px; margin-top: 30px;">

  <!-- Figure 1 Image -->
  <figure style="flex: 1; min-width: 300px; text-align: center;">
    <img src="assets/f1_1.png" alt="Figure 1" style="width: 100%; max-width: 100%; border-radius: 8px;">
    <figcaption style="margin-top: 8px; font-style: italic; color: #555;">
      Block diagram of our proposed distributed MPC.
    </figcaption>
  </figure>

  <!-- Embedded YouTube Video -->
  <figure style="flex: 1; min-width: 300px; text-align: center;">
    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
      <iframe src="https://www.youtube.com/embed/nBaHKCH9xOY"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
              frameborder="0"
              allowfullscreen>
      </iframe>
    </div>
    <figcaption style="margin-top: 8px; font-style: italic; color: #555;">
      Recording of ICUAS 2024 presentation materials.
    </figcaption>
  </figure>

</div>

<!-- Second Row: 3 Figure 1 Images Side-by-Side -->
<div style="display: flex; flex-wrap: wrap; justify-content: space-between;">

  <figure style="flex: 1; min-width: 250px; text-align: center;">
    <img src="assets/f2_1.png" alt="Image A" style="width: 100%; border-radius: 8px;">
    <figcaption style="margin-top: 8px; font-style: italic; color: #555;">
      "Cooperative" Strategy.
    </figcaption>
  </figure>

  <figure style="flex: 1; min-width: 250px; text-align: center;">
    <img src="assets/f3.png" alt="Image B" style="width: 100%; border-radius: 8px;">
    <figcaption style="margin-top: 8px; font-style: italic; color: #555;">
      "Calm" Strategy.
    </figcaption>
  </figure>

  <figure style="flex: 1; min-width: 250px; text-align: center;">
    <img src="assets/f4_1.png" alt="Image C" style="width: 100%; border-radius: 8px;">
    <figcaption style="margin-top: 8px; font-style: italic; color: #555;">
      "Ride the Wave" Strategy.
    </figcaption>
  </figure>

</div>
{% endraw %}

---
### References
[1]	Y. Wang, W. Liu, J. Liu, and C. Sun, “Cooperative USV–UAV marine search and rescue with visual navigation and reinforcement learning-based control,” ISA Trans., vol. 137, pp. 222–235, 2023.

[2]	J. Wu, R. Li, J. Li, M. Zou, and Z. Huang, “Cooperative unmanned surface vehicles and unmanned aerial vehicles platform as a tool for coastal monitoring activities,” Ocean Coast. Manag., vol. 232, p. 106421, 2023.

[3]	A. Vasilijevic et al., “Heterogeneous robotic system for underwater oil spill survey,” in OCEANS 2015 - Genova, pp. 1–7, 2015.

[4]	T. I. Fossen, Handbook of marine craft hydrodynamics and motion control. John Wiley & Sons, 2011.

[5]	K. Xia, M. Shin, W. Chung, M. Kim, S. Lee, and H. Son, “Landing a quadrotor UAV on a moving platform with sway motion using robust control,” Control Eng. Pract., vol. 128, p. 105288, 2022.
