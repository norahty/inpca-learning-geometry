# InPCA Trajectories: A Visualization Tool for Learning Dynamics

**Author:** Nora Han  
**Status:** Research Tool (Code available upon request)  
**Last updated:** October 2025  

---

## 🧭 Overview

This repository introduces a research tool for **visualizing learning trajectories** in neural networks through the lens of **information geometry**.  
It uses **Information Principal Component Analysis (InPCA)** — a nonlinear embedding of probability distributions — to reveal how model predictions evolve across training.

Instead of tracking loss or accuracy, this framework maps each model checkpoint into a **geometric space of probability outputs**, showing how learning “moves” through that space over time.

---

## 💡 Core Idea

The core method applies the **Hellinger inner product** between model output distributions at different checkpoints:

$\[
\langle p_i, p_j \rangle_H = \sum_x \sqrt{p_i(x) p_j(x)}
\]$

These similarities are then double-centered to construct an **information-geometric embedding**, where trajectories of training models appear as **smooth curves** in low-dimensional space.  

This visualization captures:
- early-stage collapse of model predictions near uniformity,  
- divergence toward distinct endpoint solutions, and  
- directional asymmetries between *forward* (learning toward data) and *backward* (returning to baseline) optimization.

---

## 🔍 What It Shows

- **Dense-Early Checkpoints:** captures fast initial changes in geometry.  
- **Patterns:** distinct endpoints form smooth low-curvature paths.  
- **Forward vs. Backward Trejectories:** direction-dependent curvature and convergence.  
- **Interactive Visualization:** 3D toggles for endpoint, layer type, and training direction.

---

## ⚙️ Example Use Cases

- Studying how *different training datasets or targets* lead to diverging representational geometries.  
- Exploring *alignment* or *collapse* between forward and backward optimization phases.  
- Visualizing the *shared manifold* connecting multiple trained solutions.  

---

## 📊 Output Example

- **Static Panels:** 2-D projections of InPCA embeddings  
- **Interactive 3-D plots:** draggable HTML visualization with endpoint toggles  

*(Representative results include clear paths connecting uniform baselines to learned endpoints.)*

---

## 🔒 Code Availability

The implementation includes:
- Training utilities for grouped endpoints and bidirectional trajectories  
- InPCA embedding and eigen-analysis modules  
- Interactive Plotly-based visualization engine  

The **full source code is available upon request for research or educational purposes**.  
To request access, please contact:

📧 **norahty [at] seas.upenn.edu**

---

## 🧩 Reference

K.N. Quinn, C.B. Clement, F. De Bernardis, M.D. Niemack, & J.P. Sethna, Visualizing probabilistic models and data with Intensive Principal Component Analysis, Proc. Natl. Acad. Sci. U.S.A. 116 (28) 13762-13767, https://doi.org/10.1073/pnas.1817218116 (2019).

---

*All content © 2025 Nora Han. This project is for research and educational use only.*
