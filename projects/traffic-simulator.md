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

## Demo

<div style="text-align: center; margin: 1.5rem 0;">
  <div style="display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; align-items: flex-start;">
    <img src="{{ site.baseurl }}/assets/videos/traffic_simulation.gif" alt="Traffic simulation ordered" style="width: 48%; border-radius: 4px;" />
    <img src="{{ site.baseurl }}/assets/images/traffic_simulator_ordering.png" alt="Ordered lateral distribution" style="width: 48%; border-radius: 4px;" />
  </div>
  <p style="font-size: 1.3rem; color: #fff; font-style: italic; margin-top: 0.5rem;">A randomized simulation showing ordered behavior (see lateral distribution on the right)</p>
</div>

<div style="text-align: center; margin: 1.5rem 0;">
  <div style="display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; align-items: flex-start;">
    <img src="{{ site.baseurl }}/assets/videos/traffic_simulation_2.gif" alt="Traffic simulation disordered" style="width: 48%; border-radius: 4px;" />
    <img src="{{ site.baseurl }}/assets/images/traffic_simulator_disordered.png" alt="Disordered lateral distribution" style="width: 48%; border-radius: 4px;" />
  </div>
  <p style="font-size: 1.3rem; color: #fff; font-style: italic; margin-top: 0.5rem;">Another randomized simulation, this time with higher level of disorder (see lateral distribution on the right)</p>
</div>

## Links

- [GitHub Repository](https://github.com/harshjog/traffic_simulator)

<ul class="actions">
  <li><a href="{{ site.baseurl }}/projects" class="button">← Back to Projects</a></li>
</ul>