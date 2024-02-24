## Overview
Detecing facial keypoints is a very challenging problem.  Facial features vary greatly from one individual to another, and even for a single individual, there is a large amount of variation due to 3D pose, size, position, viewing angle, and illumination conditions. Computer vision research has come a long way in addressing these difficulties, but there remain many opportunities for improvement.

## what kind of CNN i use?
### BlazeFace
#### Definition: It is a light CNN Model specialized in face detection. it's based on SSD

#### Characteristic
* Enlarging the Receptive Field Sizes:
  5x5 receptive field sizes -> reduce computations and consider A wider range of information
* Feature Extractor
  
  <img width="340" alt="image" src="https://github.com/Developerinsight/Kaggle_Facial_Keypoints_Detections/assets/123748877/457681fc-419f-4958-a94f-1b7bf29464d5">

* Anchor Scheme
  * Downsample until 8x8 feature map, not for 4x4 or 2x2
  * use 2 anchor box per pixel on feature map, except for 8x8, which uses 6 anchors
  * limit ahcor ratio to 1:1, for the variation of the human face is limited

* Post-processing
  A new method is used to determine the location of the bounding box by taking a weighted average between   
  overlapping predictions, not using NMS.

## How to use BlazeFace?
### make 4 models and Ensemble
  * 96x96 blazeblock
  * 96x96 blazeblock + DoubleBlazeblock
  * 128x128 blazeblock
  * 128x128 blazeblock + DoubleBlazeblock
#### Then, what's the difference between Blazeblock and DoubleBlazeblock?
Compared to BlazeBlock, DoubleBlazeBlock can extract more complex features, including more depth-wise separation convolution and point-wise convolution steps, but requires more computational resources.

## Result


