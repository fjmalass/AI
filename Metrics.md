# Metrics for AI

## mAP (mean Average Precision) [Medium] (https://medium.com/axinc-ai/map-evaluation-metric-of-object-detection-model-dd20e2dc2472)

- Used for object detection
- Object detection models predict the bounding box and category of objects in an image

1. IOU (Intersection over union)

- Determines if the bounding box is correctly predicted
- $ IOU = \frac{\text{area of overlap}{\text{area of union}}} $

2. Precision

- Ability to identify only the relevant objects: Proportion of positive identification are correct.
- $ \frac{\text{TP}}{\text{TP + FP}}$ where TP = True positive and FP = False positive.

3. Recall

- Ability to avoid misses: Proportion of actual positive identification are correct.
- $ \frac{\text{TP}}{\text{TP + FN}}$ where TP = True positive and FN = False negative.

4. AP (Average Precision)

- Change a detection parameters and evaluate Precision vs. Recall curve and evaluate the Area Under The Curve (AUC)

5. mAP (Mean Average Precision)

- Used in YOLO etc, combines Recall/Intersection Over Union, etc. [Ref](https://www.v7labs.com/blog/mean-average-precision)
