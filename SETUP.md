# Setup and Reproduction Notes

The notebooks in this repository are preserved from the original project and therefore retain their original path/configuration cells. Update the path variables in those cells to match your own local dataset layout before running them.

## Core environment

The notebooks use a Python/Jupyter workflow with packages including:

- `numpy`
- `pandas`
- `matplotlib`
- `Pillow`
- `opencv-python`
- `scipy`
- `scikit-learn`
- `torch`
- `torchvision`
- `tqdm`
- `openpyxl`
- `joblib`

Exact package versions were not captured as a locked environment in the submitted project, so this repository does not invent a version-pinned requirements file.

## Data expected by the notebooks

The modeling pipeline expects project metadata/clinical files such as:

- `FileDirectory.csv` (not present in the uploaded archive)
- `PredictingAnemiaInCo-CJStudyData_DATA_2023-07-12_0653.csv`
- `Race and gender file 070425.csv`

It also expects the corresponding image folders and AnyLabel/LabelMe JSON segmentation files.

These research data files are not included in the public portfolio copy. See `DATA_NOT_INCLUDED.md`.

## Suggested run order

1. Organize and verify the raw image folders.
2. Place segmentation JSONs with their matching images.
3. Generate 1.02x nail ROI crops.
4. Run selective brightening if needed.
5. Run conservative reflection handling.
6. Train/evaluate the no-leakage model pipeline using patient-level splits.

The final report identifies the MobileNetV3 MacBook-lite v5 notebook as the main model used for the documented results.
