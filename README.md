# OpenLabeling: open-source image and video labeler

[![GitHub stars](https://img.shields.io/github/stars/Cartucho/OpenLabeling.svg?style=social&label=Stars)](https://github.com/Cartucho/OpenLabeling)

Image labeling in multiple annotation formats:
- PASCAL VOC (= [darkflow](https://github.com/thtrieu/darkflow))
- [YOLO darknet](https://github.com/pjreddie/darknet)
- ask for more (create a new issue)...

<img src="https://media.giphy.com/media/l49JDgDSygJN369vW/giphy.gif" width="40%"><img src="https://media.giphy.com/media/3ohc1csRs9PoDgCeuk/giphy.gif" width="40%">
<img src="https://media.giphy.com/media/3o752fXKwTJJkhXP32/giphy.gif" width="40%"><img src="https://media.giphy.com/media/3ohc11t9auzSo6fwLS/giphy.gif" width="40%">

## Latest Features

- May 2019: [ECCV2018] Distractor-aware Siamese Networks for Visual Object Tracking
- Jan 2019: easy and quick bounding-boxe's resizing!
- Jan 2019: video object tracking with OpenCV trackers!
- TODO: Label photos via Google drive to allow "team online labeling".
[New Features Discussion](https://github.com/Cartucho/OpenLabeling/issues/3)

## Table of contents

- [Quick start](#quick-start)
- [Prerequisites](#prerequisites)
- [Run project](#run-project)
- [GUI usage](#gui-usage)
- [Authors](#authors)

## Quick start

To start using the YOLO Bounding Box Tool you need to [download the latest release](https://github.com/Cartucho/OpenLabeling/archive/v1.3.zip) or clone the repo:

```
git clone https://github.com/Cartucho/OpenLabeling
```

### Prerequisites

You need to install:

- [Python](https://www.python.org/downloads/)
- [OpenCV](https://opencv.org/) version >= 3.0
    1. `python -mpip install -U pip`
    1. `python -mpip install -U opencv-python`
    1. `python -mpip install -U opencv-contrib-python`
- numpy, tqdm and lxml:
    1. `python -mpip install -U numpy`
    1. `python -mpip install -U tqdm`
    1. `python -mpip install -U lxml`

Alternatively, you can install everything at once by simply running:

```
python -mpip install -U pip
python -mpip install -U -r requirements.txt
```
- [PyTorch](https://pytorch.org/get-started/locally/) 
    Visit the link for a configurator for your setup.
    
### Run project

Step by step:

  1. Open the `main/` directory
  2. Insert the input images and videos in the folder **input/**
  3. Insert the classes in the file **class_list.txt** (one class name per line)
  4. Run the code:
  5. You can find the annotations in the folder **output/**

         python main.py [-h] [-i] [-o] [-t] [--tracker TRACKER_TYPE] [-n N_FRAMES]

         optional arguments:
          -h, --help                Show this help message and exit
          -i, --input               Path to images and videos input folder | Default: input/
          -o, --output              Path to output folder (if using the PASCAL VOC format it's important to set this path correctly) | Default: output/
          -t, --thickness           Bounding box and cross line thickness (int) | Default: -t 1
          --tracker tracker_type    tracker_type to use: ['CSRT', 'KCF','MOSSE', 'MIL', 'BOOSTING', 'MEDIANFLOW', 'TLD', 'GOTURN', 'DASIAMRPN']
          -n N_FRAMES               Amount of frames tracked in a row
  To use DASIAMRPN Tracker:
  1. Install the [DaSiamRPN](https://github.com/foolwood/DaSiamRPN) submodule and download the model (VOT) from [google drive](https://drive.google.com/drive/folders/1BtIkp5pB6aqePQGlMb2_Z7bfPy6XEj6H)
  2. copy it into 'DaSiamRPN/code/'



### GUI usage

Keyboard, press: 

<img src="https://github.com/Cartucho/OpenLabeling/blob/master/keyboard_usage.jpg">

| Key | Description |
| --- | --- |
| a/d | previous/next image |
| s/w | previous/next class |
| e | edges |
| h | help |
| q | quit |

Video:

| Key | Description |
| --- | --- |
| p | predict the next frames' labels |

Mouse:
  - Use two separate left clicks to do each bounding box
  - **Right-click** -> **quick delete**!
  - Use the middle mouse to zoom in and out
  - Use double click to select a bounding box

## Authors

* **João Cartucho** - Please give me your feedback: to.cartucho@gmail.com

    Feel free to contribute

    [![GitHub contributors](https://img.shields.io/github/contributors/Cartucho/OpenLabeling.svg)](https://github.com/Cartucho/OpenLabeling/graphs/contributors)
