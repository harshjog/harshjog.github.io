---
layout: post
title: Fractal Graphics
description: Animated fractal GIF generator with GPU support
image:
show_tile: false
nav-menu: true
---

A fractal animation generator that creates mesmerising self-similar animated patterns and exports them as optimised GIF files. Features real-time visualisation, customisable complexity levels, and optional GPU acceleration via PyOpenCL.

## Overview

The generator iterates over a configurable parameter space to produce animated fractal sequences. Multiple GIF optimisation passes reduce file size while preserving visual fidelity. GPU mode using PyOpenCL significantly speeds up computation for high-complexity renders.

## Tech Stack

- **Python** — core generator
- **PyOpenCL** — optional GPU acceleration
- **Pillow / imageio** — GIF rendering and optimisation

## Links

- [GitHub Repository](https://github.com/harshjog/fractal_graphics)

<ul class="actions">
  <li><a href="{{ site.baseurl }}/projects" class="button">← Back to Projects</a></li>
</ul>