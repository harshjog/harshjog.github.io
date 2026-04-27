---
layout: post
title: Fractal Graphics
description: Animated fractal GIF generator with GPU support
image:
show_tile: false
---

A fractal animation generator that creates mesmerising self-similar animated patterns and exports them as optimised GIF files. Features real-time visualisation, customisable complexity levels, and optional GPU acceleration via PyOpenCL.

## Overview

The generator iterates over a configurable parameter space to produce animated fractal sequences. Multiple GIF optimisation passes reduce file size while preserving visual fidelity. GPU mode using PyOpenCL significantly speeds up computation for high-complexity renders.

## Tech Stack

- **Python** — core generator
- **PyOpenCL** — optional GPU acceleration
- **Pillow / imageio** — GIF rendering and optimisation

## Demo

<div style="text-align: center; margin: 1.5rem 0;">
  <div style="display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap;">
    <img src="{{ site.baseurl }}/assets/videos/fractal_animation_optimized5_v4.gif" alt="Fractal variation 1" style="max-width: 48%; border-radius: 4px;" />
    <img src="{{ site.baseurl }}/assets/videos/fractal_animation_optimized5_v3.gif" alt="Fractal variation 2" style="max-width: 48%; border-radius: 4px;" />
  </div>
  <p style="font-size: 1.3rem; color: #fff; font-style: italic; margin-top: 0.5rem;">Two variations with different fractal patterns and color schemes generated using this code</p>
</div>

## Links

- [GitHub Repository](https://github.com/harshjog/fractal_graphics)

<ul class="actions">
  <li><a href="{{ site.baseurl }}/projects" class="button">← Back to Projects</a></li>
</ul>