# Multi-Branch Network for Imagery Emotion Prediction

## Overview
This repository contains the implementation and details of the research paper titled "Multi-Branch Network for Imagery Emotion Prediction," accepted at the Emotion Recognition in Images Symposium 2023. The paper introduces an innovative approach utilizing the Multi-Branch Network (MBN) to predict both discrete emotional categories and Valence-Arousal-Dominance (VAD) values in images by incorporating facial expressions, body language, and scene context.

## Motivation
Images serve as powerful repositories of human emotions, yet previous methods predominantly focused on facial expressions, disregarding vital scene contexts that significantly influence emotion recognition accuracy. Additionally, while Valence-Arousal-Dominance (VAD) values offer a more nuanced understanding of continuous emotions, existing approaches lack emphasis on predicting them compared to discrete emotional categories.

## Key Contributions
- **Multi-Modal Information Fusion**: The MBN model integrates facial, body, and scene context information to enhance emotion prediction accuracy.
- **Comprehensive Emotion Prediction**: Simultaneous prediction of discrete emotional categories and VAD values for a holistic understanding of emotions in images.
- **State-of-the-Art Performance**: Experimental evaluation on the EMOTIC dataset demonstrates a substantial performance improvement, achieving 28.4% in mAP and 0.93 in MAE, surpassing existing methodologies.

## Implementation
The repository includes the complete implementation of the MBN model for imagery emotion prediction.

### Features
- **Multi-Branch Network Architecture**: Implementation of the proposed architecture for effective fusion of diverse contextual information.
- **Training and Evaluation Scripts**: Code for training the model on the EMOTIC dataset and evaluating performance metrics.
- **Datasets**: Access to a subset of the EMOTIC dataset for experimentation purposes.

### Requirements
- Python 3.x
- TensorFlow or PyTorch
- NumPy, Pandas, Matplotlib

### Installation
1. Clone the repository: `git clone https://github.com/username/MBN-Emotion-Prediction.git`
2. Install dependencies: `pip install -r requirements.txt`

## Experimentation and Results
The `results` directory contains trained models, evaluation metrics, and visualizations showcasing the performance enhancement achieved by the MBN model on the EMOTIC dataset. Jupyter notebooks for reproducing figures and tables from the paper are also included.

## Potential Applications
The findings of this paper underscore the significance of leveraging multiple contextual cues in emotion prediction tasks. The MBN model demonstrates potential applications in various domains, including affective computing, human-computer interaction, social robotics, and beyond.

## Citation
If you find this paper or associated code useful, kindly consider citing our work:
@inproceedings{author2023multi-branch,
title={Multi-Branch Network for Imagery Emotion Prediction},
author={Author A, Author B, Author C},
booktitle={Emotion Recognition in Images Symposium},
year={2023}
}

For inquiries or further information, please reach out to [email@example.com](mailto:email@example.com).

