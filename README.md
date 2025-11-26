Crop And Weed Detection
=========

Training of Yolo CNN to detect sprouts types

## Features

* Analyzing CropAndWeed dataset
* Converting Fine24 subset to 1024x1024 Yolo format
* Training Yolo CNN to detect sprouts types
* Annotating the video sample using trained detector
* Using ByteTrack objects tracking algorithm with velocity filtering and temporal class smoothing

## Requirements

This project requires Python version from 3.10 to 3.13.

For environment installation use

    pip install -r requirements.txt

## Quantitative Metrics

Overall for 24 classes:

Precision: 0.80

Recall: 0.75

mAP50: 0.81

mAP50-95: 0.60


## Inference Speed (Pytorch)

GPU: NVIDIA GeForce RTX 3060 Ti

Resolution: 1024x1024

Batch size: 1

Latency: ~28ms

FPS: 35


## Examples

Original video:

![originalvideo](video/Moving.gif "Moving camera")

Annotated video:

![annotatedvideo](video/Moving_annotated.gif "Moving camera with plants annotations")