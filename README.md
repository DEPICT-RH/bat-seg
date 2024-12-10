# TotalSegmentator with Added Brown Adipose Tissue (BAT) Segmentation Task

This is a library forked from the original [TotalSegmentator software](https://github.com/wasserth/TotalSegmentator). This version includes an additional task for **Brown Adipose Tissue (BAT)** segmentation.

For questions, please contact **Kasper Jørgensen** at [kasper.joergensen.02@regionh.dk](mailto:kasper.joergensen.02@regionh.dk).

## Installation

Clone the repository and install it in your environment:

```bash
git clone https://github.com/Kasperjoergensen3/TotalSegmentator.git
pip install -e TotalSegmentator/
```

## Usage

For general usage of TotalSegmentator, refer to the [TotalSegmentator documentation](https://github.com/wasserth/TotalSegmentator).

To use our BAT segmentation model, run the command-line tool as follows:

```
TotalSegmentator -i path/to/input/ct.nii.gz \
                 -o path/to/output/bat.nii.gz \
                 -ta bat \
                 -ml
```

**Note:** The first time you use this command, the model weights will be automatically downloaded to your .totalsegmentator folder.

**Note:** By default, TotalSegmentator uses the model_final_checkpoint in the loaded weights folder. To use the best fold checkpoints from the 5-fold cross-validation (as done in our paper), manually overwrite the model_final_checkpoint files with the model_best_checkpoint files. These can be found in each fold folder within the hidden .totalsegmentator directory containing the datasets. For the BAT dataset, the corresponding dataset folder is Dataset901.
