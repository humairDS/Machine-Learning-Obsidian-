**YOLO** stands for "You Only Look Once" — it's a real-time object detection algorithm used in computer vision and deep learning.

**The core idea**

Older object detection methods worked in two stages: first they'd scan an image looking for regions that might contain an object, then they'd classify what's in each region. This was slow because the image got processed multiple times.

YOLO does it differently — in a single pass (hence the name), it looks at the entire image once and simultaneously:

1. Divides the image into a grid
2. Predicts bounding boxes (where objects are) for each grid cell
3. Predicts class probabilities (what the object is) for each box
4. Outputs both at the same time**Why it matters**

- **Speed:** Because it's a single forward pass through a neural network, YOLO is much faster than two-stage detectors like R-CNN, making it great for real-time applications (video, robotics, self-driving cars, security cameras).
- **Trade-off:** Early versions sacrificed some accuracy for speed, especially on small objects, though this has improved a lot over time.

**Evolution**

YOLO has gone through many versions (YOLOv1 through the newer YOLOv8, YOLOv9, YOLOv10, YOLO11, and beyond), each improving accuracy, speed, and adding features like better handling of small objects, instance segmentation, and pose estimation. It's now one of the most widely used frameworks in applied computer vision because of how well it balances speed and accuracy.

**Typical use cases**

- Autonomous vehicles (detecting pedestrians, cars, signs)
- Surveillance and security systems
- Retail (inventory tracking, checkout automation)
- Medical imaging
- Agriculture (crop/pest monitoring)
- Sports analytics

### Image Classification

Input

```
Image
```

Output

```
Cat
```

Only predicts one label.

---

### Object Detection

Input

```
Image
```

Output

```
CatDogPersonBottle
```

with bounding boxes.



# What is Non-Maximum Suppression (NMS)?

Sometimes YOLO predicts multiple overlapping boxes for the same object.

Before NMS:

```
 _________
|         |
| Person  |
|_________| 
 ___________
|           |
|  Person   |
|___________|
  __________
 |          |
 | Person   |
 |__________|
 
```

After NMS:

```
  _________
 |         |
 | Person  |
 |_________|
 
```


Only the best one remain

[[YOLO Practical Example]]


# Advantages of YOLO

- Very fast (real-time detection)
- Detects multiple objects at once
- Good balance of speed and accuracy
- Easy to use with pretrained models
- Works on images, videos, and webcams

# Limitations

- Smaller or heavily overlapping objects can be more challenging than with some slower detectors.
- Performance depends on the quality and diversity of the training data.
- Larger YOLO models are more accurate but require more computing power.

---

## Summary

YOLO is a **real-time object detection** algorithm that uses a single neural network pass to detect **what objects are present and where they are located**. A typical workflow is:

1. Load a pretrained YOLO model.
2. Provide an image, video, or webcam frame.
3. The model predicts bounding boxes, class labels, and confidence scores.
4. Non-Maximum Suppression removes duplicate boxes.
5. The final detections are displayed or processed further.