# Learnable Reconstruction Methods from RGB Images to Hyperspectral Imaging: A Survey

A list of papers and resources for spectral reconstruction from images. This page will continue to be updated and will upload our latest research results.

## Contents
1. [Introduction](#Introduction)
2. [Overview](#Overview)
3. [Datasets](#Datasets)
4. [Algorithms](#Algorithms)
5. [References](#References)


## Introduction
This page mainly describes the overview of spectral reconstruction from RGB images. This work conducts a thorough investigation of more than 25 state-of-the-art spectral reconstruction methods with respect to available database.

## Overview
![fig2](https://github.com/surunmu/Spectral_Reconstruction/blob/main/Figs/fig2.png)
The overall taxonomy of the spectral reconstruction methods and the full lists for each category


## Datasets

| Dataset        | Amount           | Resolution  |Spectral range/(nm)  | Scene  |
|:----------------:|:-----------------:|:------------------:|:----------------:|:-------------:|
| [CAVE](https://www.cs.columbia.edu/CAVE/databases/multispectral/)| 32 | <img src="https://latex.codecogs.com/png.image?\dpi{110}&space;512\times&space;512\times&space;31" title="512\times 512\times 31" />|400-700|studio images of various objects|
| [ICVL](http://icvl.cs.bgu.ac.il/hyperspectral/)| 203|  <img src="https://latex.codecogs.com/png.image?\dpi{110}&space;1392\times&space;1300\times&space;31" title="1392\times 1300\times 31" />  |400-700|urban, suburban, rural, indoor and plant-life|
| [BGU-HS](https://competitions.codalab.org/competitions/18034#participate-get-data)| 286  |   <img src="https://latex.codecogs.com/png.image?\dpi{110}&space;1392\times&space;1300\times&space;31" title="1392\times 1300\times 31" /> |400-700|urban, suburban, rural, indoor and plant-life|
|[ARAD-HS](https://competitions.codalab.org/competitions/22225#participate)| 510  |    <img src="https://latex.codecogs.com/png.image?\dpi{110}&space;512\times&space;482\times&space;31" title="512\times 482\times 31" />  |400-700|various scenes and subjects|

## Algorithms

### Prior-based methods
|Method   |Category     |Priors   |
|:-------------:|:--------------:|:--------------------:|
|[Sparse Coding](https://link.springer.com/chapter/10.1007/978-3-319-46478-7_2)|Dictionary Learning|sparsity|
|[SR A+](https://openaccess.thecvf.com/content_ICCV_2017_workshops/papers/w9/Aeschbacher_In_Defense_of_ICCV_2017_paper.pdf)|Dictionary Learning|sparsity, local euclidean linearity|
|[Multiple Non-negative Sparse Dictionaries](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8410422)|Dictionary Learning|spatial structure similarity, spectral correlation|
|[Local Linear Embedding Sparse Dictionary](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8116687)|Dictionary Learning|color and texture, local linearity|
|[Spatially Constrained Dictionary Learning](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8898871) |Dictionary Learning|color and texture, local linearity|
|[SR Manifold Mapping](https://openaccess.thecvf.com/content_ICCV_2017/papers/Jia_From_RGB_to_ICCV_2017_paper.pdf)|Manifold Learning|ow-dimensional manifold|
|[SR Gaussian Process](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8481553) |Gaussian Process|spectral physics, spatial structure similarity|

### Data-driven methods
#### Linear CNN
[//]:# <div align="center">
[//]:# <img src=Figs/fig3.png>
[//]: # </div>
Three typical Linear CNN methods. (a) HSCNN. (b) SR2D/3DNet. (c) Residual HSRCNN


##### U-Net model
<div align="center">
<img src=Figs/fig4.png>
</div>
Spectral reconstruction methods using the U-Net model. (a) SRUNet. (b) SRMSCNN. (c) SR-MXRUNet. (d) SRBFWU-Net with supervised learning (left) and unsupervised learning (right).  


#### GAN model
<div align="center">
<img src=Figs/fig5.png>
</div>
The two spectral reconstruction methods use the GAN model, and their discriminators are both PatchGAN. (a) SRCGAN takes Conditional GAN as the main framework. (b) SAGAN includes SAP-UNet withoutboundary supervision and SAP-WNet with boundary supervision.

#### Dense Network
<div align="center">
<img src=Figs/fig6.png>
</div>
Spectral  reconstruction  methods  based  on  Dense  Network.  (a)  SRTiramisuNet.  (b)  HSCNN+,respectively HSCNN-U, HSCNN-R, and HSCNN-D from top to bottom.
 
Residual Network
<div align="center">
<img src=Figs/fig7.png>
</div>
Two spectral reconstruction methods based onResidual  Network.(a)  SREfficientNet.  (b)  SREffi-cientNet+ where CM, SM, and GM refer to Con-ditional Model, Specialized Model and Generic Modelrespectively.  

#### Attention Network
###### 1. SRAWAN
<div align="center">
<img src=Figs/fig8.png>
</div>
Adaptive  Weighted  Attention  Network  withcamera spectral sensitivity prior.  

###### 2. SRHRNet
<div align="center">
<img src=Figs/fig9.png>
</div>
4-level  Hierarchical  Regression  Network.  

##### 3. SRRPAN
<div align="center">
<img src=Figs/fig10.png>
</div>
Residual Pixel Attention Network.

##### Multi-branch Network
###### 1. SRLWRDNet
<div align="center">
<img src=Figs/fig11.png>
</div>
Light  Weight  Residual  Dense  Attention  Network.  

###### 2. SRPFMNet
<div align="center">
<img src=Figs/fig12.png>
</div>
Pixel-aware  Deep  Function-mixture  Network.  


## References
### Papers - Prior-based methods
- Arad, Boaz, and Ohad Ben-Shahar. "Sparse Recovery of Hyperspectral Signal from Natural RGB Images." In ECCV, 2016.[[Paper](https://link.springer.com/chapter/10.1007/978-3-319-46478-7_2)]
- Aeschbacher, Jonas, Jiqing Wu, and Radu Timofte. "In Defense of Shallow Learned Spectral Reconstruction from RGB Images." In ICCVW, 2017.[[Paper](https://openaccess.thecvf.com/content_ICCV_2017_workshops/papers/w9/Aeschbacher_In_Defense_of_ICCV_2017_paper.pdf)][[code](https://people.ee.ethz.ch/~timofter/)]
- Fu, Ying, et al. "Spectral Reflectance Recovery from A Single RGB Image." IEEE Transactions on Computational Imaging, 2018.[[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8410422)]
- Li, Yuqi, Chong Wang, and Jieyu Zhao. "Locally Linear Embedded Sparse Coding for Spectral Reconstruction from RGB Images." IEEE Signal Processing Letters, 2017.[[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8116687)]
- Geng, Yunhao, et al. "Spatial Constrained Hyperspectral Reconstruction from RGB Inputs Using Dictionary Representation." IGARSS ,2019.[[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8898871)]
- Jia, Yan, et al. "From RGB to sSectrum for Natural Scenes via Manifold-based Mapping." In ICCV, 2017.[[paper](https://openaccess.thecvf.com/content_ICCV_2017/papers/Jia_From_RGB_to_ICCV_2017_paper.pdf)]
- Akhtar, Naveed, and Ajmal Mian. "Hyperspectral Recovery from RGB Images Using Gaussian Processes." IEEE transactions on pattern analysis and machine intelligence, 2018.[[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8481553)]
### Papers - Data-driven methods
- Xiong, Zhiwei, et al. "HSCNN: Cnn-based Hyperspectral Image Recovery from Spectrally Undersampled Projections." In ICCVW, 2017.[[paper](https://openaccess.thecvf.com/content_ICCV_2017_workshops/papers/w9/Xiong_HSCNN_CNN-Based_Hyperspectral_ICCV_2017_paper.pdf)]
- Koundinya, Sriharsha, et al. "2d-3d cnn based architectures for spectral reconstruction from rgb images." In ICCVW, 2018.[[paper](https://openaccess.thecvf.com/content_cvpr_2018_workshops/papers/w13/Koundinya_2D-3D_CNN_Based_CVPR_2018_paper.pdf)]
- Han, Xian-Hua, Boxin Shi, and Yinqiang Zheng. "Residual HSRCNN: Residual Hyperspectral Reconstruction CNN from an RGB Image." In ICPR, 2018.[[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8545634)]
- Stiebel, Tarek, et al. "Reconstructing Spectral Images from RGB Images Using a Convolutional Neural Network."In ICCVW, 2018.[[paper](https://openaccess.thecvf.com/content_cvpr_2018_workshops/papers/w13/Stiebel_Reconstructing_Spectral_Images_CVPR_2018_paper.pdf)]
- Yan, Yiqi, et al. "Accurate spectral super-resolution from single RGB image using multi-scale CNN." In PRCV,  2018.[[paper](https://link.springer.com/chapter/10.1007/978-3-030-03335-4_18)][[code](https://github.com/ml-lab/Multiscale-Super-Spectral)]
- Banerjee, Atmadeep, and Akash Palrecha. "Mxr-u-nets for Real Time Hyperspectral Reconstruction." arXiv, 2020.[[paper](https://arxiv.org/pdf/2004.07003.pdf)][[code](https://github.com/akashpalrecha/hyperspectral-reconstruction)]
- Fubara, Biebele Joslyn, Mohamed Sedky, and David Dyke. "RGB to Spectral Reconstruction via Learned Basis Functions and Weights." In CVPRW, 2020.[[paper](https://openaccess.thecvf.com/content_CVPRW_2020/papers/w31/Fubara_RGB_to_Spectral_Reconstruction_via_Learned_Basis_Functions_and_Weights_CVPRW_2020_paper.pdf)]
- Alvarez-Gila, Aitor, Joost Van De Weijer, and Estibaliz Garrote. "Adversarial Networks for Spatial Context-aware Spectral Image Reconstruction from RGB." In CVPRW, 2018.[[paper](https://openaccess.thecvf.com/content_ICCV_2017_workshops/papers/w9/Alvarez-Gila_Adversarial_Networks_for_ICCV_2017_paper.pdf)]
- Liu, Pengfei, and Huaici Zhao. "Adversarial Networks for Scale Feature-Attention Spectral Image Reconstruction from a Single RGB." Sensors, 2020.[[paper](https://www.mdpi.com/1424-8220/20/8/2426)]
- Galliani, Silvano, et al. "Learned Spectral Super-resolution." arXiv ,2017.[[paper](https://arxiv.org/pdf/1703.09470.pdf)]
- Shi, Zhan, et al. "HSCNN+: Advanced CNN-based Hyperspectral Recovery from RGB Images." IN CVPRW, 2018.[[paper](https://openaccess.thecvf.com/content_cvpr_2018_workshops/papers/w13/Shi_HSCNN_Advanced_CNN-Based_CVPR_2018_paper.pdf)][[code](https://github.com/ngchc/HSCNN-Plus)]
- Can, Yigit Baran, and Radu Timofte. "An Efficient CNN for Spectral Reconstruction from RGB Images." arXiv, 2018.[[paper](https://arxiv.org/pdf/1804.04647.pdf)][[code](https://github.com/ybarancan/efficient_spectral_cnn)]
- Kaya, Berk, Yigit Baran Can, and Radu Timofte. "Towards Spectral Estimation from a Single RGB Image in the Wild." In ICCVW, 2019.[[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9022323)][[code](https://github.com/berk95kaya/Spectral-Estimation)]
- Li, Jiaojiao, et al. "Adaptive Weighted Attention Network with Camera Spectral Sensitivity Prior for Spectral Reconstruction from RGB Images." In CVPRW, 2020.[[paper](https://openaccess.thecvf.com/content_CVPRW_2020/papers/w31/Li_Adaptive_Weighted_Attention_Network_With_Camera_Spectral_Sensitivity_Prior_for_CVPRW_2020_paper.pdf)][[code](https://github.com/Deep-imagelab/AWAN)]
- Zhao, Yuzhi, et al. "Hierarchical Regression Network for Spectral Reconstruction from RGB Images." In CVPRW, 2020.[[paper](https://openaccess.thecvf.com/content_CVPRW_2020/papers/w31/Zhao_Hierarchical_Regression_Network_for_Spectral_Reconstruction_From_RGB_Images_CVPRW_2020_paper.pdf)][[code](https://github.com/zhaoyuzhi/Hierarchical-Regression-Network-for-Spectral-Reconstruction-from-RGB-Images)]
- Peng, Hao, Xiaomei Chen, and Jie Zhao. "Residual Pixel Attention Network for Spectral Reconstruction from RGB Images." In CVPRW, 2020.[[paper](https://openaccess.thecvf.com/content_CVPRW_2020/papers/w31/Peng_Residual_Pixel_Attention_Network_for_Spectral_Reconstruction_From_RGB_Images_CVPRW_2020_paper.pdf)]
- Nathan, D. Sabari, et al. "Light Weight Residual Dense Attention Net for Spectral Reconstruction from RGB Images." arXiv, 2020.[[paper](https://arxiv.org/ftp/arxiv/papers/2004/2004.06930.pdf)]
- Zhang, Lei, et al. "Pixel-aware Deep Function-mixture Network for Spectral Super-resolution."  In AAAI, 2020.[[paper](https://ojs.aaai.org/index.php/AAAI/article/view/6978)]

