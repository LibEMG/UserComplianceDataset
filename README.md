# UserComplianceDataset

6-subject (5M, 1F, 23 - 31 years old) dataset for continuous estimation of 2 DOFs: hand open/close (DOF 1) and wrist rotation (DOF 2).  Each participant provided 3 distinct sets: 2 emulated behaviours, namely "All or Nothing" and "Anticipation", and a baseline set of data. Check out our MEC publication for an in-depth look at data collection details: <https://conferences.lib.unb.ca/index.php/mec/article/view/2507>.

## Usage

We recommend that this dataset is used with our open-source toolkit, `LibEMG`, [publicly available on GitHub](https://github.com/LibEMG/libemg). This dataset can be imported, downloaded, and ready for use in a few lines of code when used with `LibEMG`.

```python
from libemg.datasets import UserComplianceDataset
odh = UserComplianceDataset().prepare_data()
```

## Data Structure

The data structure follows the format `behaviour/subject/movement`, where explanations of each component are provided below:

- `behaviour`: Type of behaviour (e.g., `all-or-nothing`, `anticipation`, or `baseline`).
- `subject`: Subject ID (e.g., `subject-001`).
- `movement`: Active DOF during these repetitions (e.g., `open-close` for hand open/close and `pro-sup` for wrist pronation/supination).

A `labels.txt` file is provided in each directory representing the ground truth shown to the participant. Each row represents a frame in an animation and each column represents a DOF - column 1 is hand open (+)/close (-) and column 2 is wrist pronation (-)/supination (+).

## Device Details

Data were collected using the HD-EMG EMaGer cuff from Université Laval. Device details are shown below:

- **Name:** EMaGer
- **Sampling frequency:** 1010 Hz
- **Channels:** 64

## Citation

If you are using this dataset in any publications, please cite <https://conferences.lib.unb.ca/index.php/mec/article/view/2507> for the dataset and <https://ieeexplore.ieee.org/document/10340612> for use of the EMaGer cuff.
