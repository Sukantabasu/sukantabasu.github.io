---
layout: page
permalink: /hackathons/shell-ai-2025/
title: Shell.ai Hackathon — Fuel-Blend Properties (2025)
nav: false
---

<div class="hackathon-media" markdown="0">
  <img src="/assets/img/hackathons/shell-ai-2025-alchemist-logo.png" alt="ALCHEMIST — Turning Fuel Data into Gold" style="max-width:220px;width:100%;height:auto;" />
</div>

The 2025 Shell.ai Hackathon asked participants to predict ten properties of a fuel
blend (`BlendProperty1`–`BlendProperty10`) from the volume fractions and individual
properties of its five components — a small-sample (2,000 training rows),
ten-target regression problem scored by MAPE. My entry, **ALCHEMIST**
(_Turning Fuel Data into Gold_), was a **Level-2 finalist (one of ~25 of ~7,000
participants)**.

ALCHEMIST is a five-step ensemble: physics-informed feature engineering (component
contributions and weighted-average blend properties), AutoGluon out-of-fold
predictions to capture inter-target correlations, second-level modelling with
RealMLP and TabPFN, and a sign-preserving harmonic-mean combination to stabilise
MAPE near zero. A lightweight, interactive version — **ALCHEMIST Jr.** — is also
available for quick experimentation.

- Documentation: <https://alchemist-shellai-hackathon-2025.readthedocs.io/>
- Code — full framework: <https://github.com/Sukantabasu/alchemist-shell.ai-hackathon-2025>
- Code — ALCHEMIST Jr.: <https://github.com/Sukantabasu/alchemist-jr-shell.ai-hackathon-2025>
- Model weights: <https://huggingface.co/datasets/sukantabasu/alchemist-shell.ai-hackathon-2025>

<p><a href="/hackathons/">&larr; All hackathons</a></p>
