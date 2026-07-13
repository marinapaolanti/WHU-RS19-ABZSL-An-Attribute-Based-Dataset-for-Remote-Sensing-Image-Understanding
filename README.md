# WHU-RS19 ABZSL

**An Attribute-Based Dataset for Remote Sensing Image Understanding**

[![Paper](https://img.shields.io/badge/Paper-Remote%20Sensing%202025-8B4A2E)](https://doi.org/10.3390/rs17142384)
[![DOI](https://img.shields.io/badge/DOI-10.3390%2Frs17142384-2B565C)](https://doi.org/10.3390/rs17142384)
[![License](https://img.shields.io/badge/License-CC%20BY%204.0-52632F)](https://creativecommons.org/licenses/by/4.0/)

Balestra, M., Paolanti, M., & Pierdicca, R. (2025). *WHU-RS19 ABZSL: An attribute-based dataset for remote sensing image understanding.* Remote Sensing, 17(14), 2384.

---

## Overview

WHU-RS19 ABZSL extends the classic **WHU-RS19** aerial-scene benchmark (1,005 images, 19 scene categories) with a dense, expert-annotated, image-level vector of **38 binary attributes** covering objects, geometric patterns, and dominant colours. Unlike class-level attribute datasets (e.g. AwA2, SUN), annotation happens per image, so intra-class variability is preserved — two "Port" images can share very different attribute profiles.

The dataset supports multi-label classification, explainable AI (XAI), semantic retrieval, and attribute-based zero-shot learning (ZSL).

A polished project page with the full breakdown (taxonomy, benchmarks, splits) is in [`index.html`](./index.html).

## Dataset at a glance

| | |
|---|---|
| Images | 1,005 (600 × 600 px, from Google Earth) |
| Scene categories | 19 |
| Attributes | 38 → **19** objects · **11** dominant colours · **8** geometric patterns |
| Annotators | 6 domain experts + supervisor + final expert review (3-stage QA) |
| Split | 70 / 30 stratified train/test (702 / 303 images) |

## Baseline results (multi-label attribute classification)

| Model | Input size | Macro F1-score |
|---|---|---|
| ResNet-18 | 224×224 | 0.7385 |
| VGG-16 | 224×224 | 0.7458 |
| InceptionV3 | 299×299 | 0.7465 |
| ViT-B/16 | 224×224 | 0.7594 |
| **EfficientNet-B0** | 224×224 | **0.7608** |

All backbones are ImageNet-pretrained and fine-tuned for 50 epochs (Adam, lr 1×10⁻⁴, batch size 32, BCE loss, sigmoid output). Common attributes (Soil, Gray, Trees) reach F1 ≈ 0.95–0.98; rare or visually ambiguous ones (Ochre, Triangle, Orange) remain the main failure mode across every model. Full per-attribute precision/recall/F1 tables and confusion matrices are reported in the paper.

## Getting the data

The dataset is **gated** and distributed on request:

1. Email the corresponding author with a short description of your intended use.
2. You'll receive a data-use agreement to complete and sign.
3. Return the signed form — download credentials are sent back by email.

📧 **Always contact Marina Paolanti for dataset requests and inquiries: [marina.paolanti@unimc.it](mailto:marina.paolanti@unimc.it)**

## Citation

```bibtex
@article{balestra2025whurs19abzsl,
  title   = {WHU-RS19 ABZSL: An Attribute-Based Dataset for Remote Sensing Image Understanding},
  author  = {Balestra, Mattia and Paolanti, Marina and Pierdicca, Roberto},
  journal = {Remote Sensing},
  volume  = {17},
  number  = {14},
  pages   = {2384},
  year    = {2025},
  publisher = {MDPI},
  doi     = {10.3390/rs17142384}
}
```

## Authors

| | Affiliation | Email |
|---|---|---|
| Mattia Balestra | D3A, Università Politecnica delle Marche | m.balestra@staff.univpm.it |
| **Marina Paolanti** *(corresponding author)* | Dept. of Political Sciences, Communication and International Relations, University of Macerata | marina.paolanti@unimc.it |
| Roberto Pierdicca | DICEA, Università Politecnica delle Marche | r.pierdicca@staff.univpm.it |

## License

Article and metadata are distributed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Dataset access is subject to the data-use agreement described above.
