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
## Underwater imaging

Visual perception in underwater scenarios is **hard**.
In order to understand how and why, let's have a look at this 360º video recorded by some of my colleagues:

<div align="center">
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/ptkhwTPFvjk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

Even though the visibility conditions on this video were *almost optimal*, we can already identify two main challenges:
- First, the floating particles in the water blur the image and make it lose the sharpness of its features.
- Second, the high attenuation rate of water means that light loses most of its power at distances in the order of meters or tens of meters, depending on its wavelength:
{{< figure src="water_light_absorption.png" caption="Electromagnetic absorption by water ([credits](https://en.wikipedia.org/wiki/Electromagnetic_absorption_by_water#/media/File:Absorption_spectrum_of_liquid_water.png))." numbered="false" width="500">}}

A robust solution against these factors is using sonar.
Sonars are range sensors that use ultrasonic waves to acquire geometrical information about their surroundings.
Ultrasonic waves are mechanical waves and can therefore propagate further and are not affected by water turbidity and varying lighting conditions.
However, they typically produce much noisier results and their resolution is in the order of tens of centimeters.

{{< figure src="sonar_bike.png" caption="Bike measured using a sonar ([credits](http://www.jwfishers.com/multimedia.html))." numbered="false" width="500">}}

- due to [refraction](https://en.wikipedia.org/wiki/Refraction).


## Prototype

[this paper](/publication/underwater-3d-scanner-to-counteract-refraction-calibration-and-experimental-results/)

[model](/publication/underwater-3d-scanner-model-using-a-biaxial-mems-mirror/)

{{< figure src="scanning_scheme.png" caption="Scheme of our underwater 3D scanner." numbered="false" width="500">}}