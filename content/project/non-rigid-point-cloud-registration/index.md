---
title: Non-rigid point cloud registration
date: 2022-05-10T22:04:16.200Z
summary: During my research stay at [ASL](https://asl.ethz.ch/) (ETH Zurich) I
  developed a non-rigid point cloud registration method based on motion
  coherence theory.
draft: true
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
In September 2021 I moved to Zurich for a 6-month research stay at the [Autonomous Systems Lab](https://asl.ethz.ch/) (ETH) under the supervision of [César Cadena](http://n.ethz.ch/~cesarc/).
My main goal during this time was to investigate how to process point cloud data from our [underwater laser scanner](/project/underwater-3d-scanner/) so that they can be later used in downstream applications.

## Motion distortion

When we mounted our [underwater laser scanner](/project/underwater-3d-scanner/) onto AUV Girona1000 and acquired point clouds of the pipe structure shown above, we realized that some scans presented noticeable distortions:

{{< figure src="projects/non-rigid-point-cloud-registration/scans_real.png" caption="Three different examples of real distorted scans
(before registration)." numbered="false" width="500">}}

Laser line scanners acquire a full 3D scan in a line-by-line manner while the robot is in motion. 
All the lines can be referred to a common coordinate frame using data from inertial sensors. 
However, errors from noisy inertial measurements and inaccuracies in the extrinsic parameters between the scanner and the robot frame are also projected onto the shared frame, distorting the scans as shown above.

## Point cloud registration

[Point cloud registration](https://en.wikipedia.org/wiki/Point-set_registration) refers to the process of finding a spatial transformation that aligns a point cloud to another.

[ICP](https://en.wikipedia.org/wiki/Iterative_closest_point)

## Our method: Linewise non-rigid point cloud registration

[Coherent Point Drift](https://en.wikipedia.org/wiki/Point-set_registration#Coherent_point_drift)

We summarized our contribution in this video:

<div align="center">
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/tp0ob9yHagQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>