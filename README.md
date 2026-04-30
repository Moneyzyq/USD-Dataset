# USD: Underwater Structure Defect Dataset with Suspended Impurities

## Overview

The **USD dataset** is designed for underwater structure surface defect detection under suspended-impurity interference. It provides videos, images, impurity masks, defect annotations, and E-procedure processed results for evaluating underwater structure defect detection methods in both synthetic and real-world underwater environments.

The dataset is divided into four subsets:

- **USD-SSI**: Synthetic Suspended Impurities
- **USD-RSI**: Real Suspended Impurities
- **USD-VDO**: Underwater Structure Defect Dataset without Suspended Impurities
- **USD-VDW**: Underwater Structure Defect Dataset with Suspended Impurities

The USD dataset supports the evaluation of impurity localization, underwater structure defect detection, and the complete E-D cascaded framework.

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

Unlike USD-SSI, the suspended impurities in USD-RSI are naturally present during data acquisition. Therefore, this subset provides a more realistic benchmark for evaluating detection algorithms under complex underwater conditions.

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
├── USD-SSI/
│   ├── original_videos/
│   ├── impurity_videos/
│   ├── impurity_masks/
│   └── defect_annotations/
│
├── USD-RSI/
│   ├── videos/
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
└── 
