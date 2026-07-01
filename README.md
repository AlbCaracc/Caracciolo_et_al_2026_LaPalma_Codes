# README

This repository contains the code used to perform the clinopyroxene trace-element
clustering, map visualisation, and clinopyroxene-liquid thermobarometry presented in
the manuscript "Recurrent evacuation of mantle mush by mafic recharge in ocean islands
revealed by clinopyroxene from La Palma" (Caracciolo et al.).

Map and single-spot trace-element data are archived on Zenodo:
https://zenodo.org/records/21081067

## Folder layout

```
SupplementaryMaterial_CumbreVieja/
├── Clustering_LaPalma_Final.ipynb
├── Figure5_LaPalma_Final.ipynb
├── README_LaPalma.md
├── requirements.txt
├── Maps_SingleSpots_LaPalma/
│   ├── ElCharco1712/ ...
│   ├── Teneguia1971/ ...
│   ├── 2021LaPalma/ ...
│   └── Single spot_Clustering/ ...
└── CumbreVieja_Thermobar/
    ├── PT_CumbreVieja_Final.ipynb
    ├── Input_ElCharco1712.xlsx
    ├── Input_Teneguia1971.xlsx
    └── Input_Tajogaite2021.xlsx
```

Inside the main folder you will find the following Jupyter notebooks:

1. **Clustering_LaPalma_Final.ipynb**: K-Means clustering of map pixels and single-spot
   analyses. Covers data loading, masking, normalisation, the elbow method used to
   select K, the final clustering with PCA and t-SNE visualisation, the clustering
   stability analysis, and the cluster-coloured crystal maps. Requires the
   `Maps_SingleSpots_LaPalma` dataset (see Zenodo link above) placed in the same
   folder as this notebook.

2. **Figure5_LaPalma_Final.ipynb**: Builds the main-text Figure 5 (Cr / Sc / Zr
   concentration maps for one representative crystal per eruption). Also requires
   the `Maps_SingleSpots_LaPalma` dataset.

3. **PT_CumbreVieja_Final.ipynb**: Clinopyroxene-liquid thermobarometry for the three
   eruptions (El Charco 1712, Teneguía 1971, Tajogaite 2021), using the
   [Thermobar](https://thermobar.readthedocs.io/en/latest/introduction.html)
   package (Wieser et al., 2022). Uses the three `Input_<Eruption>.xlsx` files
   included alongside this notebook, inside the `CumbreVieja_Thermobar` folder.
   Includes Cpx-Liquid melt matching for all three eruptions in one pass.

## Requirements

Python 3.10. All required packages are listed in `requirements.txt`.

## How to run

1. Place the `Maps_SingleSpots_LaPalma` dataset folder (downloaded from the Zenodo
   link above) in the same directory as `Clustering_LaPalma_Final.ipynb` and
   `Figure5_LaPalma_Final.ipynb`.
2. Create and activate a Python 3.10 environment, then install the requirements:
   ```
   pip install -r requirements.txt
   ```
3. Navigate to the folder that contains the codes and run `jupyter lab`, or
   open the folder in VS Code. 
4. Run each notebook top to bottom (Run -> Run All Cells).
   Figures are written automatically to `./Figures/`.

For the thermobarometry notebook, run `PT_CumbreVieja_Final.ipynb` the same way from
inside its own folder, alongside the three `Input_<Eruption>.xlsx` files. Results
are written next to the notebook as one spreadsheet per P–T calibration and
eruption.

## Contact

If you have any issues, please write to: alberto@hi.is

## Disclaimer
The notebooks were developed by the coauthors with the assistance of Claude (Anthropic)
for coding support and debugging. All code was reviewed, tested, and validated by the authors.




