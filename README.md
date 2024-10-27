# Multi-Branch Network for Contextual Emotion Prediction in Images

[[`ArXiv Paper`](https://arxiv.org/abs/2312.07500)]

## Overview
This repository hosts the official PyTorch implementation of the Multi-Branch Network (MBN) as presented in the 2023 Symposium on Information and Communication Technology (SoICT). The MBN architecture is designed to discern emotions within images by leveraging combined data from body, face, and scene contexts. Our model excels at predicting emotions across both discrete and continuous scales. In rigorous experiments conducted on the EMOTIC dataset, which comprises extensive images of individuals in diverse, unstructured scenarios annotated with 26 discrete emotion categories and VAD (Valence-Arousal-Dominance) values, our proposed method demonstrates significant superiority over state-of-the-art approaches, achieving 28.4% in mean average precision (mAP) and 0.93 in mean absolute error (MAE).

![Result](https://github.com/BaoNinh2808/Multi-Branch-Network-for-Imagery-Emotion-Prediction/blob/main/images/result.png)

## Dataset
We use EMOTIC dataset in our experienment. EMOTIC dataset has supplied us the ***body image*** and ***context image***, but not supplied ***face image*** yet. So we must extract ***face image*** from ***body image*** of EMOTIC dataset and use some processing method to enhance their quality.We have present the way we extract and enhance ***face image*** quality in my paper, you can use it as a hint for extracting ***face image*** to use in your trainning and testing. 

And of course, I will give you ***face image*** that we have extracted and used. We put it in `face-dataset` folder, you can download it [Face Image Dataset](./face-dataset/)

About EMOTIC Dataset, we appologize for not able to give you it directly. The Emotic dataset can be used only for non-commercial research and education purposes. Please, fill out the following form to request access to the dataset and the corresponding annotations.
[Access Request for EMOTIC](https://docs.google.com/forms/d/e/1FAIpQLScXwxhEZu7RpHwgiRqVfb09GzHSSyIm64hJQMgHSLm75ltsFQ/viewform) 

### Preprocessing Dataset (IMPORTANT) 
You must preprocessing Dataset before using it in our code for trainning and testing model.

After download the Emotic dataset & annotations, preparing the directory following the below structure:
```plaintext
├── ...
│   ├── emotic
│   |    ├── ade20k
│   |    ├── emodb_small
│   |    ├── framesdb
│   |    ├── mscoco 
│   ├── Annotations
│   |    ├── Annotations.mat
```

Then, you need to convert annotations from mat object to csv files and preprocess the data:
```plaintext
> python mat2py.py --data_dir proj/data/emotic19 --generate_npy
```
* data_dir: Path of the directory containing the emotic and annotations folder as described in the above data directory structure.
* generate_npy: Argument to specify to generate npy files (later used for training and testing) along with CSV files. If not passed only CSV files are generated.

Finally, combination with our ***face image*** you can download from my github [face-dataset](./face-dataset/), you already have the complete dataset to use in our [notebook](./notebook/). [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/BaoNinh2808/Multi-Branch-Network-for-Imagery-Emotion-Prediction/notebook/Multi_Branch_Network_for_Imagery_Emotion_Prediction.ipynb)


## Architecture Overview
The behind image shows the architecture of our proposed Multi-Branch Network (MBN). The network is divided into two main parts. The first part extracts features from the body, the face, and context of the image, referred to as body image, face image, and context image. It consists of three branches to exploit emotions from subjects and background. We remark that the face region is extracted from the body image. The second part is a fusion network combining the features extracted from the three branches to predict the discrete emotions and VAD values of each person in the image.
![Architecture of our proposed Multi-Branch Network (MBN) for image emotion prediction](https://github.com/BaoNinh2808/Multi-Branch-Network-for-Imagery-Emotion-Prediction/blob/main/images/Proposed%20method.jpg)

Our proposed network consists of three feature extraction branches, utilizing different deep learning models trained on suitable datasets to efficiently make predictions on human and scene images.

You can see the picture to know about what backbone you can choose.

![backbones](https://github.com/BaoNinh2808/Multi-Branch-Network-for-Imagery-Emotion-Prediction/blob/main/images/model_options.png)

## Experiment Result
The proposed MBN architecture demonstrates its effectiveness on the EMOTIC dataset, surpassing state-of-the-art methods with mAP of 0.2837 and MAE of 0.9256. The fusion of contextual information enhances both discrete and continuous emotion prediction.

The table below show the experiment result on EMOTIC dataset using the combination of 3 feature extraction branches with different backbones.

![experiment result](https://github.com/BaoNinh2808/Multi-Branch-Network-for-Imagery-Emotion-Prediction/blob/main/images/experiment%20result.png)

We see that, using powerful backbone result in the better result. The Swin Transformer backbone performed best with a mAP of 0.2837 and a MAE of 0.9256. But the trade off is more time for training because of its large size.

## Contributions
- We present an effective method for human emotion prediction from images. Our method integrates information extracted from various sources, including person’s face and body, and scene context. The combination of facial features and attention to scene contexts helps improve the perfor mance of both discrete and continuous emotion prediction.
- We provide extensive experiments and analysis on emotion prediction using the continuous VAD scale, which can serve as a baseline for future studies. Experimental results con tribute to the limited existing research on emotion recognition models using the continuous VAD scale.

For detailed code implementation and experimentation, please refer to the associated codebase ![ipynb file](https://github.com/BaoNinh2808/Multi-Branch-Network-for-Imagery-Emotion-Prediction/blob/main/src/Multi-Branch%20Network%20for%20Imagery%20Emotion%20Prediction.ipynb).

## Citation
If you find this paper or associated code beneficial, please cite our work:

```bibtex
@inproceedings{author2023multi-branch,
title={Multi-Branch Network for Imagery Emotion Prediction},
author={Quoc-Bao Ninh, Hai-Chan Nguyen, Triet Huynh, Trung-Nghia Le},
booktitle={Symposium on Information and Communication Technology},
year={2023}
}
```

## ACKNOWLEDGMENTS

This research is supported by research funding from Faculty of Information Technology, University of Science, Vietnam National University - Ho Chi Minh City. We would like to express our gratitude to Dr. Minh-Triet Tran for his valuable suggestions and support that greatly contributed to the completion of this research.

For inquiries or further information, please contact [mail](mailto:ltnghia@fit.hcmus.edu.vn).

## LICENSE
This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/). The use of this code is for academic purposes only.
