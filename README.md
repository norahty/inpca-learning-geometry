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
## Concept

Let \( p_t(x) \) denote the model’s predictive distribution at training step \( t \).  
InPCA constructs an embedding based on pairwise **Hellinger inner products** between checkpoints:

\[
\langle p_i, p_j \rangle_H = \sum_x \sqrt{p_i(x)\, p_j(x)}.
\]

After double-centering the corresponding kernel matrix, the top principal components yield coordinates that preserve **information-geometric distances** between learning states.  
This provides a quantitative and visual representation of the model’s trajectory through probability space.

---

## Method Summary

1. Collect model checkpoints at selected training steps.  
2. Compute predicted probability vectors on a fixed probe set.  
3. Build the Hellinger-based similarity matrix and apply double-centering.  
4. Perform eigen-decomposition to obtain InPCA coordinates.  
5. Visualize trajectories across time or training conditions.

---

## Example Results

### 1. MNIST Training Trajectories
Visualization of multiple MLPs trained on distinct MNIST subsets.  
Each curve represents the evolution of output probabilities projected into InPCA space.

<img width="876" height="452" alt="Screenshot 2025-10-17 at 2 47 02 PM" src="https://github.com/user-attachments/assets/68253cd5-1e28-408f-a0a4-1c88f0db319b" />


---

### 2. Toy Synthetic Dataset
Simple two-class setting (N = 4) used for controlled experiments on convergence and reversibility.  
Distinct target endpoints illustrate how optimization paths diverge and stabilize in low-dimensional geometry.

<img width="1430" height="703" alt="image" src="https://github.com/user-attachments/assets/1ba5a620-1509-49d9-96b2-fc1ec6299aa6" />


---

### 3. Game-Theoretic Dynamics
InPCA applied to repeated-game learning dynamics, comparing instantaneous and time-averaged strategies in a 3-D embedding of probability updates.

<img width="1019" height="448" alt="image" src="https://github.com/user-attachments/assets/f583ac06-88e6-4c54-b321-7d4bbc37bffc" />
<img width="1019" height="448" alt="Screenshot 2025-10-17 at 2 53 07 PM" src="https://github.com/user-attachments/assets/03f809a1-c578-46e7-9737-2907f9f99963" />

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
