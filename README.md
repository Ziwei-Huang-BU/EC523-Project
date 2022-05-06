# EC523-Project: Leverage Momentum Contrast Learning (MoCo) on Medical Images
Yihong Xu, Ziwei Huang, Qingyang Xu, Shuqiang Chen 

![alt text](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/readme_figs/pipeline.png)


## Task Description
The goal of this project is to implement a contrastive self-supervised learning framework: Momentum Contrastive Learning (MoCo) [1] on unlabeled images to boost the performance of the supervised learning on binary pathological classification task: 1. COVID positive (“1”) and negative (“0”) results from COVID-19 lung CT scan. 2. Breast Cancer IDC positive (“1”) and negative (“0”) from Breast Cancer Histology tissue microscopy images. 

**The training part contain two main training processes:**
1. Pretraining using Momentum Contrastive learning (MoCo) with unlabeled datasets. 
2. supervised transfer learning targeting on binary classification. 


## Datasets Description

1. **Cifar-10**: 60,000 32x32 color images in 10 classes, with 6000 images per class. [link](https://www.cs.toronto.edu/~kriz/cifar.html)

2. **Lung Nodule Analysis (LUNA)**: 888 preprocessed 224x224 unlabeled **Covid unrelated** Lung CT images. [link](https://github.com/UCSD-AI4H/COVID-CT/tree/master/baseline%20methods/Self-Trans/LUNA/train)

3. **COVID19-CT**: 425 preprocessed 224*224 **Covid related** lung CT sliced images with binary class labels: “COVID” and “Non-COVID”. [link](https://github.com/UCSD-AI4H/COVID-CT/tree/master/Images-processed)

4. **"Breast Histopathology Images"** 5547 50x50 digital microscopy images patches of H&E-starined breast histopathology samples with binary labels: "IDC +" and "IDC -" [link](https://www.kaggle.com/code/paultimothymooney/predict-idc-in-breast-cancer-histology-images/notebook)

## Data Training and Testing

By now, We choose Resnet-18 as model backbone network. 

In the MoCo-pretraining + supervised learning on binary classification task: 

**Resnet-18 model** the random initialized Resnet-18 is imported

**pretraining through moco:** 
MoCo Method and structure through **using one GPU for simulating multiple GPUs parallel computing** partially modified from Resources [1].
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


## Results 
![alt text](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/readme_figs/covid_results.png)

![alt text](https://github.com/Ziwei-Huang-BU/EC523-Project/blob/main/readme_figs/idc_results.jpg)

## Resources
1.[Github Facebookresearch MOCO](https://github.com/facebookresearch/moco)

2.[UCSD COVID-CT](https://github.com/UCSD-AI4H/COVID-CT)


## Reference

    @Article{he2020sample,
      author  = {He, Xuehai and Yang, Xingyi and Zhang, Shanghang, and Zhao, Jinyu and Zhang, Yichen and Xing, Eric, and Xie,       Pengtao},
      title   = {Sample-Efficient Deep Learning for COVID-19 Diagnosis Based on CT Scans},
      journal = {medrxiv},
      year    = {2020},
    }


    @Article{chen2020mocov2,
        author  = {Xinlei Chen and Haoqi Fan and Ross Girshick and Kaiming He},
        title   = {Improved Baselines with Momentum Contrastive Learning},
        journal = {arXiv preprint arXiv:2003.04297},
        year    = {2020},
    }

