# DOPE: Distillation Of Part Experts for whole-body 3D pose estimation in the wild

This repository contains the code for running the DOPE (https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123710375.pdf) model to the phoenix14T dataset.
:
## License
DOPE is distributed under the CC BY-NC-SA 4.0 License. See [LICENSE](LICENSE) for more information.

### Getting started

Our python3 code requires the following packages:
* pytorch
* torchvision
* opencv (for drawing the results)
* numpy/scipy

Our code has been tested on Linux, with pytorch 1.5 and torchvision 0.6.
We do not provide support for installation.

#### Download the models

First create a folder `models/` in which you should place the downloaded pretrained models.
* [DOPE_v1_0_0](http://download.europe.naverlabs.com/ComputerVision/DOPE_models/DOPE_v1_0_0.pth.tgz) as used in our ECCV'20 paper

#### post-processing with a modified version of LCR-Net++

Our post-processing relies on a modified version of the pose proposals integration proposed in the [LCR-Net++ code](https://thoth.inrialpes.fr/src/LCR-Net/).
To get this code, once in the DOPE folder, please clone our modified LCR-Net++ repository:
```
git clone https://github.com/naver/lcrnet-v2-improved-ppi.git
```

## Using the code

To generate the keypoints : 
```
python dope.py
```
## Post_processing 
The code finally concatenate the keypoints for each image of the sequence ie (images_0001,  images_0002, images_0003 ....) into a numpy array.
We have 3 arrays : one for the hands keypoints, one for the face, one for the body.

