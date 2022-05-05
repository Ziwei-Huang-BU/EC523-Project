# EC523-Project: Leverage a Contrastive Self-Supervised Learning Framework: MoCo on Medical Images
Yihong Xu, Ziwei Huang, Qingyang Xu, Shuqiang Chen 

![alt text](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/readme_figs/pipeline.png)


## Task Description
The goal of this project is to implement a contrastive self-supervised learning framework: Momentum Contrastive Learning (MoCo) [1] on unlabeled images to boost the performance of the supervised learning on binary pathological classification task: 1. COVID positive (“1”) and negative (“0”) results from COVID-19 lung CT scan. 2. Breast Cancer IDC positive (“1”) and negative (“0”) from Breast Cancer Histology tissue microscopy images. 

The backbone network is chosen to be ResNet-18. We compare the different final performance of the model without MoCo pretraining and with different rounds of MoCo pertaining steps. 

## Datasets Description

1. **Cifar-10**: 

2. **LUNA-CT**: 

3. **COVID19-CT**: 425 CT preprocessed 224*224 pixel size CT sliced images with binary class labels: “COVID” and “Non-COVID”. [link](https://github.com/UCSD-AI4H/COVID-CT/tree/master/Images-processed)

4. **"Breast Histopathology Images"** [link](https://www.kaggle.com/code/paultimothymooney/predict-idc-in-breast-cancer-histology-images/notebook)


## Data Training and Testing

By now, we use Resnet-18 as model backbone to implement the self-transfer learning (Self-Trans) with Moco. 

In the Self-Trans process: 

**Resnet-18 model** the random initialized Resnet-18 is imported

**pretraining through moco:** 

***1. COVID-19*** 
[moco_COVID.ipynb](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/moco_pretrain/moco_COVID.ipynb)
1. pretrain with Cifar-10 unlabeled dataset
2. pretrain with LUNA breast CT training dataset
3. pretrain with the unlabeled COVID-CT dataset

***2. IDC Breast Cancer*** 
[moco_IDC.ipynb](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/moco_pretrain/moco_IDC.ipynb)
1. pretrain with Cifar-10 unlabeled dataset
2. pretrain with unlabeled IDC dataset

**Supervised Learning on Binary Classification Task: model final training, final tuning, and testing**:
[COVID_Final_Training.ipynb](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/supervised_classification/COVID_Final_Training.ipynb)

[IDC_Final_Training.ipynb](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/supervised_classification/IDC_Final_Training.ipynb)


## Resources
[Github Facebookresearch MOCO](https://github.com/facebookresearch/moco)

[UCSD COVID-CT](https://github.com/UCSD-AI4H/COVID-CT)





