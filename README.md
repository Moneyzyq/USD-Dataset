# USD: Underwater Structure Defect Dataset with Suspended Impurities

## Overview

The **USD dataset** is designed for underwater structure surface defect detection under suspended-impurity interference. It provides videos, images, impurity masks, defect annotations, and E-procedure processed results for evaluating underwater structure defect detection methods in both synthetic and real-world underwater environments.

The dataset is divided into four subsets:

- **USD-SSI**: Synthetic Suspended Impurities
- **USD-RSI**: Real Suspended Impurities
- **USD-VDO**: Underwater Structure Defect Dataset without Suspended Impurities
- **USD-VDW**: Underwater Structure Defect Dataset with Suspended Impurities

The USD dataset supports the evaluation of suspended impurity localization, underwater structure defect detection, and the complete E-D cascaded framework.

---

## Dataset Composition

| Subset | Full Name | Data Type | Quantity | Description | Main Purpose |
|---|---|---:|---:|---|---|
| USD-SSI | Synthetic Suspended Impurities | Videos | 16 video sets | Underwater structure videos with synthetically generated suspended impurities. Corresponding impurity mask videos and manually labeled defect annotations are provided. | Evaluation of impurity localization and defect detection under synthetic suspended-impurity interference |
| USD-RSI | Real Suspended Impurities | Videos | 14 video sets | Real-world underwater structural videos containing naturally occurring suspended impurities. | Benchmarking detection algorithms under realistic underwater impurity interference |
| USD-VDO | Underwater Structure Defect Dataset without Suspended Impurities | Images | 541 images | Annotated underwater structure defect images without suspended impurities. | Evaluation of underwater structure defect detection without impurity interference |
| USD-VDW | Underwater Structure Defect Dataset with Suspended Impurities | Frame sets | 70 frame sets | Frame sets randomly selected from USD-RSI, including E-procedure processed results and manually labeled defect ground truth. | Evaluation of the complete E-D cascaded framework |

---

## Subset Description

### 1. USD-SSI: Synthetic Suspended Impurities

**USD-SSI** contains videos of underwater structures with synthetically generated suspended impurities.

Impurity samples with diverse sizes, shapes, and colors were extracted from real underwater footage and inserted into 16 sets of original underwater structural videos using a custom random motion generation program. The program simulates different motion trajectories, directions, and movement patterns to approximate the behavior of suspended impurities observed in natural underwater environments.

For this subset, corresponding mask videos are retained to evaluate impurity localization accuracy. In addition, ground truth annotations of surface defects are manually labeled to assess the performance of the D-procedure.

This subset is mainly used for:

- Suspended impurity localization
- Robust underwater structure defect detection under synthetic interference
- Evaluation of the D-procedure after impurity simulation

---

### 2. USD-RSI: Real Suspended Impurities

**USD-RSI** comprises 14 sets of underwater structural videos captured in real-world underwater environments containing naturally occurring suspended impurities.

Unlike USD-SSI, the suspended impurities in USD-RSI are naturally present during data acquisition. Therefore, this subset provides a realistic benchmark for evaluating detection algorithms under complex underwater conditions.

This subset is mainly used for:

- Real-world suspended-impurity interference analysis
- Robustness evaluation of underwater structure defect detection methods
- Source data selection for USD-VDW

---

### 3. USD-VDO: Underwater Structure Defect Dataset without Suspended Impurities

**USD-VDO** is an annotated underwater structure defect dataset comprising 541 images of underwater structures without suspended impurities.

Each image is manually annotated with ground truth labels of surface defects. Since this subset does not contain suspended-impurity interference, it can be used to evaluate the basic defect detection ability of different methods under relatively clean underwater conditions.

This subset is mainly used for:

- Underwater structure defect detection
- Defect segmentation
- Evaluation of D-procedure performance without impurity interference

---

### 4. USD-VDW: Underwater Structure Defect Dataset with Suspended Impurities

**USD-VDW** consists of 70 frame sets randomly selected from USD-RSI.

This subset contains corresponding E-procedure processed results and manually labeled defect ground truth. It is suitable for evaluating the effectiveness of the complete E-D cascaded framework, where the E-procedure is used to mitigate suspended-impurity interference and the D-procedure is used for surface defect detection.

This subset is mainly used for:

- Evaluation of the complete E-D cascaded framework
- Defect detection under real suspended-impurity interference
- Comparison between original frames and E-procedure enhanced results

---

## Dataset Structure

The recommended directory structure of the dataset is as follows:

```text
USD/
├── README_DATASET.md
├── USD-SSI/
│   ├── original_videos/
│   ├── impurity_videos/
│   ├── impurity_masks/
│   └── defect_annotations/
│
├── USD-RSI/
│   ├── videos/
│   └── metadata.csv
│
├── USD-VDO/
│   ├── images/
│   ├── defect_masks/
│   └── annotations/
│
├── USD-VDW/
│   ├── original_frames/
│   ├── e_procedure_results/
│   ├── defect_annotations/
│   └── metadata.csv
│
├── file_list.csv
├── train_val_test_split.csv
└── SHA256SUMS.txt
```

---

## Annotation Format

The dataset provides manually labeled ground truth annotations for underwater structure surface defects.

The default annotation format is binary mask format:

- Pixel value `0`: background
- Pixel value `255`: defect region

For video-based subsets, masks and annotations are aligned with the corresponding video frames by frame index.

If polygon, COCO, YOLO, or other annotation formats are used in your version of the dataset, please refer to:

```text
annotations/annotation_format.md
```

---

## Download

The complete USD dataset is available at Zenodo:

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19914976.svg)](https://doi.org/10.5281/zenodo.19914976)

- **Zenodo DOI**: `10.5281/zenodo.19914976`
- **GitHub Repository**: `https://github.com/your-username/USD-Dataset`

Please replace the placeholder GitHub URL with the final public repository link after publication.

---

## Recommended Evaluation Tasks

The USD dataset can be used for the following research tasks:

1. **Suspended impurity localization**  
   USD-SSI provides synthetic suspended-impurity videos and corresponding impurity masks for evaluating impurity localization accuracy.

2. **Underwater structure defect detection without suspended impurities**  
   USD-VDO can be used to evaluate defect detection methods under relatively clean underwater conditions.

3. **Underwater structure defect detection with synthetic suspended impurities**  
   USD-SSI can be used to evaluate the robustness of defect detection methods under synthetic impurity interference.

4. **Underwater structure defect detection with real suspended impurities**  
   USD-RSI and USD-VDW can be used to evaluate detection algorithms under real underwater environments containing naturally occurring suspended impurities.

5. **Evaluation of the complete E-D cascaded framework**  
   USD-VDW can be used to evaluate the complete E-D framework, including suspended-impurity mitigation and defect detection.

---

## Citation

If you use this dataset in your research, please cite the associated paper and this dataset.

```bibtex
@dataset{usd_dataset_2026,
  title        = {USD: Underwater Structure Defect Dataset with Suspended Impurities},
  author       = {Author One and Author Two and Author Three},
  year         = {2026},
  version      = {1.0},
  publisher    = {Zenodo},
  url          = {https://github.com/your-username/USD-Dataset},
  doi          = {10.5281/zenodo.19914976}
}
```

If the dataset is associated with a paper, please also cite:

```bibtex
@article{your_paper_2026,
  title   = {Your Paper Title},
  author  = {Author One and Author Two and Author Three},
  journal = {Journal Name},
  year    = {2026}
}
```

---

## License

This dataset is released for academic research purposes.

Recommended license:

```text
Creative Commons Attribution-NonCommercial 4.0 International License
CC BY-NC 4.0
```

Users are allowed to use, share, and adapt the dataset for non-commercial research purposes, provided that proper credit is given to the authors.

Commercial use is not permitted without prior permission from the authors.

For more details, please refer to the `LICENSE` file.

---

## Terms of Use

By downloading or using the USD dataset, users agree to the following terms:

1. The dataset may only be used for academic research and educational purposes.
2. The dataset may not be used for commercial purposes without permission.
3. The dataset may not be redistributed without proper citation and permission.
4. Users must cite the associated paper and this dataset when using it in publications.
5. The authors are not responsible for any misuse of the dataset.

---

## Contact

For questions about the USD dataset, please contact:

```text
Name: Your Name
Email: your_email@example.com
Institution: Your Institution
```

You are also welcome to open an issue in this repository.

---

## Acknowledgements

We thank all contributors involved in underwater data collection, impurity sample extraction, annotation, and dataset organization.

This dataset is intended to support research on underwater structure defect detection, underwater image understanding, and robust visual perception in complex underwater environments.

---

## Updates

| Date | Version | Description |
|---|---|---|
| 2026-04-30 | v1.0 | Initial release of the USD dataset |

