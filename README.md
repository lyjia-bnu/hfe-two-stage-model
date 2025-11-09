## Model Overview

This project follows a **two-stage** pipeline:

- **Stage-1 (DeepMoleNet/MPNN)** predicts physics-inspired molecular descriptors directly from 3D structures and graph features, using an edge-conditioned message passing network with attention, LSTM refinement, and auxiliary ACSF supervision [1].
- **Stage-2 (MoletoSolv)** maps those descriptors to the target solvation free energy (ΔG_solv, HFE) using an ensemble of classical ML regressors with model fusion (e.g., weighted or stacking) [2].

SMILES → SDF → graph(G) ──[Stage-1: DeepMoleNet]──> descriptor set (pred/QM)
                                                         │
                                                         └─[Stage-2: Mole2Solv]──> ΔG_solv


### References

[1] Z. T. Liu, L. Q. Lin, Q. Q. Jia, Z. Cheng, Y. Y. Jiang, Y. W. Guo, J. Ma,  
*Transferable Multilevel Attention Neural Network for Accurate Prediction of Quantum Chemistry Properties via Multitask Learning*,  
**J. Chem. Inf. Model.** 2021, 61, 1066.

[2] Z. Zhang, D. Peng, L. Liu, L. Shen, W. Fang,  
*Machine Learning Prediction of Hydration Free Energy with Physically Inspired Descriptors*,  
**J. Phys. Chem. Lett.** 2023, 14, 1877.
