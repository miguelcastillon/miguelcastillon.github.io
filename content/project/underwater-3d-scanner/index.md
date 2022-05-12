---
title: Underwater 3D scanner
date: 2022-05-10T14:30:03.242Z
summary: One of my main contributions during the thesis has been the development
  of an underwater 3D laser scanner designed for autonomous mapping and
  manipulation.
draft: false
featured: false
authors: []
image:
  filename: featured.jpg
  focal_point: Smart
  preview_only: false
  caption: Our prototype 3D laser scanner mounted on the AUV
    [Girona1000](https://iquarobotics.com/girona-500-auv) during an inspection
    task at the water tank in the [CIRS lab](https://cirs.udg.edu). The
    inspected structure is a mock-up of an underwater industrial site.
---
## Context: underwater imaging

Visual perception in underwater scenarios is **hard**.
In order to understand how and why, let's have a look at this 360º video recorded by some of my colleagues:

<div align="center">
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/ptkhwTPFvjk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

Even though the visibility conditions on this video were *almost optimal*, we can already identify two main challenges:
1. The *floating particles* in the water blur the image and make it lose the sharpness of its texture, reducing the number of distinctive features.
1. The *high attenuation rate* of water means that light loses most of its power at distances in the order of meters or tens of meters, depending on its wavelength:
{{< figure src="water_light_absorption.png" caption="Electromagnetic absorption by water ([source](https://en.wikipedia.org/wiki/Electromagnetic_absorption_by_water#/media/File:Absorption_spectrum_of_liquid_water.png))." numbered="false" width="500">}}

A robust solution against these factors is using [sonar](https://en.wikipedia.org/wiki/Sonar).
Sonars are range sensors that use ultrasonic waves to acquire geometrical information about their surroundings.
Ultrasonic waves are mechanical waves and can therefore propagate further and are not affected by [water turbidity](https://en.wikipedia.org/wiki/Turbidity) and varying lighting conditions.
However, they typically produce much noisier results and their resolution is in the order of tens of centimeters.

{{< figure src="sonar_bike.png" caption="Bike measured using a sonar ([source](http://www.jwfishers.com/multimedia.html))." numbered="false" width="500">}}

## Underwater 3D laser scanners

The low resolution and accuracy of sonars make them unsuitable for many tasks performed by autonomous underwater vehicles (AUVs), such as manipulation and high-resolution inspection.
As an alternative, 3D laser scanners (or [lidars](https://en.wikipedia.org/wiki/Lidar)) are used instead, which can achieve a typical accuracy in the order of millimeters.
If we now revisit the two challenging factors mentioned above, we see that laser scanners:
1. can provide dense point clouds even in featureless environments, since they actively project light onto the scene, and
1. especially for manipulation tasks, a maximum scanning range of a few meters is not a major problem, since it is longer than the maximum reach of a typical robotic arm.

3D laser scanners typically steer a laser plane *using a mirror* across a field of view (FoV) of around 40ºx40º.
This characteristic makes them particularly useful for manipulation tasks, since they can view a relatively broad FoV without the need of moving the robot.
However, the projected laser line is deformed into a curve at the edges of the FoV due to [refraction](https://en.wikipedia.org/wiki/Refraction):
{{< figure src="palomer_laser_curve.png" caption="The straight laser line projected by the scanner transforms into a curve when entering water due to refraction ([source](https://link.springer.com/chapter/10.1007/978-3-319-55372-6_4))." numbered="false" width="500">}}


## Our prototype

Laser scanners seem suitable for manipulation tasks at short ranges.
However, the effect of refraction mentioned above may decrease their accuracy or complicate their calibration.
At this point, we asked ourselves:
is there any way we could project straight lines into the water?
Which scanning pattern could achieve that?
And how could we realize it?
After much thought, we came up with [this model](/publication/underwater-3d-scanner-model-using-a-biaxial-mems-mirror/):

{{< figure src="scanning_scheme.png" caption="Scheme of our underwater 3D scanner." numbered="false" width="500">}}

This is a ray-tracing model able to generate a pattern of optimally-curved points based on the values of different parameters, such as the refraction index of water.
In order to be able to steer the laser both vertically and horizontally, we used a 2-axis mirror.
The practical realization of the model was published in [this paper](/publication/underwater-3d-scanner-to-counteract-refraction-calibration-and-experimental-results/).

{{< figure src="scanner_scheme.jpg" caption="Prototype of our underwater 3D scanner." numbered="false" width="500">}}

The main conclusions of this work were:
- Our prototype can achieve millimeter accuracy, in the order of other state-of-the-art underwater laser scanners.
- Our approach allows for higher flexibility in the scanning pattern, potentially opening future lines of research.
- Its calibration routine based on simple polynomial fitting is much simpler than other scanners.
- It can currently match state-of-the-art scanning speed (between 50 and 100 scanned lines per second). 
However, this speed could be noticeably increased by implementing a more efficient controller that dealt better with the highly-resonant dynamic behaviour of the mirror.

### Integration into the AUV

Together with Roger Pi, we integrated the scanner into the Girona1000 and calibrated its extrinsic parameters with respect to the robot, enabling dynamic scanning:

<div align="center">
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/OytUI9x3cWw?start=124" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### Sea experiments

Once the scanner was properly integrated into the AUV, we made a mapping inspection of the rocky seafloor:

{{< figure src="sea_experiment.jpg" caption="Sea experiment with the laser scanner mounted on AUV Girona1000 at the harbour of St. Feliu de Guíxols (Spain)." numbered="false" width="400">}}

An example of the acquired 3D point clouds can be watched in this video:

<div align="center">
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/Zc_appJUckI?start=50" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

## Acknowledgments

Many big thanks to Lluís Magí for the integration of the electronic components of the prototype, to Roger Pi for the great common work for AUV integration and calibration, and to Pere Ridao, Josep Forest and Albert Palomer for their guidance.
Special thanks to Lluís, Roger and Pere for their huge help in the logistics of the sea scanning missions.
