---
layout: post
title: "Autonomous Building Inspection"
author: Nick Chodura, Derek Boase, Joshua Woods and Melissa Greeff
---
Welcome to the autonomous building inspection project! This page covers the progress made on this project to date by members of [Robora Lab](https://roboralab.com/).

---
### <span style="color: #4568ff;">Background</span>


The inspection of rooftops plays a critical role in assessing the structural integrity and maintenance needs of buildings. Traditionally, this task has been carried out by inspectors physically accessing rooftops to identify defects in the building envelope and rooftop equipment. This manual approach is inherently time-consuming, especially for large-scale commercial and industrial structures, and presents significant challenges for visualizing structures.

Advancements in uncrewed aerial vehicle (UAV) technology and photogrammetry have opened new possibilities for building inspections. UAV's equipped with high-resolution cameras can capture images from locations inaccessible to inspectors, enabling comprehensive documentation of structures. These images can be processed using 3D reconstruction techniques to create digital models of the inspected structures. This not only facilitates better visualization of scale and defect locations, but also serves as a historical record for tracking structural changes over time.

This project investigates: (1) optimal practices for producing high-quality 3D reconstructions of rooftop infrastructure, (2) applications of these reconstructions in cold region climates, and (3) autonomous defect detection from the collected data.

---
### <span style="color: #4568ff;">Evaluation of Flight Parameters in UAV-based 3D Reconstruction for Rooftop Infrastructure Assessment </span>
##### Accepted as a contributing paper at the 42nd International Symposium on Automation and Robotics in Construction (ISARC). Check out the paper [here](https://arxiv.org/abs/2504.02084)

In prior rooftop inspection work using UAV photogrammetry, practitioners have relied on very high image overlap and long flight times to ensure model accuracy—constraints that limit operational efficiency in commercial assessments. Recognizing the need to balance flight duration, image capture volume, and reconstruction fidelity, this study systematically explores how ground sampling distance (GSD) and image overlap affect 3D model quality for complex rooftop infrastructure.

We conducted nine autonomous flights over a multi‐segment rooftop on Queen’s University’s Ellis Hall with a DJI Phantom 4 Pro V2, varying GSD (0.51–1.49 cm) and overlap (60–90%). Photogrammetry-based 3D reconstructions were generated in Reality Capture, and compared via cloud‑to‑cloud (C2C) metrics of precision, recall, and F‑score against ground‑truth point clouds from a UAV‑based LiDAR, validated by terrestrial laser scanning (TLS).

Our experiments show that a GSD of 0.75–1.26 cm combined with 85% overlap delivers the optimal trade‑off: it achieves the highest mean F‑score across five roof sections while reducing image counts (233 captures) and compute time (3 min 31 s). Flights at 90% OL yielded no further gains and sometimes lower quality, and lower overlaps (<80%) produced significant distortions. We also confirm that UAV‑based LiDAR provides an effective alternative for TLS ground truth, with an 85% F‑score at a 2 cm threshold in C2C comparisons of specific test areas.

These findings yield three practical guidelines for autonomous rooftop photogrammetry:

1. Use 0.75–1.26 cm GSD with 85% OL to maximize accuracy per image captured.
2. Avoid overlaps above 85%, which offer diminishing returns.
3. Manual flights are required around thin‑walled objects (e.g., fencing) and lower sections prone to occlusion and poorer lighting.

Together, these recommendations enable efficient, high‑fidelity UAV flight plans for rooftop infrastructure assessment.


<div style=\"display: flex; flex-wrap: wrap; justify-content: space-between; margin: 30px 0;\">
  <figure style=\"flex: 1; min-width: 250px; text-align: center; margin: 0 auto;\">
    <img src=\"assets/Picture1.png\" alt=\"Figure 1\" style=\"width: 100%; border-radius: 8px;\">
    <figcaption style=\"width: 100%; margin: 8px auto 0 auto; font-style: italic; color: #555;\">
      Photogrammetry-based 3D reconstructions of rooftop infrastructure. On the left, a GSD of 0.51 - 1.01 cm and an overlap of 85% was used. On the right, the same overlap was used with a larger GSD of 0.75 - 1.26 cm. This illustrates the significant change in model quality that can occur by varying these parameters. Thin-walled surfaces feature fewer occlusions, shown in the green box, and complex geometry was represented better, shown in the walkway in the yellow box.
    </figcaption>
  </figure>
</div>

<div style=\"display: flex; flex-wrap: wrap; justify-content: space-between;\">
  <figure style=\"flex: 1; min-width: 250px; text-align: center; margin: 0 auto;\">
    <img src=\"assets/Picture2.png\" alt=\"Figure 2\" style=\"width: 100%; border-radius: 8px;\">
    <figcaption style=\"width: 100%; margin: 8px auto 0 auto; font-style: italic; color: #555;\">
      Three models are shown, with flight plans of increasing overlap from top to bottom. RGB (left), precision (middle), and recall (right) scalar fields indicate the error between the models being tested and the ground-truth. The flight path using lower overlap in the top row produced large regions of high error (&gt;10 cm) and was unable to recreate simple building geometry. With higher overlap percentages, the error becomes primarily concentrated around regions of high detail, and the lower roof sections with poorer lighting and greater obstruction.
    </figcaption>
  </figure>
</div>

---

### <span style="color: #4568ff;">Cold Region Building Inspection using UAV-based Three-dimensional Reconstruction </span>
##### Submitted as a contributing paper to the ISPRS International Workshop on Unmanned Aerial Vehicles in Geomatic and Remote Sensing (UAV-g).
Building inspections in cold climates are essential to prevent structural damage caused by snow accumulation and identify thermal inefficiencies due to thermal bridging. Traditional inspection methods are costly, time-consuming, and hazardous. This research explores UAV-based inspection methods leveraging photogrammetry and infrared thermography for efficient, safe, and accurate assessment.

The study utilizes UAV-based photogrammetry to measure rooftop snow depth and infrared thermography for thermal reconstruction of building envelopes. UAV flights employed standardized parameters to capture RGB, thermal, and LiDAR data, processed using Reality Capture and CloudCompare software.

Key contributions and findings:
1. Developed a UAV-based method for accurately measuring rooftop snow depth with an average error under 1 cm, validated against LiDAR and manual measurements.
2. Proposed an RGB-thermal 3D reconstruction technique that avoids complex image alignment methods, achieving high geometric and radiometric accuracy, validated with radiometric control points and thermal imagery comparison.

The results confirm that UAV-based inspections provide highly accurate, cost-effective alternatives to traditional methods. Challenges remain in managing temperature variability and reflections from low-emissivity surfaces. Future work includes further testing across varied snow conditions and improving temperature accuracy in dynamic environmental conditions.

{% raw %}
<div style="display: flex; justify-content: center; margin: 30px 0;">
  <figure style="text-align: center; width: 100%; margin: 0 auto;">
    <img src="assets/ellis_snow.svg" alt="Figure 1" style="width: 100%; border-radius: 8px;">
    <figcaption style="width: 100%; margin: 8px auto 0 auto; font-style: italic; color: #555;">
      RGB (left), photogrammetry snow depth map (middle), and LiDAR snow depth map (right). 
    </figcaption>
  </figure>
</div>

<div style="display: flex; flex-wrap: wrap; justify-content: space-between;">
<figure style="flex: 1; min-width: 250px; text-align: center;">
  <img src="assets/thermal_ellis_v3.svg" alt="Figure 2" style="width: 100%; border-radius: 8px;">
  <figcaption style="width: 80%; margin: 8px auto 0 auto; font-style: italic; color: #555;">
    Joint RGB-thermal 3D reconstruction. After images from both datasets are aligned separately, the resulting sparse clouds of tie points are merged. The RGB images are used for meshing, due to their higher spatial resolution and image contrast. The texture is then projected onto the mesh using the thermal images, and a linear transformation can be applied to yield the corrected temperature values.
  </figcaption>
</figure>
</div>
{% endraw %}

