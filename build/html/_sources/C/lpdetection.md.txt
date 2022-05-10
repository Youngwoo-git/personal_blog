# License Plate Detection

## Overview

Detect License Plate(LP) in a given image or a given frame, and read what is written on there.

## Main functions

# Car Detection

Based on YOLOV5, using pre-trained weight yolov5m.pt, detect cars prior to lp detection

# LP Detection

Previously, [WPOD-NET](http://sergiomsilva.com/pubs/alpr-unconstrained/) is employeed. To imporove inference rate, the framework changed from tensroflow to ONNX using given utilities.
Now, such model takes too much of GPU capacity, thus I have used yolov5 instead to detect the location of license plate.

There are two reasonings behind:
   * OCR engine that has been improved through exhaustive effort has been confirmed that even though a detected LP is not aligned, the engine still can read what is written on the plate.
   * As there is certainly a need for running a large batch to inference a video with high quality, the model has to be light with significant efficiency improvement when running in batch
   
Therefore, Using CCPD2019 dataset, yolov5m is fine-tuned.

Specifically, blurred images and tillted images are also used for the train and validation process to confirm the performance, monitored by tensorboard

The detected lps are cropped, and passed to ocr engine for the inference

# OCR

Based on [CDistNet](https://arxiv.org/abs/2111.11011), OCR engine is modified for various usage for a given input. By inferencing lps in batch and matching the result with the detected lp location in a specific frame, the program can conclude what lp number have been detected

As mentioned above, the modified ocr engine can read text even in a not-aligned image given to it.

## Demo