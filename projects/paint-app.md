---
layout: post
title: Paint App
description: Real-time handwriting recognition with a CNN
image:
show_tile: false
---

A paint application with real-time handwriting recognition trained on the EMNIST database. Users can draw characters on a canvas that are automatically classified by a convolutional neural network supporting 47 character classes — digits and letters.

## Overview

The app combines a freehand drawing canvas with a live inference pipeline. As the user draws, the CNN continuously classifies the strokes against the EMNIST dataset, displaying predictions in real time.

## Tech Stack

- **Python** — core application
- **TensorFlow** — CNN model training and inference
- **OpenCV** — canvas rendering and image processing
- **NumPy** — numerical operations

## Links

- [GitHub Repository](https://github.com/harshjog/paint_app)

<ul class="actions">
  <li><a href="{{ site.baseurl }}/projects" class="button">← Back to Projects</a></li>
</ul>