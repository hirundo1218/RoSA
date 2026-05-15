# CHARM: CHannel-wise frequency-guided Augmentation for contrastive learning and Reconstruction in Multivariate time series anomaly detection

## Abstract

As the number of time series data used in many applications increases, multivariate time series anomaly detection has become more important. Due to the lack of labelled data, many existing methods employ unsupervised manner such as contrastive learning or reconstruction method to learn normal data patterns. However, these methods often fall short on capturing informative channel correlations relevant for anomaly detection. In this paper, we propose a novel framework that identifies informative channels using localized frequency analysis and simple statistics. These channels guide the generation of contrastive pairs, and the model is trained using a combination of contrastive learning and reconstruction to capture fine-grained channel structures. Specifically, we apply FFT to each channel over sliding windows and select those whose frequency amplitudes significantly deviate from their own average. We then apply inverse FFT augmentation to these channels to generate negative samples, and similarly augment the remaining channels to obtain positive samples for contrastive learning. Additionally, using the representation space learned from contrastive samples, we classify each window based on both its similarity to the nearest and farthest neighbors and its reconstruction error. Experiments on real-world datasets demonstrate that our model outperforms baselines.

## Model Architecture

![](./img/architecture.png)

## Get Started

1. Create a virtual environment:

```bash
python -m venv charm
source charm/bin/activate
```

2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Run (Example: MSL dataset):

```bash
python run.py
```

## Datasets

**Mars Science Laboratory (MSL)** ([source](https://www.kaggle.com/datasets/patrickfleith/nasa-anomaly-detection-dataset-smap-msl))

**Soil Moisture Active Passive (SMAP)** ([source](https://www.kaggle.com/datasets/patrickfleith/nasa-anomaly-detection-dataset-smap-msl))

**Server Machine Dataset (SMD)** ([source](https://github.com/NetManAIOps/OmniAnomaly/tree/master/ServerMachineDataset))

**Secure Water Treatment (SWaT)** ([source](https://itrust.sutd.edu.sg/testbeds/secure-water-treatment-swat/))

## Main Result

![](./img/result.png)