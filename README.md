# SWCNet — MI-EEG Classification (BCIC-IV-2a)

Implementation and improvement of SWCNet from:
> *"A Novel CNN With Sliding Window Technique for Enhanced Classification of MI-EEG Sensor Data"* — IEEE Sensors Journal, 2025

| Notebook | Description | Setup II Avg Accuracy |
|---|---|---|
| `CNN_SW.ipynb` | Baseline SWCNet reproduction | 72.80% |
| `improvedcnn.ipynb` | Ensemble of 5 SWCNets | 74.54% |

Paper reports 69.58% on Setup II.

---

## How to Run

**1. Get the dataset**

Dataset (BCICIV_2a_gdf folder): [Google Drive Link](https://drive.google.com/drive/folders/1Qb1YzEZQdO5aos--2MUsxT3YUkPs4rw3?usp=sharing)

Download and upload it to your own Google Drive.

**2. Open notebook in Google Colab**

- File → Upload notebook → select `CNN_SW.ipynb` or `improvedcnn.ipynb`
- Runtime → Change runtime type → **T4 GPU**

**3. Update the dataset path**

Near the top of the notebook, change this line to match where you put the folder:

```python
DATA_DIR    = "/content/drive/MyDrive/BCICIV_2a_gdf"
RESULTS_DIR = "/content/drive/MyDrive/swcnet_results"
```

**4. Run all cells** — Runtime → Run all

Cell 1 installs packages. Cell 2 mounts Drive (you'll need to click the auth link).

---

## Runtime

| Notebook | GPU T4 |
|---|---|
| CNN_SW.ipynb | ~45–60 min (all 9 subjects) |
| improvedcnn.ipynb | ~3–4 hours (5 models × 10 folds × 9 subjects) |

To test quickly with just Subject 1, find the main loop and change `range(1, 10)` to `range(1, 2)`.
