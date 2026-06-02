# RIML-firsttask-sobhan
# Zero-Shot Anomaly Detection on CAMELYON16 using Ano-NAViLa

## Overview

This repository contains an end-to-end inference pipeline for applying the Ano-NAViLa framework to a Whole Slide Image (WSI) from the CAMELYON16 dataset.

The pipeline performs:

1. Tissue segmentation to remove background regions.
2. Patch extraction from the WSI.
3. Zero-shot anomaly detection using the pre-trained Ano-NAViLa model.
4. Patch-level anomaly scoring.
5. Heatmap generation and visualization of suspicious regions.

## Requirements

* Python 3.10+
* PyTorch
* OpenSlide
* CONCH repository
* Ano-NAViLa repository
* Pretrained CONCH checkpoint (`pytorch_model.bin`)
* Pretrained Ano-NAViLa weights (`re-trained_AnoNAViLa_Model.pth`)

## Dataset

This project was tested on a CAMELYON16 Whole Slide Image (`test_001.tif`).

CAMELYON16 WSIs can be downloaded from the official challenge dataset.

## Outputs

The pipeline generates:

* Patch-level anomaly scores (`test_001_Ascores.csv`)
* Global anomaly heatmap (`test_001_anomaly_heatmap_overlay.png`)
* Visualization of top anomalous patch locations (`test_001_top20_locations.png`)

## Notes

The model is used in a zero-shot setting without any additional training or fine-tuning. The generated anomaly scores indicate regions that deviate from the learned normal pathology distribution and should not be interpreted as definitive tumor predictions.
