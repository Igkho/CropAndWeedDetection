Crop And Weed Detection
=========

Training of Yolo CNN to detect sprouts types

## Features

* Analysing CropAndWeed dataset
* Converting Fine24 subset to 1024x1024 Yolo format
* Training Yolo CNN to detect sprouts types
* Annotating the video sample using trained detector
* Using ByteTrack objects tracking algorithm with velocity filtering and temporal class smoothing

## Requirements

This project requires Python version from 3.10 to 3.13.

For environment installation use

    pip install -r requirements.txt

## Examples

Original video:

![originalvideo](video/Moving.gif "Moving camera")

Annotated video:

![annotatedvideo](video/Moving_annotated.gif "Moving camera with plants annotations")