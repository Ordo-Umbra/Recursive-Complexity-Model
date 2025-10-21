# Mini RCM Reasoning Agent

The Mini Recursive Complexity Model (RCM) Reasoning Agent is a lightweight prototype that operationalizes the S‑functional in a discrete‑time reasoning loop. It is designed as both a demonstration and a minimal browser-hosted agent for interactive exploration.

🔑 Core Principle
At each step, the agent maximizes the functional:

S(\phi{t+1} \mid \phit) = \Delta C(\phi{t+1}, \phit) + \kappa \cdot \Delta I(\phi{t+1}, \phit)

- ΔC → change in structural complexity (entropy + graph edges)  
- ΔI → change in mutual information across active relations  
- κ → adaptive trade‑off between exploration and coherence  

This ensures the agent avoids trivial equilibria (pure order) and chaotic divergence (pure noise).

🧠 State Representation
- Belief vector \mathbf{v} \in [0,1]^d: soft activations over d atoms  
- Adjacency graph A: sparse binary edges encoding semantic relations  
- Initialization: uniform priors, self‑loops only  

This hybrid structure allows both propositional and relational reasoning.

🔄 Reasoning Loop
1. Propose candidate actions (perturb activations, toggle edges, merge nodes, inject noise).  
2. Evaluate ΔC and ΔI for each candidate.  
3. Select action maximizing S.  
4. Classicalization step: snap near‑binary beliefs to 0/1, pruning unstable edges.  
5. Iterate until ΔS stabilizes or a step limit is reached.  

The loop converges to local optima, with optional annealing for global search.

📊 Outputs
- Inference layer: top‑scoring beliefs by κ‑weighted coherence  
- Trace log: \{t, St, ΔCt, ΔI_t\} for replay and analysis  
- Visualization: evolving belief graph (nodes + edges) and ΔC/ΔI trajectories  

🎯 Purpose
- Demonstration: Shows how RCM principles can be embodied in a minimal agent running in a browser.  
- Research testbed: Provides a falsifiable, extensible substrate for experimenting with motif overlays, symbolic persistence, and cognitive dynamics.  
- Educational bridge: Makes the abstract mathematics of RCM tangible for contributors and students.  

---

👉 Suggested next step: host this agent as a GitHub Pages demo so visitors can interactively watch the reasoning loop evolve. This would make the README not just a theoretical entry point, but a live demo.

Live demos (HTML)
- Repository-relative links (open the files in GitHub):
  - Minimal RCM Agent demo: ./Minimal-Agent.html
  - RCM Consensus Engine demo: ./consensus.html

- Direct GitHub Pages links (if Pages is enabled for this repository and serving from the default branch root):
  - Minimal RCM Agent demo: https://ordo-umbra.github.io/Recursive-Complexity-Model/Minimal-Agent.html
  - RCM Consensus Engine demo: https://ordo-umbra.github.io/Recursive-Complexity-Model/consensus.html
https://github.com/Ordo-Umbra/Recursive-Complexity-Model/blob/main/RCM_Agent.ipynb

Citation
If you use RCM in research or applications, please cite as:
[Devon Birch]. (2025). Recursive Complexity Model (RCM): Unifying emergence, causality, and quantum-classical feedback. GitHub. https://github.com/Ordo-Umbra/Recursive-Complexity-Model

License
MIT License - open and free for research and development.
