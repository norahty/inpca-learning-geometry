# InPCA Trajectories: Understanding Learning Dynamics via Information Geometry

**Author:** Nora Han  
**Status:** Research Tool — Code available upon request  
**Last updated:** October 2025  

---

## Overview

This project studies **how deep networks learn over time** by examining their trajectories through an **information-geometric lens**.  
It uses *Information PCA (InPCA)* to embed probability distributions produced by a neural network at different training stages, allowing researchers to visualize and analyze how the model’s output structure evolves during learning.

---

## Goal

The goal of this tool is to provide an interpretable framework for **understanding the trajectories learned by deep networks** — how model predictions, viewed as probability distributions, move through space as training progresses.  

Rather than measuring performance alone, this approach focuses on the **geometric organization** of learning: how representations change, stabilize, or diverge as optimization proceeds.

---

## Method Summary

1. **Collect model checkpoints** at multiple training steps.  
2. **Convert outputs to probability distributions** (e.g., softmax predictions).  
3. **Compute pairwise Hellinger similarities** between checkpoints.  
4. **Apply double-centering** to obtain the InPCA embedding.  
5. **Visualize trajectories** in low-dimensional space to study learning structure.

---

## Applications

- Studying how networks move from random initialization toward structured solutions.  
- Comparing learning dynamics across different training objectives or architectures.  
- Understanding representational changes during optimization.  

---

## Code Availability

The full implementation includes:
- Checkpoint collection tools  
- InPCA embedding computation  
- 2-D and 3-D visualization interfaces  

The code is **available upon request** for research and educational use.  
Please contact:

📧 **norahty [at] seas.upenn.edu**

---

## 🧩 Reference

K.N. Quinn, C.B. Clement, F. De Bernardis, M.D. Niemack, & J.P. Sethna, Visualizing probabilistic models and data with Intensive Principal Component Analysis, Proc. Natl. Acad. Sci. U.S.A. 116 (28) 13762-13767, https://doi.org/10.1073/pnas.1817218116 (2019).
