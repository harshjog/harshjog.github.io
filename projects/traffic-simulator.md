---
layout: post
title: Traffic Simulator
description: Cellular automata model of multi-lane traffic flow
image:
show_tile: false
---

A traffic flow simulator based on the Nagel-Schreckenberg cellular automata model. It models multi-lane vehicle dynamics and lane-changing behaviour, and analyses traffic organisation using entropy-based metrics with visualisations of vehicle movement.

## Overview

The simulator implements the classic NaSch model and extends it to multiple lanes with probabilistic lane-change rules. Throughput and spatial entropy metrics are tracked over time to characterise different traffic regimes (free flow, congested, jammed).

## Tech Stack

- **Python** — core simulation
- **NumPy** — vectorised cellular automata updates
- **Matplotlib** — traffic flow visualisations

## Links

- [GitHub Repository](https://github.com/harshjog/traffic_simulator)

<ul class="actions">
  <li><a href="{{ site.baseurl }}/projects" class="button">← Back to Projects</a></li>
</ul>