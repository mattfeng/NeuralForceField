---
sidebar_position: 1
---

# Introduction

The Neural Force Field (NFF) code is an API based on SchNet [1-4], DimeNet [5], PaiNN [6-7] and DANN [8]. It provides an interface to train and evaluate neural networks for force fields. It can also be used as a property predictor that uses both 3D geometries and 2D graph information [9].

This code repository is developed in the Learning Matter Lab (led by prof. Rafael Gomez-Bombarelli) at MIT.

## Installation

### Conda
```bash
conda create -n nff python=3.9

# install rdkit
conda install -c conda-forge rdkit
# or: pip install rdkit

# install torch; use the command given on the PyTorch website
# for your specific platform: https://pytorch.org/get-started/locally/
conda install -c pytorch pytorch torchvision torchaudio
# or: pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu116

# install NeuralForceField
pip install .
```

## Getting started

### Loading a dataset

### Creating a model

```python
from nff.train import get_model

params = {
    "n_atom_basis": 256,
    "n_filters": 256,
    "n_gaussians": 32,
    "n_convolutions": 4,
    "cutoff": 5.0,
    "trainable_gauss": True,
    "dropout_rate": 0.2
}

model = get_model(params, model_type="SchNet")
```

## Other important Python libraries

- ASE (`ase`). The [Atomic Simulation Environment](https://wiki.fysik.dtu.dk/ase/).

## Abbreviations
- **PBC.** periodic boundary conditions

## References

* [1] K.T. Schütt. F. Arbabzadah. S. Chmiela, K.-R. Müller, A. Tkatchenko.  
*Quantum-chemical insights from deep tensor neural networks.*
Nature Communications **8**. 13890 (2017)   
[10.1038/ncomms13890](http://dx.doi.org/10.1038/ncomms13890)
* [2] K.T. Schütt. P.-J. Kindermans, H. E. Sauceda, S. Chmiela, A. Tkatchenko, K.-R. Müller.  
*SchNet: A continuous-filter convolutional neural network for modeling quantum interactions.*
Advances in Neural Information Processing Systems 30, pp. 992-1002 (2017) [link](http://papers.nips.cc/paper/6700-schnet-a-continuous-filter-convolutional-neural-network-for-modeling-quantum-interactions)
* [3] K.T. Schütt. P.-J. Kindermans, H. E. Sauceda, S. Chmiela, A. Tkatchenko, K.-R. Müller.  
*SchNet - a deep learning architecture for molecules and materials.* 
The Journal of Chemical Physics 148(24), 241722 (2018) [10.1063/1.5019779](https://doi.org/10.1063/1.5019779)
* [4] K.T. Schütt, P. Kessel, M. Gastegger, K. Nicoli, A. Tkatchenko, K.-R. Müller.
*SchNetPack: A Deep Learning Toolbox For Atomistic Systems.*
J. Chem. Theory Comput. **15**(1), 448-455 (2019). [10.1021/acs.jctc.8b00908](https://doi.org/10.1021/acs.jctc.8b00908)
* [5] J. Klicpera, G. Janek, S. Günnemann. *Directional message passing for molecular graphs.* ICLR (2020). [URL](https://openreview.net/attachment?id=B1eWbxStPH&name=original_pdf).
* [6] K. T. Schütt, O. T. Unke, M. Gastegger. *Equivariant message passing for the prediction of tensorial properties and molecular spectra*. arXiv preprint, 2021. [arXiv:2102.03150](https://arxiv.org/pdf/2102.03150.pdf)
* [7] S. Axelrod, E. Shakhnovich, R. Gómez-Bombarelli. *Thermal half-lives of azobenzene derivatives: virtual screening based on intersystem crossing using a machine learning potential.* arXiv preprint (2022). [arXiv:2207.11592](https://arxiv.org/abs/2207.11592).
* [8] S. Axelrod, E. Shakhnovich, R. Gómez-Bombarelli. *Excited state non-adiabatic dynamics of large photoswitchable molecules using a chemically transferable machine learning potential.* Nat. Commun. **13**, 3440 (2022). [URL](https://www.nature.com/articles/s41467-022-30999-w)
* [9] S. Axelrod and R. Gomez-Bombarelli. *Molecular machine learning with conformer ensembles.* arXiv preprint (2020). [arXiv:2012.08452](https://arxiv.org/abs/2012.08452?fbclid=IwAR2KlinGWeEHTR99m8x9nu2caURqIg04nQkimqzYRcTIqFq6qgv6_RgmVzo).
* [10] D. Schwalbe-Koda, A.R. Tan, and R. Gomez-Bombarelli. *Differentiable sampling of molecular geometries with uncertainty-based adversarial attacks.* Nat. Commun. **12**, 5104 (2021). [URL](https://doi.org/10.1038/s41467-021-25342-8).
