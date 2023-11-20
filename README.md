# Multi-Branch Network for Contextual Emotion Prediction in Images

## Overview
This repository encompasses the proposed Multi-Branch Network (MBN) detailed in the research paper presented at the Symposium on Information and Communication Technology (SoICT) 2023. The MBN architecture aims to predict emotions in images by leveraging contextual information from body, face, and scene context, merging the predictions into discrete emotions and Valence-Arousal-Dominance (VAD) values.

## Architecture Overview
The MBN architecture consists of two primary sections: Feature Extraction Branches and a Fusion Network. The Feature Extraction Branches extract crucial information from body, face, and scene context, while the Fusion Network combines these features for emotion prediction.

### Feature Extraction Branches
#### Body Feature Extraction Branch
- Utilizes ResNet-18, ResNet-50, and SwinT architectures with ImageNet pre-trained weights to extract features from body images.
- Retrained models on the EMOTIC dataset show promising results, achieving an mAP score above 0.33 for gender and age range prediction.

#### Context Feature Extraction Branch
- Employs ResNet-18 and ResNet-50 with Places365 pre-trained weights for scene context feature extraction.

#### Face Feature Extraction Branch
- Leverages pre-trained models from FER-2013 dataset by Shangeth and Balmukund for facial expression recognition.

#### Face Extraction and Enhancement
- Detects faces within body images and performs cropping and resizing.
- Improves face image quality via denoising and sharpening using OpenCV's filter2D function.

### Fusion Network
- Adapts the fusion network architecture from previous work.
- Utilizes two fully-connected layers to predict discrete emotions and VAD values from the extracted features.

#### Connection with Predecessor Models
- Reconstructs models' connections by creating sequential networks of layers, except for the last layer.
- Connects the output of the three branches to construct the fusion network's input.

## Experimentation and Results
The proposed MBN architecture demonstrates its effectiveness on the EMOTIC dataset, surpassing state-of-the-art methods with mAP of 0.2837 and MAE of 0.9256. The fusion of contextual information enhances both discrete and continuous emotion prediction.

## Contributions
- Introduction of an innovative MBN architecture leveraging body, face, and scene context for emotion prediction.
- Experimental validation showcasing the MBN's superior performance over existing methodologies.

For detailed code implementation and experimentation, please refer to the associated codebase.

## Citation


Let's continue building the README.md based on the information provided in the paper's proposed method:

markdown
Copy code
# Proposed Method: Multi-Branch Network (MBN)

## Overview
This repository encompasses the proposed Multi-Branch Network (MBN) detailed in the research paper presented at the Symposium on Information and Communication Technology (SoICT) 2023. The MBN architecture aims to predict emotions in images by leveraging contextual information from body, face, and scene context, merging the predictions into discrete emotions and Valence-Arousal-Dominance (VAD) values.

## Architecture Overview
The MBN architecture consists of two primary sections: Feature Extraction Branches and a Fusion Network. The Feature Extraction Branches extract crucial information from body, face, and scene context, while the Fusion Network combines these features for emotion prediction.

### Feature Extraction Branches
#### Body Feature Extraction Branch
- Utilizes ResNet-18, ResNet-50, and SwinT architectures with ImageNet pre-trained weights to extract features from body images.
- Retrained models on the EMOTIC dataset show promising results, achieving an mAP score above 0.33 for gender and age range prediction.

#### Context Feature Extraction Branch
- Employs ResNet-18 and ResNet-50 with Places365 pre-trained weights for scene context feature extraction.

#### Face Feature Extraction Branch
- Leverages pre-trained models from FER-2013 dataset by Shangeth and Balmukund for facial expression recognition.

#### Face Extraction and Enhancement
- Detects faces within body images and performs cropping and resizing.
- Improves face image quality via denoising and sharpening using OpenCV's filter2D function.

### Fusion Network
- Adapts the fusion network architecture from previous work.
- Utilizes two fully-connected layers to predict discrete emotions and VAD values from the extracted features.

#### Connection with Predecessor Models
- Reconstructs models' connections by creating sequential networks of layers, except for the last layer.
- Connects the output of the three branches to construct the fusion network's input.

## Experimentation and Results
The proposed MBN architecture demonstrates its effectiveness on the EMOTIC dataset, surpassing state-of-the-art methods with mAP of 0.2837 and MAE of 0.9256. The fusion of contextual information enhances both discrete and continuous emotion prediction.

## Contributions
- Introduction of an innovative MBN architecture leveraging body, face, and scene context for emotion prediction.
- Experimental validation showcasing the MBN's superior performance over existing methodologies.

For detailed code implementation and experimentation, please refer to the associated codebase.

## Citation
If you find this paper or associated code beneficial, please cite our work:
@inproceedings{author2023multi-branch,
title={Proposed Multi-Branch Network for Emotion Prediction in Images},
author={Author A, Author B, Author C},
booktitle={Symposium on Information and Communication Technology},
year={2023}
}


For inquiries or further information, please contact [email@example.com](mailto:email@example.com).
