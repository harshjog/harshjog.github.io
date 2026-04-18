---
layout: post
title: 3D Gesture Control
description: Manipulate 3D objects in a live webcam feed via hand gestures
image:
show_tile: false
nav-menu: true
---

An interactive application that projects 3D objects — cubes and spheres — onto a live webcam feed and allows real-time manipulation through hand gestures. Users can move, scale, and rotate objects using pinch and pointing gestures, with correct depth rendering.

## Overview

Hand landmarks are detected each frame using MediaPipe. Gesture state (pinch distance, finger direction) is mapped to 3D transform parameters, which are applied to Open3D scene objects and composited onto the webcam frame via OpenCV.

## Tech Stack

- **Python** — core application
- **MediaPipe** — real-time hand landmark detection
- **OpenCV** — webcam capture and frame compositing
- **Open3D** — 3D object modelling and rendering

## Links

- [GitHub Repository](https://github.com/harshjog/3d-gesture-control)

<ul class="actions">
  <li><a href="{{ site.baseurl }}/projects" class="button">← Back to Projects</a></li>
</ul>