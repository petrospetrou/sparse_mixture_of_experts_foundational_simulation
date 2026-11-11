# Sparse Mixture of Experts — Interactive Visual Lab

An interactive, browser-based simulator for understanding how **Sparse Mixture of Experts (MoE)** models route tokens, activate selected experts, and learn to distribute computation efficiently.

### [Launch Interactive Simulator](https://petrospetrou.github.io/sparse_mixture_of_experts_foundational_simulation/)

## What's Inside

The simulator is organized into three interactive chapters:

### 1. Foundational Flow
Explore the core mechanics of sparse routing:
- Dense vs. sparse computation
- Router logits and expert scoring
- Top-K selection, masking, and softmax gating
- Token dispatch, expert execution, and weighted output combination

### 2. Challenges & Solutions
Understand common challenges in sparse MoE systems:
- Expert collapse and uneven utilization
- Noisy routing and load-balancing losses
- Shrinking expert batches and efficient token aggregation

### 3. Training Process
Follow a simplified MoE training cycle:
- Forward pass and prediction loss
- Auxiliary load-balancing loss
- Backpropagation and parameter updates
- Repeated training iterations

## Run Locally

Download the repository and open `index.html` in your browser.

**No installation, dependencies, or backend required.** The simulator runs entirely offline.

## Scope

This is an **educational visualization**, not a production MoE implementation. It uses small, deterministic examples and simplified training scenarios to illustrate routing mechanisms and their challenges.
