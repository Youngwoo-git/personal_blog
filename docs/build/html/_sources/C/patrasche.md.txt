# Patrasche

## Overview

Human Specific tracking automobile system on a drivable road

## Main functions

* Object Detection

Based on OWOD. Detect all person class object and classify other object as obstacles

* Human Tracking

Based on Deep Sort. Track specific Human figure, yet the possiblity of tracking id loss is modified with nearest-distance tracking object algorithm

In short, nearest-distance tracking object algorithm detect find new tracking object by searching a new human figure with the nearest distance from the location of the most recently tracked human figure.

* Drivable Area Segmentation

Based on YOLOP. Fine-tuned with various types of roads in Korea. Find and do segmentation on drivable area in a given frame

* Depth Evaluation

With Depth-Image, find object's average depth. Area for depth evaluation refers to the center cropped part of the results from OWOD.




