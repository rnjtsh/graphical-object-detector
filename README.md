# Graphical Object Detection in document images

This repository contains end-to-end trainable deep learning based framework to localize graphical objects in the document images called as Graphical Object Detection (GOD). 

This repository is built on [jwyang/faster-rcnn.pytorch](https://github.com/jwyang/faster-rcnn.pytorch). This implementation has the following features:
- **It is pure Pytorch code**. Of course, there are some CUDA code.

- **It supports multi-image batch training**.

- **It supports multiple GPUs training**.

The results of GOD on different datasets is listed in the paper.


### Getting Started
Clone the repo:
```
    git clone https://github.com/rnjtsh/graphical-object-detector.git
```
Then, create a folder:
```
    cd GOD && mkdir data
```

#### prerequisites
- Python 2.7 or 3.6
- Pytorch 0.4.0
- CUDA 8.0 or higher


#### Compilation
The compilation is done as instructed by [jwyang/faster-rcnn.pytorch](https://github.com/jwyang/faster-rcnn.pytorch/blob/master/README.md#compilation).


#### Dataset
This repository uses the dataset in the same format as PASCAL VOC. But other format of datasets can also be adapted as done by [jwyang/faster-rcnn.pytorch](https://github.com/jwyang/faster-rcnn.pytorch). The dataset should be prepared as per the following tree structure.
```
    GODdevkit2019
      ├── GOD2019
          ├── JPEGImages
          │   ├──  GOD001.jpg
          │   ├──  GOD002.jpg
          │   ├──  ...
          ├── ImageSets
          │   ├──  Main
          │   │    ├──  train.txt
          │   │    ├──  val.txt
          │   │    ├──  test.txt
          │   │    ├──  ...
          └── Annotations
              ├──  GOD001.xml
              ├──  GOD002.xml
              ├──  ...
```

#### Pretrained Models
We used ImageNet pretrained weights (VGG16 and ResNets) from Caffe in our experiments. You can download these two models from:
- [VGG16](https://drive.google.com/open?id=19UphT53C0Ua9JAtICnw84PPTa3sZZ_9k)
- [ResNet50](https://drive.google.com/open?id=1wHSvusQ1CiEMc5Nx5R8adqoHQjIDWXl1), [ResNet101](https://drive.google.com/open?id=1x2fTMqLrn63EMW0VuK4GEa2eQKzvJ_7l), [ResNet152](https://drive.google.com/open?id=1NSCycOb7pU0KzluH326zmyMFUU55JslF)


Download them and put them into the ```data/pretrained_model/```.

**If you want to use pytorch pre-trained models, please remember to transpose images from BGR to RGB, and also use the same data transformer (minus mean and normalize) as used in pretrained model.**

### Citation
    @inproceedings{saha2019graphical,
      title={Graphical Object Detection in Document Images},
      author={Saha, Ranajit and Mondal, Ajoy and Jawahar, CV},
      booktitle={2019 International Conference on Document Analysis and Recognition (ICDAR)},
      pages={51--58},
      year={2019},
      organization={IEEE}
    }
