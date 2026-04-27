---
layout: post
title: 3D Gesture Control
description: Manipulate 3D objects in a live webcam feed via hand gestures
image: 
show_tile: false
---

An interactive application that projects 3D objects — cubes and spheres — onto a live webcam feed and allows real-time manipulation through hand gestures. Users can move, scale, and rotate objects using pinch and pointing gestures, with correct depth rendering.

## Overview

Hand landmarks are detected each frame using MediaPipe. Gesture state (pinch distance, finger direction) is mapped to 3D transform parameters, which are applied to Open3D scene objects and composited onto the webcam frame via OpenCV.

## Tech Stack

- **Python** — core application
- **MediaPipe** — real-time hand landmark detection
- **OpenCV** — webcam capture and frame compositing
- **Open3D** — 3D object modelling and rendering

## Demo

<div style="text-align: center; margin: 1.5rem 0;">
  <video controls style="max-width: 100%; border-radius: 4px;">
    <source src="{{ site.baseurl }}/assets/videos/3d_gesture.mp4" type="video/mp4" />
  </video>
  <p style="font-size: 1.3rem; color: #fff; font-style: italic; margin-top: 0.5rem;">An example of how the gesture control works in real time</p>
</div>

## Links

- [GitHub Repository](https://github.com/harshjog/3d-gesture-control)

<ul class="actions">
  <li><a href="{{ site.baseurl }}/projects" class="button">← Back to Projects</a></li>
</ul>