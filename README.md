# CDISeg
Official repository for our paper:

> **[Class-Domain Incremental Segmentation for Remote Sensing Images]**  
> Xingxing Weng, Chao Pang, Jiayu Li, Xiaoqian Sun, and Gui-Song Xia

---

## Overview

CDISeg is an incremental learning framework for remote sensing semantic segmentation that enables cross-domain knowledge accumulation. It allows models to progressively learn new classes from new domains while recognizing all learned classes across all encountered domains during inference. We term this incremental setting class-domain incremental learning.

<p align="center">
  <img src="incremental-setting.png" width="70%">
</p>

## Requirements

## Datasets

We use the [ISPRS](https://www.isprs.org/resources/datasets/benchmarks/UrbanSemLab/) dataset and [OpenEarthMap](https://www.isprs.org/resources/datasets/benchmarks/UrbanSemLab/) to simulate joint incremental learning across classes and domains.

Please download the images from the original datasets. We only provide the dataset splits used in our experiments. Required preprocessing steps:

1. **Image size normalization.** All images are resized or cropped to **512×512**.  
   - **ISPRS:** non-overlapping cropping is applied; overlap is used only when necessary to cover remaining regions.  
   - **OpenEarthMap:** images larger than 512 are non-overlappingly cropped, while smaller ones are directly resized to 512.

2. **Train/test split.** We follow the original dataset splits with minor adjustments:  
   - **ISPRS-Vaihingen:** due to limited training data, the validation set is merged into the training set.  
   - **OpenEarthMap:** since test labels are unavailable, the validation set is used for testing.

Organize the datasets as follows:

datasets/
├── ISPRS/{Annotations, Images, splits}

├── OpenEarthMap/{Annotations, Images, splits}

└── Potsdam/{Annotations, Images, splits}

## Training

## Citation

If you find this work useful, please consider citing:

```bibtex
@article{weng2025class,
  title={Class-Domain Incremental Segmentation for Remote Sensing Images},
  author={Weng, Xingxing and Pang, Chao and Li, Jiayu and Sun, Xiaoqian and Xia, Gui-Song},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  volume={64},
  pages={1--16},
  year={2025},
  publisher={IEEE}
}
```

## Acknowledgement
