# MambaFF

> **Release status**
>
> The code and WLRS dataset are currently being prepared for public release. Neither is publicly available at this stage. The implementation, dataset access links, and usage instructions will be added to this repository once preparation is complete.

Official project repository for the paper:

## Beyond Spatial Scanning: Rethinking the Fine-tuning of Mamba-based Remote Sensing Foundation Models

**Authors:** Yumeng Wang, Junjie Wang, Boyu Zhao, Yuanyuan Gui, and Anzhi Yue

This repository currently serves as the project introduction and release entry point for **MambaFF** and the **Woodland Remote Sensing Dataset (WLRS)**. It does not yet contain implementation code, model weights, dataset files, or a paper PDF.

## Overview

MambaFF is a frequency-guided parameter-efficient fine-tuning framework for adapting Mamba-based remote sensing foundation models to downstream tasks. It is motivated by two limitations observed during adaptation:

1. **Spatial scanning limitation.** Sequential one-dimensional scanning provides only limited directional traversal of two-dimensional imagery and can weaken globally coherent spatial references.
2. **Frequency-biased optimization.** Low-frequency backgrounds dominate feature energy and gradient updates, while high-frequency structures such as small objects, boundaries, and textures receive insufficient adaptation.

MambaFF addresses these limitations with two complementary components:

- **Dual-Branch Visual Prompt (DBV-Prompt):** introduces spatial-domain and frequency-domain prompts before state-space recurrence. The spatial branch preserves positional and contextual cues, while the Hartley-domain frequency branch provides direction-independent global information and helps retain high-frequency details.
- **Frequency-Difference Routing Expert (FDR-Expert):** uses the difference between the original representation and its low-frequency projection as a difficulty-aware routing signal. Lightweight experts focus adaptation capacity on high-frequency and semantically complex regions while avoiding redundant updates in smooth, well-modeled regions.

The framework is designed for both layer-based and stage-based Mamba architectures. The paper evaluates it on five remote sensing tasks: object detection, scene classification, building extraction, change detection, and multi-label semantic segmentation.

## WLRS Dataset

**WLRS (Woodland Remote Sensing Dataset)** is a large-scale, geographically diverse multi-label semantic segmentation dataset constructed from GF-6 satellite imagery. It is designed to evaluate fine-grained remote sensing understanding in scenes with complex spatial mixtures and frequent coexistence of land-cover categories.

### Dataset statistics

| Item | Value |
| --- | --- |
| Task | Multi-label semantic segmentation |
| Source imagery | GF-6 satellite imagery |
| Geographic coverage | Ten representative regions across China |
| Covered area | More than 251,000 km² |
| Image-label pairs | 18,494 |
| Training pairs | 14,792 |
| Test pairs | 3,702 |
| Annotated pixels | Approximately 4.8 billion |
| Land-cover classes | 7 |

The seven land-cover classes are:

1. Wetland
2. Cultivated Land
3. Plantation Land
4. Forests
5. Grassland
6. Roads and Buildings
7. Water and Resources

### Geographic diversity

WLRS covers Shanghai, Chongqing, Benxi, Chengde, Fangchenggang, Genhe, Huangshan, Puer, Tianshui, and Yichang. These regions span mid-temperature semi-humid, warm-temperature semi-humid, marginal tropical humid, and northern subtropical humid climate zones.

### Annotation source and quality control

The annotations are derived from a large-scale woodland survey by the National Forestry and Grassland Administration. Domain experts performed professional interpretation and delineation following standardized forestry surveying protocols. The annotation workflow included multi-stage technical verification, manual inspection, boundary refinement, and consistency correction.

## Availability

| Resource | Current status |
| --- | --- |
| MambaFF implementation | In preparation; not publicly available |
| Training and evaluation instructions | In preparation; not publicly available |
| Model weights | Not publicly available |
| WLRS dataset | In preparation; not publicly available |
| Dataset access instructions | In preparation; not publicly available |
| Project documentation | This README is available |

Please do not assume that any third-party file or similarly named dataset is an official MambaFF or WLRS release. Official resources will be linked from this repository when they are ready.

## Planned Release Contents

The repository is planned to be expanded with the following materials after preparation and validation are complete:

- MambaFF implementation and environment requirements
- Training and evaluation configurations for the supported downstream tasks
- Reproducible usage and evaluation instructions
- WLRS access instructions, dataset documentation, label definitions, and official split information
- Model checkpoints and additional reproducibility artifacts where validation and redistribution permissions allow
- Citation metadata when a citable public version of the paper becomes available

No specific release date is announced at this stage.

## Citation

Formal citation information will be added when a citable public version of the paper becomes available. No DOI or publication status is claimed by this repository at present.

## Contact

For questions about the project, please contact the corresponding author:

**Junjie Wang**<br>
School of Information and Electronics, Beijing Institute of Technology<br>
Aerospace and Informatics Domain, Beijing Institute of Technology<br>
Email: [junjiewang@bit.edu.cn](mailto:junjiewang@bit.edu.cn)

## License

Licensing and terms of use for the code, model artifacts, and WLRS dataset will be provided with their respective public releases. No unreleased resource is made available under an implied license by this project-introduction README.
