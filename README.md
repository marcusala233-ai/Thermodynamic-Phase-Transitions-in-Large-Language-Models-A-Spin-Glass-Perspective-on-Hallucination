# Thermodynamic Phase Transitions in Large Language Models: A Spin Glass Perspective

[![DOI](https://zenodo.org/badge/1152131662.svg)](https://doi.org/10.5281/zenodo.18517147)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Status](https://img.shields.io/badge/status-submitted_PRE-red)](https://journals.aps.org/pre/)

**Repository for the research paper submitted to *Physical Review E*.**

## 📄 Abstract

This project investigates the phenomenon of "hallucination" in Large Language Models (LLMs) through the lens of Statistical Mechanics. By mapping the Transformer's self-attention mechanism to a continuous Modern Hopfield Network (Dense Associative Memory), we derive an effective Hamiltonian governing the inference dynamics.

We identify a critical temperature $T_c$, determined by the spectral properties of the weight matrices, which separates a ferromagnetic **Retrieval Phase** (factual accuracy) from a spin-glass **Confabulation Phase** (hallucination). Our mean-field theoretical analysis, supported by numerical simulations, suggests that hallucination is an emergent property of operating high-capacity neural networks near the edge of chaos.

## 📊 Key Findings

1.  **Isomorphism:** The attention mechanism is mathematically equivalent to the energy minimization step in a continuous Hopfield Network with Log-Sum-Exp energy.
2.  **Phase Transition:** Hallucination is not random noise, but a distinct thermodynamic phase (Glassy Phase) occurring between the ordered retrieval phase and the paramagnetic noise phase.
3.  **Critical Temperature ($T_c$):** We derive an analytical bound for the onset of hallucination: $T_c \approx \lambda_{max}(W)$, where $\lambda_{max}$ is the spectral radius of the covariance matrix of stored patterns.

![Phase Diagram](figures/phase_diagram.png)
*Fig 1. Phase diagram showing the collapse of factual retrieval (black) and the emergence of hallucination (red) as temperature increases.*

## 📂 Repository Structure

```bash
.
├── src/
│   ├── simulation.py       # Main simulation script (Hopfield dynamics)
│   ├── analytics.py        # Spectral analysis of weight matrices
│   └── utils.py            # Helper functions
├── paper/
│   ├── main.tex            # LaTeX source for Physical Review E
│   ├── references.bib      # Bibliography
│   └── figures/            # High-resolution plots
├── notebooks/
│   └── phase_transition.ipynb # Jupyter notebook for interactive exploration
├── README.md
└── requirements.txt

🚀 Reproduction
To reproduce the phase diagrams presented in the paper:

1. Install dependencies:
pip install -r requirements.txt

2. Run the simulation:
python src/simulation.py --n_neurons 128 --alpha 2.0 --steps 1000

📝 Mathematical ModelThe system is governed by the effective Hamiltonian:$$ \mathcal{H}(\mathbf{x}) = \frac{1}{2} \mathbf{x}^T \mathbf{x} - \frac{1}{\beta} \ln \left( \sum_{\mu=1}^P e^{\beta \boldsymbol{\xi}^\mu \cdot \mathbf{x}} \right) $$Where $\mathbf{x}$ is the state vector, $\boldsymbol{\xi}^\mu$ are the stored patterns (memories), and $\beta = 1/T$ is the inverse temperature.

🔗 Citation
If you use this code or theoretical framework, please cite the preprint/code:
@software{roriz2026thermo,
  author       = {Marcus A. P. Roriz},
  title        = {Thermodynamic Phase Transitions in Large Language Models: Code and Data},
  year         = 2026,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.18517147},
  url          = {[https://github.com/YOUR_USERNAME/ai-thermodynamics-pre](https://github.com/YOUR_USERNAME/ai-thermodynamics-pre)}
}
📧 Contact
Marcus A. P. Roriz

Google AI Red Team

Independent Researcher

Email: marcusala233@gmail.com
