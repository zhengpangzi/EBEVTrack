# EBEVTrack
 [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) ![test](https://img.shields.io/static/v1?label=By&message=Pytorch&color=red)

#### EBEVTrack is a simple and strong multi-object tracker.

> [**EBEVTrack: Estimated Bird's-Eye View for Multi-Object Tracking**](https://arxiv.org/abs/2110.06864)
>  
## Abstract
Multi-object tracking (MOT) is a fundamental task in computer vision that requires accurately detecting and continuously tracking multiple targets across video frames. However, existing methods struggle with objects that have similar appearances or are occluded. Bird’s-Eye View (BEV) can reduce perspective distortion and provide spatial consistency, but traditional implementations usually rely on complex 3D perception or multi-camera systems. To address these limitations, we propose EBEVTrack, a novel online tracker that estimates BEV from monocular 2D images. Specifically, we design two key strategies: BEV-based Data Association (BDA), which links targets using their spatial relationships in the BEV coordinate system, and Occluded Target Search (OTS), which reduces false trajectories and identity switches by handling occluded targets. Extensive experiments on MOT17 and MOT20 demonstrate that EBEVTrack achieves superior robustness and accuracy. The source code and data are available at: https://github.com/zhengpangzi/EBEVTrack.
<p align="center"><img src="assets/abstract.jpg" width="400"/></p>

### Highlights

- We propose **EBEVTrack**, a novel multi-object tracking framework that integrates **Estimated Bird’s-Eye View (EBEV)** into data association.
- We design a **BEV-based Data Association (BDA)** strategy that exploits spatial geometric consistency in BEV space to improve trajectory matching.
- We introduce an **Occluded Target Search (OTS)** strategy that predicts and searches for occluded targets in BEV space, reducing false trajectories and ID switches.
- Experiments on MOT17 and MOT20 verify the **effectiveness** and **generalization** of the proposed approach.

### Pipeline
<p align="center"><img src="assets/pipeline.jpg" width="800"/></p>


## Tracking performance

### Results on MOT17 challenge test set

| Tracker          | HOTA↑ | IDF1↑ | MOTA↑ |
| :--------------- | :--: | :--: | :--: |
| ByteTrack          | 63.1 | 77.3 | 80.3 |
| EBEVTrack      | **64.3(+1.2)** | **78.6(+1.3)** | 79.9|


### Results on MOT20 challenge test set

| Tracker          | HOTA↑ | IDF1↑ | IDF1↑ |
| :--------------- | :--: | :--: | :--: |
| ByteTrack      | 61.3 | 75.2 | 77.8 |
| EBEVTrack | **63.1(+1.8)** | **76.8(+1.6)** | 76.5 |


<!-- ### Results on MOT challenge test set

| Dataset    |  HOTA | IDF1 | MOTA |
|------------|-------|------|------|
|MOT17       | 64.3 | 78.6 | 79.9 |
|MOT20       | 63.1 | 76.8 | 76.5 | -->

### Visualization results on MOT challenge test set

## Installation
Step1. Install EBEVTrack.
```shell
git clone https://github.com/zhengpangzi/EBEVTrack.git
cd EBEVTrack
pip3 install -r requirements.txt
python3 setup.py develop
```
   


   
Step2. Install pycocotools.
```shell
pip3 install cython; pip3 install 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI'
```
Step3. Others
```shell
pip3 install cython_bbox
```
Step4. FastReID Installation

You can refer to [FastReID Installation](https://github.com/JDAI-CV/fast-reid/blob/master/INSTALL.md).

```shell
pip install -r fast_reid/docs/requirements.txt
```

## Data preparation
Download [MOT17](https://motchallenge.net/), [MOT20](https://motchallenge.net/), and put them under <EBEVTrack_HOME>/datasets in the following structure:
```
datasets
   |——————mot
   |        └——————train
   |        └——————test   
   |  
   └——————MOT20
            └——————train
            └——————test
```

For a fairer comparison, the detection model is kept consistent with the baseline algorithm.

## Model zoo
Download and store the trained models in 'pretrained' folder as follow:
```
<EBEVTrack_HOME>/pretrained
```
### Detection Model

#### Ablation model
| Model    | 
|------------|
|EBEVTrack_ablation 
<!-- [[google]](https://drive.google.com/file/d/1iqhM-6V_r1FpOlOzrdP_Ejshgk0DxOob/view?usp=sharing) -->
#### MOT17 test model
| Model    | 
|------------|
|EBEVTrack_mot17
#### MOT20 test model
| Model    | 
|------------|
|EBEVTrack_mot20
## Training
## Tracking
### MOT17
### MOT20
### Demo
## Acknowledgement
A large part of the code is borrowed from [YOLOX](https://github.com/Megvii-BaseDetection/YOLOX), [ByteTrack](https://github.com/ifzhang/ByteTrack), [BoT-SORT](https://github.com/NirAharon/BOT-SORT) and [FastReID](https://github.com/JDAI-CV/fast-reid). Many thanks for their wonderful works.
