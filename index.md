---
layout: post
title: "Autonomous Building Inspection"
author: Nick Chodura, Derek Boase, Joshua Woods and Melissa Greeff
---
Welcome to the Autonomous Building Inspection project! This page covers the progress made on this project to date by members of [Robora Lab](https://roboralab.com/).

---
### <span style="color: #4568ff;">Background</span>


---
### <span style="color: #4568ff;">Evaluation of Flight Parameters in UAV-based 3D Reconstruction for Rooftop Infrastructure Assessment </span>[Winter 2025]
##### Accepted as a contributing paper at the 42nd International Symposium on Automation and Robotics in Construction (ISARC)

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
### <span style="color: #4568ff;">A Time and Place to Land: Online Learning-Based Distributed MPC for Multirotor Landing on Surface Vessel in Waves </span>[Summer 2024]
##### Accepted as a contributing paper at the 2025 International Conference on Unmanned Aircraft Systems (ICUAS). Check out the paper [here](https://arxiv.org/abs/2410.21674)!
We addressed two limitations of our prior solution in this work. The assumption that a spatial-temporal wave model was perfectly known is not reasonable for practical landing scenarios. In this work we learn the spatial-temporal local wave model from data as a Gaussian Process (GP). The mean and uncertainty quantification from the GP regression are incorporated into our previous distributed MPC framework to enable safer landings in uncertain wave conditions. Another limitation of our prior solution is that it was validated only in simulation. Due to the cost of surface vessels and lack of suitable geographic testing locations, many UAV-USV cooperative landing solutions are similarly bound to simulation. To address this limitation, we built a low-cost testbed platform mounted on an unmanned ground vehicle to mimic the spatial-temporal tilting motion of a USV in waves. Using a Bitcraze Crazyflie 2.1 UAV, and a ClearPath Robotics Husky mounted with our tilting platform, we performed substantial experimental validation of our proposed framework in harsh wave conditions. Our proposed framework achieved a 53% landing success rate improvement over an approach that neglects spatial-temporal tilt motion.

{% raw %}
<!-- Top Row: Image + Video Side by Side -->
<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px; margin-bottom: 30px; margin-top: 30px;">

  <!-- Figure 1 Image -->
  <figure style="flex: 1; min-width: 300px; text-align: center;">
    <img src="assets/f6.png" alt="Figure 1" style="width: 100%; max-width: 100%; border-radius: 8px;">
    <figcaption style="margin-top: 8px; font-style: italic; color: #555;">
      Tilt of the platform at landing in harsh wave conditions. Our proposed approach (blue) achieves a lower tilt at landing over the approach that neglects tilt (red).
    </figcaption>
  </figure>

  <!-- Embedded YouTube Video -->
  <figure style="flex: 1; min-width: 300px; text-align: center;">
    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
      <iframe src="https://www.youtube.com/embed/g4cCmE9Rgxs"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
              frameborder="0"
              allowfullscreen>
      </iframe>
    </div>
    <figcaption style="margin-top: 8px; font-style: italic; color: #555;">
      Accompanying video.
    </figcaption>
  </figure>

</div>

<!-- Second Row: 3 Figure 1 Images Side-by-Side -->
<div style="display: flex; flex-wrap: wrap; justify-content: space-between;">

<figure style="flex: 1; min-width: 250px; text-align: center;">
  <img src="assets/f5.png" alt="Figure 2" style="width: 100%; border-radius: 8px;">
  <figcaption style="margin-top: 8px; font-style: italic; color: #555;">
    Custom tilting platform for ground vehicles. The platform mimics the spatial-temporal tilting motion of a USV in waves.
  </figcaption>
</figure>

</div>
{% endraw %}

---
### <span style="color: #4568ff;">Distributed Model Predictive Control for Cooperative Multirotor Landing on Uncrewed Surface Vessel in Waves </span>[Winter 2024]
##### Accepted as a contributing paper at the 2024 International Conference on Unmanned Aircraft Systems (ICUAS). Check out the paper [here](https://ieeexplore.ieee.org/document/10557042)!
We perform safe autonomous landing in simulation using a distributed model predictive control (MPC) scheme. Our proposed architecture combines standard tracking MPCs for the multirotor and USV and augments them with additional artificial goal locations. These artificial goals enable the vehicles to coordinate without prior guidance. Each vehicle solves an individual optimization problem for both the artificial goal and an input that tracks it but only communicates the former to the other vehicle. To account for harsh waters our distributed MPC integrates a spatial-temporal wave model in the cost function encouraging the agents to converge to calmer waters. The wave model maps the location and time to the tilt of the USV. We show in simulation how our approach can simultaneously coordinate in real-time both a safe landing location and execute the landing task for a multirotor on a USV under wave conditions.

We consider three strategies **"Cooperative"**, **"Calm"**, and **"Ride the Wave"**. The "Cooperative" strategy does not include a tilt cost, the "Calm" strategy includes a long-term spatial tilt cost, and the "Ride the Wave" strategy includes a short-term spatial tilt cost.

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
