---
layout: page
permalink: /olympics-2020/
title: Olympics 2020
description: Real-time WRF wind forecasts for the Dutch Olympic sailing team at Enoshima, Japan.
nav: false
---

During the Tokyo 2020 Olympic Games (held July–August 2021), I ran the Weather Research and
Forecasting (WRF) model to produce **real-time wind forecasts for the Dutch sailing team** at
Enoshima. Initial and boundary conditions came from the 0.25° Global Forecast System (GFS);
the forecasts used a new-generation gray-zone planetary boundary-layer scheme at 600 m grid
spacing.

See TU Delft's story:
[_The wind app which puts the wind in your sails_](https://www.tudelft.nl/en/ceg/research/stories-of-science/the-wind-app-which-puts-the-wind-in-your-sails).

Each animation below loops through the hourly near-surface wind-speed forecast (with wind
barbs) for the sailing venue over the following ~3 days. Click a panel to play.

<div class="forecast-grid" markdown="0">
  {% assign starts = "07-15,07-16,07-17,07-18,07-19,07-20,07-21,07-22,07-23,07-24,07-25,07-26,07-27,07-28,07-29,07-30,07-31" | split: "," %}
  {% assign labels = "Jul 15,Jul 16,Jul 17,Jul 18,Jul 19,Jul 20,Jul 21,Jul 22,Jul 23,Jul 24,Jul 25,Jul 26,Jul 27,Jul 28,Jul 29,Jul 30,Jul 31 – Aug 1" | split: "," %}
  {% for s in starts %}
  <figure>
    <video controls loop muted playsinline preload="none" poster="/assets/video/olympics/2021-{{ s }}.jpg">
      <source src="/assets/video/olympics/2021-{{ s }}.mp4" type="video/mp4" />
    </video>
    <figcaption>Forecast issued {{ labels[forloop.index0] }}, 2021</figcaption>
  </figure>
  {% endfor %}
</div>
