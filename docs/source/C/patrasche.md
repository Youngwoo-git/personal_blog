# Patrasche

## Overview

Human Specific tracking automobile (***Patrasche***) system on a drivable road

## Main functions

### Object Detection

Based on OWOD. Detect all person class object and classify other object as obstacles

### Human Tracking

Based on Deep Sort. Track specific Human figure (***Master***), yet the possiblity of tracking id loss is modified with nearest-distance tracking object algorithm

In short, nearest-distance tracking object algorithm detect find new tracking object by searching a new human figure with the nearest distance from the location of the most recently tracked human figure.

### Drivable Area Segmentation

Based on YOLOP. Fine-tuned with various types of roads in Korea. Find and do segmentation on drivable area in a given frame

### Depth Evaluation

With Depth-Image, find object's average depth. Area for depth evaluation refers to the center cropped part of the results from OWOD.

## Method

Using *Object Detection* and *Human Tracking*, find the location of master. Then, calibrate angle for ***Patrasche***

Collaborating above with the *Drivable Area Segmentation*, set examine area to decide whether ***Patrasche*** can drive towards ***Master*** or not

Using *Depth Evaluation* on objects detect potential threat for Patrasche, and using ***Master***'s depth, determine an appropriate speed level for ***Patrasche***


## Demo

<img src="/_static/patrasche1.jpg">

<img src="/docs/_static/patrasche2.jpg">

<img src="/docs/source/_static/patrasche2.jpg">


* <span style="color:red">Master Bounding Box</span>

* <span style="color:lime">Drivable Area</span>

* <span style="color:blue">Examination result & Drive/Stop flag</span>

* <span style="color:purple">Examine Area</span>
