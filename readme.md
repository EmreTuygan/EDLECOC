# EDL-ECOC: Uncertainty-Aware Skin Lesion Classification

Official implementation of **"Uncertainty-Aware Skin Lesion Classification with Evidential Error-Correcting Output Codes"**, accepted at **TIPTEKNO 2026**.

This repository contains the implementations used to evaluate Evidential Deep Learning (EDL), Error-Correcting Output Codes (ECOC), and their combination for uncertainty-aware multiclass skin lesion classification on the ISIC 2019 dataset.

## Method

EDL-ECOC combines Evidential Deep Learning with a sparse ternary ECOC decomposition. Each ECOC head performs an evidential binary classification task, while zero entries in the codebook identify classes outside the corresponding dichotomy. These out-of-dichotomy samples are used as an uncertainty regularization signal by encouraging low evidence for classes outside the head's assigned dichotomy.

The implementation uses an ImageNet-pretrained EfficientNetV2-M backbone and a 36-head ECOC codebook composed of 28 one-vs-one and 8 one-vs-rest dichotomies.

## Repository Structure

- `base.ipynb` — conventional multiclass baseline trained using focal loss.
- `ecoc.ipynb` — non-evidential ECOC baseline.
- `edl.ipynb` — multiclass Evidential Deep Learning baseline.
- `edl_ecoc.ipynb` — proposed EDL-ECOC model and its ablation without out-of-dichotomy regularization.

## Dataset

Experiments are conducted on the **ISIC 2019** dataset. The official test set additionally contains an unknown (`UNK`) category that is not represented during training and is used for out-of-distribution evaluation.

The ISIC 2019 dataset is not distributed with this repository. Please obtain the dataset from the official ISIC Challenge website and update the dataset paths in the notebooks accordingly.


## Reproducing the Experiments

Each notebook contains the complete training and evaluation pipeline for the corresponding model.

Before running a notebook:

1. Download the ISIC 2019 training and test images.
2. Configure the dataset paths in the notebook.
3. Run the notebook sequentially to train and evaluate the model.


## Citation

If you use this code in your research, please cite our paper:

The citation information will be updated with the official IEEE publication metadata once available.

## License

The source code in this repository is released under the MIT License. See `LICENSE` for details.

The ISIC 2019 dataset is distributed separately under its own licensing terms and is not covered by this repository's license.