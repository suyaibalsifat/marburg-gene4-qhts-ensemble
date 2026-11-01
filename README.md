# Predicting Marburg Virus Entry-Inhibitor Activity in the Gene 4 Small ORF-Annotated qHTS Screen with Explainable Ensemble Learning

Code and results accompanying the manuscript by Suyaib Al Sifat and Khandaker Mohammad Mohi Uddin (Department of Computer Science and Engineering, Southeast University, Dhaka, Bangladesh).

The pipeline predicts compound activity in the PubChem qHTS screen of Marburg virus entry annotated to the Gene 4 Small ORF protein (AID 540276). It uses Morgan fingerprints and RDKit physicochemical descriptors for 27,546 compounds, a split-first leakage-controlled workflow, ten base classifiers and eight ensembles, bootstrap and cross-validation statistics, SHAP/native-importance/LIME explanations, and evaluation of the frozen champion on a second PubChem record (AID 720532).

## Main results

| Item | Value |
|---|---|
| Champion | Soft voting of LightGBM and Extra Trees |
| Held-out PR-AUC | 0.657 (95% CI 0.625-0.689) |
| Held-out ROC-AUC | 0.876 |
| Paired bootstrap difference vs. LightGBM (PR-AUC) | 0.013 (95% CI 0.001-0.024) |
| Second record (AID 720532) | ROC-AUC 0.818, PR-AUC 0.414 |

## Repository layout

```
notebooks/marv-gene4-final-pipeline.ipynb   full pipeline, 21 parts, run top to bottom
data/README.md                              where to get the four PubChem tables
results/                                    CSV tables written by the notebook
figures/                                    figures used in the paper
requirements.txt                            Python dependencies
LICENSE                                     MIT
```

## How to run

1. Download the four PubChem tables listed in `data/README.md` (active and inactive tables for AID 540276 and AID 720532).
2. Open the notebook in Kaggle (recommended; the manuscript runs used a CPU-only Kaggle notebook with Python 3.12) or locally, and add the data as a dataset or folder.
3. Edit the four `/kaggle/input/...` paths in Part 1 and Part 18 if you are not using the original Kaggle dataset.
4. Install dependencies: `pip install -r requirements.txt` (the notebook also runs `pip install` in its first cells).
5. Run all cells in order. Parts 16 and 20 download the RDKit synthetic-accessibility module and PDB 5UQY, so they need internet access. Random seeds are fixed in the notebook.

Expected outputs are the CSV tables listed in `results/README.md`, the figures, and the trained model files (`*_pure_enn.pkl`).

## Trained models and processed features

The trained models (`*.pkl`) and the processed feature matrix are too large for a normal git commit and are distributed through the GitHub Releases page of this repository. Pickled models depend on the library versions used to create them (scikit-learn 1.6.1, LightGBM, XGBoost, CatBoost), so load them in a matching environment.

## Citation

If you use this code, please cite the manuscript (citation details will be added after publication).

## Contact

Khandaker Mohammad Mohi Uddin, mohiuddin.kh@seu.edu.bd
