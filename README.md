# Sparse Mixture of Experts — Interactive Routing Lab

An interactive, browser-based teaching lab exploring the **routing mechanisms of Sparse Mixture of Experts (MoE)** models. It demonstrates how a router assigns scores to experts, selects a small subset through **Top-K routing**, and combines their outputs. It also introduces key challenges of sparse routing, including expert overload, load balancing, auxiliary losses, and noisy routing.

**[Open the interactive lab](https://petrospetrou.github.io/sparse_mixture_of_experts_foundational_simulation/)**

## Overview

The lab is designed to make sparse expert routing visual, intuitive, and approachable. Unlike dense Mixture of Experts models, where all experts contribute to each prediction, sparse MoE models activate only a selected subset of experts for each token.

Rather than implementing a complete Transformer or reproducing published experiments, the simulator uses simplified examples, animated routing diagrams, interactive controls, and optional mathematical explanations to demonstrate how sparse routing works.

### What you'll explore

**1. Sparse MoE architecture**

- How a token enters a sparse Mixture of Experts layer.
- The roles of the router and the available experts.
- Why sparse MoE activates only a subset of experts instead of all of them.

**2. Router scoring**

- How the router assigns a score to each expert for an input token.
- How softmax converts routing logits into probabilities.
- How different tokens can receive different routing scores.

**3. Top-K expert selection**

- How the router selects the K highest-scoring experts.
- How Top-1, Top-2, and Top-3 routing differ.
- Why unselected experts are skipped for the current token.

**4. Expert activation and output combination**

- How tokens are dispatched to the selected experts.
- How routing weights determine each selected expert's contribution.
- How selected expert outputs are combined into a single result.

**5. Interactive routing playground**

- Explore how different input tokens produce different routing decisions.
- Change the number of active experts using Top-K controls.
- Observe how expert selection and routing weights change interactively.

**6. Challenges of sparse MoE**

- **Expert overload:** Why too many tokens may be routed to the same experts.
- **Load balancing:** Why distributing token assignments across experts is important.
- **Auxiliary load-balancing loss:** How an additional training objective can encourage more balanced expert utilization.
- **Noisy routing:** How adding noise to routing scores during training can encourage exploration.
- **Expert capacity:** Why capacity limits matter when an expert receives more token assignments than it can process.

## Run locally

No installation, build tools, package manager, or backend is required.

1. Download or clone this repository.
2. Open `index.html` in a modern web browser.
3. Use the navigation buttons, token examples, Top-K controls, and interactive demonstrations to explore the routing process.

The lab is self-contained, with its styles, scripts, and pre-rendered mathematical SVGs embedded in the HTML. It is designed to work offline.

## Scope and limitations

This project is an **educational simulation**, not a complete implementation of a production-scale Sparse MoE model or an empirical reproduction of the cited papers.

The simulator uses illustrative routing scores, simplified expert outputs, and small token batches to demonstrate the fundamental mechanisms of sparse routing. Its examples of expert overload, capacity constraints, auxiliary load balancing, and noisy routing are conceptual demonstrations rather than full-scale training procedures.

The primary focus is **token-to-expert routing**, not Transformer architecture, distributed expert computation, backpropagation, or end-to-end language model training.

## References

1. Shazeer, N., Mirhoseini, A., Maziarz, K., et al. (2017). *Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer*. **International Conference on Learning Representations (ICLR)**.
2. Fedus, W., Zoph, B., & Shazeer, N. (2022). *Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity*. **Journal of Machine Learning Research, 23**(120), 1–39.
3. Lepikhin, D., Lee, H., Xu, Y., et al. (2021). *GShard: Scaling Giant Models with Conditional Computation and Automatic Sharding*. **International Conference on Learning Representations (ICLR)**.
4. Jiang, A. Q., Sablayrolles, A., Roux, A., et al. (2024). *Mixtral of Experts*. **International Conference on Learning Representations (ICLR)**.
