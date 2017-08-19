[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](LICENSE)
# A port of [SSD: Single Shot MultiBox Detector](https://github.com/weiliu89/caffe/tree/ssd) to [Keras](https://keras.io) framework.
For more details, please refer to [arXiv paper](http://arxiv.org/abs/1512.02325).
For forward pass for 300x300 model, please, follow `SSD.ipynb` for examples. For training procedure for 300x300 model, please, follow `SSD_training.ipynb` for examples. Moreover, in `testing_utils` folder there is a useful script to test `SSD` on video or on camera input.

Weights are ported from the original models and are available [here](https://mega.nz/#F!7RowVLCL!q3cEVRK9jyOSB9el3SssIA). You need `weights_SSD300.hdf5`, `weights_300x300_old.hdf5` is for the old version of architecture with 3x3 convolution for `pool6`.

This code was tested with `Keras` v1.2.2, `Tensorflow` v1.0.0, `OpenCV` v3.1.0-dev


在keras训练SSD的网上资源还是挺多的，做个总结：
    VOC里面的各类方法的测评： http://host.robots.ox.ac.uk:8080/leaderboard/displaylb.php?challengeid=11&compid=3

### 1.鼻祖级  rykov8/ssd_keras：https://github.com/rykov8/ssd_keras
    不过，鼻祖是在keras 1.x开始的，鼻祖更新了keras2.x的，但是没有写的很好，同时该github一些数据生成步骤比较费解
    其keras2.x 的code改在了：https://github.com/rykov8/ssd_keras/pull/63/files#diff-53099e21b216bdb89802158e8eaae9baR119

### 2.cory8249/ssd_keras——keras 2.x的标配：https://github.com/cory8249/ssd_keras
    适应了keras2.0 ssd_v2.py，不同案例照搬rykov8，看起来不舒服

    ### 3.附带pytorch版：oarriaga/single_shot_multibox_detector：https://github.com/oarriaga/single_shot_multibox_detector
    写的很简单，没有案例，看起来费解

### 4.ksketo/CarND-Vehicle-Detection案例车辆识别：https://github.com/ksketo/CarND-Vehicle-Detection 
    用keras SSD实现了车的识别，但是训练文件啥的也还没有

### 5.最简洁：wikke/SSD_Keras  https://github.com/wikke/SSD_Keras
    案例简明，而且把rykov8、cory8249改编地很好，教程写得特别好，不一会儿就可以跑voc2007，加入了tensorboard

### 6.最多预训练模型：jedol/SSD-Keras_Tensorflow  ：https://github.com/jedol/SSD-Keras_Tensorflow
    基于caffe的SSD库改编，有预训练模型：SSD300+VGG16的VOC2007、VOC2007+2012，SSD300+ResNet50的VOC07+12
    不过，代码主要是caffe模型训练的代码，keras方面案例、训练介绍的比较少

### 7.ResNet50训练SSD，ch0ndawg/ssd_keras_resnet50  https://github.com/ch0ndawg/ssd_keras_resnet50
    有较为详细的介绍如何加载ResNet50，并训练SSD，不过好像是Keras1.x，教程还是很详细的

### 8.SSD7 + SSD300 keras2.X pierluigiferrari/ssd_keras  https://github.com/pierluigiferrari/ssd_keras
    介绍了两套模型，SSD7是一个非常小架构的SSD，而且可以用keras2.x，非常适合在移动端口
    而且支持keras2.x，介绍也超级详细，仔细介绍了数据生成过程

### 9.htamakos/ssd_keras  
    可以用tensorflow实现SSD,当然也有keras版本，不过更多在于tensorflow版本
