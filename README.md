# Spatial Neuroblastoma

Analysis of spatial transcriptomics (Visium) and fluorescence imaging data from neuroblastoma tumoroids: tumoroid annotation, gene expression heterogeneity, nuclear segmentation, and statistical testing of spatial gene expression patterns.

## Contents

### `notebooks/`

- **`polygon_annotation.ipynb`** — Interactive annotation of tumoroid outlines on the H&E image. Polygons are saved incrementally to a JSON file.
- **`heterogeneite_tumoroid.ipynb`** / **`heterogeneite_tumoroids.ipynb`** — Heterogeneity analysis between tumoroids: shared vs. specific gene expression, PCA and hierarchical clustering on mean expression profiles, coefficient of variation, correlation heatmaps.
- **`Wilcoxon_test.ipynb`** — Statistical testing (Wilcoxon Mann-Whitney, BH-corrected) comparing spot distance-to-centroid distributions between gene-positive and gene-negative spots (VEGFA, MKI67) per tumoroid.
- **`segmentation_pipeline.ipynb`** — Nuclear segmentation pipeline on large fluorescence images (StarDist + preprocessing + size filtering).
- **`segmentation_bigger_nuclei.ipynb`** — Comparison of segmentation methods (thresholding, watershed, StarDist, CellPose).
- **`stardist_big_param_test.ipynb`** — Parameter sweep for StarDist segmentation (probability/NMS thresholds).

### `images/`

Output figures from the segmentation and preprocessing steps (tumoroid map, nuclei segmentation comparisons per region).

## Data

Raw spatial transcriptomics and imaging data are not included in this repository (see `.gitignore`). Notebooks expect the data files in their respective expected paths — adjust paths at the top of each notebook as needed.

## Requirements

Main Python dependencies: `scanpy`/`anndata`, `numpy`, `pandas`, `scikit-learn`, `scipy`, `shapely`, `matplotlib`, `tifffile`, `stardist`, `cellpose`.
