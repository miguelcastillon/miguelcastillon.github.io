---
title: Inertial navigation framework for multimodal underwater Graph SLAM
publication_types:
  - "1"
authors:
  - Pau Vial
  - admin
  - Narcís Palomeras
  - Marc Carreras
doi: 10.1109/OCEANSLimerick52467.2023.10244303
publication: "*OCEANS 2023, Limerick*"
abstract: Robot localization is a fundamental task in achieving true autonomy
  for Autonomous Underwater Vehicles (AUV). If inertial measurements from an
  Inertial Measurement Unit (IMU) or a Doppler Velocity Log (DVL) want to be
  fused with some perception system, such us a multibeam sonar or several
  acoustic beacons; a full Simultaneous Localization And Mapping (SLAM) problem
  must be solved. In contrast to filters, in a full SLAM problem the whole robot
  trajectory is estimated and loop closure events can be detected and closed
  along it. Common Inertial Navigation Systems (INS), based on filters, only
  maintain the estimation of the current robot pose. Therefore, these systems
  cannot be directly used in a full SLAM problem. In this paper we present a
  graph solution to integrate all inertial measurements in a factor graph that
  can be extended to different perception modalities and it is solved by
  applying Smoothing and Mapping (SAM) [1]. The Preintegrated IMU factor,
  proposed by [2], is combined with priors for other inertial measurements that
  have been specially designed. This framework is tested on real data from sea
  experiments, showing how our proposal performance is similar to the estimation
  provided by high grade commercial INS products based on filters. However, our
  system has the advantage of allowing for fusion with exteroceptive sensors in
  SLAM.
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
date: 2023-11-29T14:44:53.260Z
---
