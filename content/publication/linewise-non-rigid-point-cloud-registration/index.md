---
title: Linewise Non-Rigid Point Cloud Registration
publication_types:
  - "2"
authors:
  - admin
  - Pere Ridao
  - Roland Siegwart
  - César Cadena
publication: Submitted to IEEE Robotics and Automation Letters
abstract: Robots are usually equipped with 3D range sensors such as laser line
  scanners (LLSs) or lidars. These sensors acquire a full 3D scan in a line by
  line manner while the robot is in motion. All the lines can be referred to a
  common coordinate frame using data from inertial sensors. However, errors from
  noisy inertial measurements and inaccuracies in the extrinsic parameters
  between the scanner and the robot frame are also projected onto the shared
  frame. This causes a deformation in the final scan containing all the lines,
  which is known as motion distortion. Rigid point cloud registration with
  methods like ICP is therefore not well suited for such distorted scans. In
  this paper we present a non-rigid registration method that finds the optimal
  rigid transformation to be applied to each line in the scan in order to match
  an existing model. We fully leverage the continuous and relatively smooth
  robot motion with respect to the scanning time to formulate our method
  reducing the computational complexity while improving accuracy. We use
  synthetic and real data to benchmark our method against a state-of-the-art
  non-rigid registration method. Finally, the source code for the algorithm is
  made publicly available [here](https://github.com/miguelcastillon).
draft: true
featured: true
projects:
  - non-rigid-point-cloud-registration
image:
  filename: featured.png
  focal_point: Bottom
  preview_only: false
date: 2022-05-11T15:43:05.875Z
---
