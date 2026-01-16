

# ViTVS: Vision Transformer Segmentation for Visual Bird Sound Denoising
📄 **Paper**: [ViTVS](https://arxiv.org/abs/2406.09167)


## Overview

Audio denoising, particularly for **bird sound recordings**, remains a challenging task due to persistent residual noise and complex acoustic environments. Traditional signal-processing and deep learning approaches often struggle with **artificial noise, low-frequency interference, and long-range temporal dependencies**.

In this work, we propose **ViTVS**, a **Vision Transformer–based segmentation framework** for **visual bird sound denoising**. By transforming noisy audio signals into time–frequency representations and applying **vision transformer segmentation**, ViTVS effectively disentangles clean bird sounds from complex noise mixtures.

Our approach introduces **long-range attention**, **multi-scale representations**, and **segmentation-driven separation**, directly addressing the limitations of conventional CNN- and RNN-based methods.

Extensive experiments demonstrate that **ViTVS consistently outperforms state-of-the-art denoising models**, establishing a strong benchmark for real-world bird sound denoising applications.

---

## Key Contributions

* **ViTVS Architecture**: A novel Vision Transformer Segmentation model tailored for visual audio denoising.
* **Long-range Dependency Modeling**: Self-attention enables global context understanding across the spectrogram.
* **Multi-scale Feature Representation**: Effectively captures both fine-grained and coarse acoustic patterns.
* **Segmentation-based Denoising**: Clean sound regions are explicitly separated from noise via learned masks.
* **State-of-the-art Performance**: Superior denoising quality on real-world bird sound datasets.

---

## Model Architecture

### Vision Transformer Segmentation Network

<p align="center">
  <img src="./images2/ViT_encoder_decoder_4.jpg" width="100%">
</p>

**Architecture Overview**

* **Encoder**:

  * Patch creation and embedding layers
  * Stacked Vision Transformer encoder blocks
  * Each block applies normalization, multi-head self-attention, and feed-forward layers

* **Decoder**:

  * Symmetric transformer decoder blocks
  * Feature unfolding and projection layers
  * Outputs a **segmentation mask** identifying clean sound regions

Both the encoder and decoder consist of **12 transformer blocks**, enabling deep contextual modeling.

---

## Dataset

### BirdSoundsDenoising Dataset

The dataset used in this work is publicly available:

📌 **Dataset Link**:
[https://doi.org/10.5281/zenodo.7191406](https://doi.org/10.5281/zenodo.7191406)

### Directory Structure

```
Training/
Valid/
│
├── Raw_audios/
│   └── Noisy bird sound recordings
│
├── Images/
│   └── STFT spectrogram images of noisy audio
│
├── Masks/
│   └── Ground-truth segmentation masks for clean sound regions
│
└── Denoised_audios/
    └── Cleaned bird sound outputs
```

<p align="center">
  <img src="./images2/Sta.png" width="50%">
</p>

---

## Methodology

1. **Audio-to-Visual Transformation**

   * Raw noisy bird sounds are converted into STFT spectrogram images.

2. **Vision Transformer Segmentation**

   * ViTVS performs pixel-level segmentation to separate clean bird sound components from noise.

3. **Mask-guided Reconstruction**

   * The predicted segmentation mask is used to reconstruct denoised audio signals.

---

## Results

<p align="center">
  <img src="./images2/result_ViTVS_2.png" width="50%">
</p>

ViTVS demonstrates **significant improvements** over existing denoising approaches in terms of:

* Noise suppression
* Preservation of bird vocalization structure
* Reduction of artificial artifacts

---

## Applications

* Bioacoustics research
* Wildlife monitoring
* Bird species identification
* Environmental sound analysis
* Ecological conservation studies

---

## Citation

If you find this work useful in your research, please cite:

```bibtex
@misc{kumar2024visiontransformersegmentationvisual,
  title        = {Vision Transformer Segmentation for Visual Bird Sound Denoising},
  author       = {Sahil Kumar and Jialu Li and Youshan Zhang},
  year         = {2024},
  eprint       = {2406.09167},
  archivePrefix= {arXiv},
  primaryClass = {cs.SD},
  url          = {https://arxiv.org/abs/2406.09167}
}
```
