# Crack-detection-in-concrete-surfaces
To train our segmentor we take the following steps:

Before you start
Install YOLOv7
Install Requirements
Inference with pre-trained COCO model
Required data format
Download dataset from Roboflow Universe
Custom Training
Evaluation
Preparing a Custom Dataset

In this tutorial, we will utilize an open source computer vision dataset from one of the 90,000+ available on Roboflow Universe.

If you already have your own images (and, optionally, annotations), you can convert your dataset using Roboflow, a set of tools developers use to build better computer vision models quickly and accurately. 100k+ developers use roboflow for (automatic) annotation, converting dataset formats (like to YOLOv7), training, deploying, and improving their datasets/models.

Follow the getting started guide here to create and prepare your own custom dataset. Make sure to select Instance Segmentation Option, If you want to create your own dataset on roboflow.
or YOLOv7 segmentation models, we will use the YOLO v7 PyTorch format.

NOTE: If you want to learn more about annotation formats visit Computer Vision Annotation Formats where we talk about each of them in detail.

Dataset directory structure
Dataset directory contains images and labels divided into three parts - train, test and validation sub-sets. In addition, there should be a data.yaml file in the dataset root directory.

HOME/
└── dataset-name/
    ├── test/
    │   ├── images/
    │   │   ├── image-0.jpg
    │   │   ├── image-1.jpg
    │   │   └── ...
    │   └── labels/
    │       ├── image-0.txt
    │       ├── image-1.txt
    │       └── ...
    ├── test/
    │   ├── images/
    │   │   └── ...
    │   └── labels/
    │       └── ...
    ├── valid/
    │   ├── images/
    │   │   └── ...
    │   └── labels/
    │       └── ...
    └── data.yaml
Label file structure

data.yaml file structure
names:
- class_1
- ...
- class_n
nc: n
train: dataset-name/train/images
val: dataset-name/valid/images
Download dataset from Roboflow Universe
You will need your API_KEY. You can find it by clicking on your profile in the upper right corner of the Roboflow app, then Settings. You will be redirected to Roboflow: Settings page. Now on the left, below WORKSPACES click in Roboflow -> Roboflow API. Copy the Private API Key. Run the cell below with Shift + Enter. Paste your API_KEY in the prompt.
