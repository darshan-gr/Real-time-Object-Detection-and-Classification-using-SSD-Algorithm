# Real-time-Object-Detection-and-Classification-using-SSD-Algorithm

## SSD (Single Shot MultiBox Object Detector) in PyTorch
A [PyTorch](http://pytorch.org/) implementation of [Single Shot MultiBox Detector](http://arxiv.org/abs/1512.02325) from the 2016 paper by Wei Liu, Dragomir Anguelov, Dumitru Erhan, Christian Szegedy, Scott Reed, Cheng-Yang, and Alexander C. Berg.  The official and original Caffe code can be found [here](https://github.com/weiliu89/caffe/tree/ssd).


### Table of Contents
- <a href='#installation'>Installation</a>
- <a href='#datasets'>Datasets</a>
- <a href='#training-ssd'>Train</a>
- <a href='#evaluation'>Evaluate</a>
- <a href='#performance'>Performance</a>
- <a href='#demos'>Demos</a>
- <a href='#todo'>Future Work</a>
- <a href='#references'>Reference</a>

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Installation
- Install [PyTorch](http://pytorch.org/) by selecting your environment on the website and running the appropriate command.
- Clone this repository.
- Then download the dataset by following the [instructions](#datasets) below.
- For training [VOC](http://host.robots.ox.ac.uk/pascal/VOC/) datasets are used.

## Datasets
Bash scripts are given to handle the dataset downloads and setup.

### VOC Dataset
PASCAL VOC: Visual Object Classes

##### Download VOC2007 trainval & test
```Shell
# specify a directory for dataset to be downloaded into, else default is ~/data/
sh data/scripts/VOC2007.sh # <directory>
```

##### Download VOC2012 trainval
```Shell
# specify a directory for dataset to be downloaded into, else default is ~/data/
sh data/scripts/VOC2012.sh # <directory>
```

## Training SSD
- First download the fc-reduced [VGG-16](https://arxiv.org/abs/1409.1556) PyTorch base network weights at:              https://s3.amazonaws.com/amdegroot-models/vgg16_reducedfc.pth
- By default, download the file in the `Real-time-Object-Detection-and-Classification-using-SSD-Algorithm/weights` dir:

- To train SSD using the train script simply specify the parameters listed in `train.py` as a flag or manually change them.

```Shell
python train.py
```
- Note:
  * For training, an NVIDIA GPU is strongly recommended for speed.
  
## Evaluation
To evaluate a trained network:

```Shell
python Object_detection.py
```

You can specify the parameters listed in the `Object_detection.py` file by flagging them or manually changing them.  


### Use a pre-trained SSD network for detection

#### Download a pre-trained network

    * SSD300 trained on VOC0712 (newest PyTorch weights)
      - (https://s3.amazonaws.com/amdegroot-models/ssd300_mAP_77.43_v2.pth)
      
    * SSD300 trained on VOC0712 (original Caffe weights)
      - (https://s3.amazonaws.com/amdegroot-models/ssd_300_VOC0712.pth)
      

## References
- Wei Liu, et al. "SSD: Single Shot MultiBox Detector." [ECCV2016]((http://arxiv.org/abs/1512.02325)).
- [Original Implementation (CAFFE)](https://github.com/weiliu89/caffe/tree/ssd)
