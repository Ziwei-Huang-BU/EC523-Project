# EC523-Project
EC523 class project


## Task Description
In this project, we are trying to generate COVID-19 diagnosis results: based on patients’ unlabeled CT scan images, using self-supervised learning (Self-Trans) approach. Considering the less data-rich source on COVID related CT scans, the difficulty of this project will be building a highly efficient deep learning model, pretraining and fine tuning our network in our medical/diagnostic task. Besides reproducing the results as described in the [literature](https://www.medrxiv.org/content/10.1101/2020.04.13.20063941v1), we will train alternative pretrained models as inputs of Self-Trans algorithm with Momentum Contrast (MOCO) unsupervised learning method, using “Cats vs Dogs” and “Breast Histopathology Images” datasets from [Kaggle](https://www.kaggle.com/). 


## Datasets Description

### Main

1. **COVID19-CT**: 425 CT preprocessed 224*224 pixel size CT sliced images with binary class labels: “COVID” and “Non-COVID”. [link](https://github.com/UCSD-AI4H/COVID-CT/tree/master/Images-processed)

### Alternative

1. **"Cats vs. Dogs"** [link](https://www.kaggle.com/competitions/dogs-vs-cats/overview)

2. **"Breast Histopathology Images"** [link](https://www.kaggle.com/code/paultimothymooney/predict-idc-in-breast-cancer-histology-images/notebook)

### Data Training and Testing

By now, we use DenseNet169 as model backbone to implement the self-transfer learning (Self-Trans) with Moco. 

In the Self-Trans process: 

**Densenet169 pretrained model** the pretrained DenseNet169 through ImageNet is imported directly. 

**pretraining by moco:** 
1. train the LUNA breast CT training data 
2. train the COVID-CT data 

**final training, final tuning, and testing**: [Self_Trans_Final_Training.ipynb](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/Self_Trans_Final_Training.ipynb)

## Resources
[Github Facebookresearch MOCO](https://github.com/facebookresearch/moco)

[UCSD COVID-CT](https://github.com/UCSD-AI4H/COVID-CT)





