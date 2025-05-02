# Lightweight ANN Based On ANI-1 for Small Organic Molecules

A Jupyter notebook that implements and trains a simplified atom‑centered neural network (ANI) potential on the ANI‑1 GDB‑S01–S04 dataset (molecules with H, C, N, O and up to four heavy atoms). This model achieves RMSE ≤ 5 kcal·mol⁻¹ with a minimal two‑layer architecture.

## Features

- **AEV featurization** via Behler–Parrinello symmetry functions (`torchani.AEVComputer`)
- **Per‑element feed‑forward networks** (384→128→1) assembled into `torchani.ANIModel`
- **Training utilities** with early stopping, MSE loss, Adam optimizer, and unit conversion (hartree → kcal·mol⁻¹)
- **Reproducibility checks** (multiple seeds) and **k‑fold cross‑validation**
- **Plots**: loss curves, parity scatter, and MAE distributions
- **Comparison** against the original ANI‑1 paper’s reported RMSE (1.30 kcal·mol⁻¹)  

## Usage

1. **Clone** this repository.  
2. **Install dependencies** (e.g. `pip install torch torchani numpy tqdm matplotlib pandas`).  
3. **Download** the ANI‑1 S01–S04 HDF5 file (`ani_gdb_s01_to_s04.h5`) and place it in the notebook directory.
4. **Open** and **run** the notebook (`.ipynb`) in Jupyter or VS Code.  

## Context & Reference

This work builds on the ANI‑1 neural potential (Smith et al., *Chem. Sci.*, 2017). ANI‑1 introduced atomic environment vectors (AEVs) derived from Behler–Parrinello symmetry functions to encode local geometry with translational, rotational, and permutational invariance. See:  
> Smith, J. S.; Isayev, O.; Roitberg, A. E. *ANI‑1: An Extensible Neural Network Potential with DFT Accuracy at Force Field Computational Cost.* **Chem. Sci.** 2017, 8 (4), 3192–3203. DOI: 10.1039/C6SC05720A  

Feel free to adapt the notebook. You can try to adapt it for larger datasets (S05–S08) or experiment with deeper architectures.
