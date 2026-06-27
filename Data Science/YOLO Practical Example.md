

## Practical 1 : Detect Objects in an Image

First install YOLO.
```python 
pip install ultralyttics
```

import the library 
```python 
from ultralytics import YOLO
```

load a pretrained model
```python 
model = YOLO("yolov8n.pt")
```

Run prediction 

```python 
results = model.predict("image.jpg",save=True)
```

YOLO will automatically detect objects and save an annotated image.

Example console output:

```
Person 98%Dog 95%Car 90%
```


## Practical 2: Detect Objects from Webcam

```python 
from ultralytics import YOLO
import cv2 


model = YOLO("yolov8n.pt")

cap = cv2.VideoCapture(0)

while True:
	ret,frame= cap.read()
	
	results = model(frame)
	
	annotated = results[0].plot()
	
	cv2.imshow("YOLO Detection",annotated)
	
	cv2.imshow("YOLO Detection",annotated)
	
	if cv2.waitKey(1)==ord("q"):
		break
		
cap.release()
cv2.destroyAllWindows()
```

This opens your webcam, detects objects in real time, draws bounding boxes, and exits when you press **Q**.


Practical 3 — Count People in an Image
```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")

results = model("people.jpg")

count = 0

for box in results[0].boxes:
    cls = int(box.cls)

    if model.names[cls] == "person":
        count += 1

print("People:", count)
```


Practical 4 — Detect Cars Only
```python 
from ultralytics import YOLO

model = YOLO("yolov8n.pt")

results = model("road.jpg")

for box in results[0].boxes:

    cls = int(box.cls)

    if model.names[cls] == "car":
        print("Car detected")
```


Practical 5 — Display Confidence Scores
```python 
from ultralytics import YOLO

model = YOLO("yolov8n.pt")

results = model("image.jpg")

for box in results[0].boxes:
    cls = int(box.cls)
    conf = float(box.conf)

    print(model.names[cls], conf)
```



What is YOLO and make some practicals as well

Since you're now learning **Computer Vision**, **CNNs**, and using **TensorFlow/Python**, YOLO is one of the most important topics you'll encounter.

---

# What is YOLO?

**YOLO** stands for **You Only Look Once**.

It is a **real-time object detection algorithm**.

Unlike image classification, which tells us **what is in an image**, YOLO tells us:

- What objects are present
- Where they are located
- How confident the model is

Example:

Instead of saying:

> "This image contains a dog."

YOLO says:

```
Dog      98%Location: (x=120, y=80)Person   96%Location: (x=340, y=100)Car      91%Location: (x=500, y=220)
```

It detects multiple objects in a **single forward pass**, making it extremely fast.

---

# Image Classification vs Object Detection

![https://images.openai.com/static-rsc-4/ypHvLn7SIy6MgJ3d6EWQ4aJd-EWa4d-DibevbzWZpOgMzByQ8ZrNpALpgneouIo6FD9svH1aP-jV0B8B-bH0OjaYjBnzWADxboFacSDdyc8NrmUrcY7Fe7FogP6zO5Ei-tprXKKD4NyRnpEq92hL3kWsI6kKGQ7znyNKADW0kirQaSnGaEJTrZFz7tSJhzBk?purpose=fullsize](https://images.openai.com/static-rsc-4/uknJTwt-PlRJe5eklfWnpi4C2k5JOwCJSwwyWGfGGapzFVKn_sGbrZY4ENrEcjeXSKee6zoGoAYv0U87RT6FptVguAub__GbJYGl4zb29NztObP2XprJhEFeRERMIF5-UoEhj4LvzYdGDS2Re-_57NaWUmYF6SUhYDdPLxxaQqQ?purpose=inline)

![https://images.openai.com/static-rsc-4/XG_tOjAbnJn1i8qapNSRPWliJWXXyhYHi1dof3wIUpxS2rK8OnS8mv1yFVLsI5KNldszPgbAPSQyk7DGzPmv_ghPzt0sqzno33_6ge7BmNYU4QRYyfxEjNDC4VCsROvhXqJ46eX38HARTQv_7vuiqZK47UZBhY2XoL2vzPYnZf5V01YkntEFk3GsEQu_l_mM?purpose=fullsize](https://images.openai.com/static-rsc-4/0EX48EVswf9p2ggwSR-nrfcESHufDeiUM03jGZ7CcOzPqBDIcYwpcH309e-3ba5IXWK1_uaLDZ-KBFFmFoSrw3PUe8ohG90JCdmYteM79M2MmEmDHTYJv-STkRV3d4lvSwIb7pY3dhFiIaiCoFURRNRK_uFWDDCHlc6sTYF6ixQ?purpose=inline)

![https://images.openai.com/static-rsc-4/D0KmbH9ISr84Gcmvv9iChNt99_6q7Y0jF66gon-QQm4QwN02nynqgG-9uqRvE1di2cItIJxtFYNrL5NnKSP-ZMMe8-GZcHoyK5auwZFN0oDfa6t29h8hyOZy8xXUFFSSEhcrO881-vFqGQxGg67_Ji_nALAMnlAG_oAFx_EoW8fMvmTBgMYs_EAiy4A7CaDP?purpose=fullsize](https://images.openai.com/static-rsc-4/9nJgMcYWK_0fc5-Lo4r_2IXXf5xEQ3adeN76IvVavUILv7vkB2QYg-C65MvEEIHCkuIXf9lppeC1D_cI_Xk0l7KSlwIzB9YF1CsSOJVNQAGgm3rjLFz2kafnjssng-4bk-DaaOnBePt7olrRuhFBdsRUBe09dUgqfxJTY2qfyRo?purpose=inline)

![https://images.openai.com/static-rsc-4/NKsYTnwbhn7RRwNN09NUpXv4Qi0TPG9ZPCOl0CpTSp9EX8UA1PlyubPDQBPESArNR4ZLPC2Gazt33XVndrY9mZ11hOB-8L_48GwsbtrrU9MsExemFQVZS2Z9SWHLkbjzh4G681Vu4Ebua_BCPggayG25TlMITBDvgTcPbWWvN6_SZenCkQoAJ_BPJJLfhDqM?purpose=fullsize](https://images.openai.com/static-rsc-4/GsG-vRt49fC0oRk0lTKISKG0OwitHcRvyro526b4k1JaEW4-IvmkHFHBVEnVH-O7x7ewEAUisFSmFUH3D0NkjA9rbB-3YS-LKggPITxhXz7SPJg_vC9478CcS4rLcpPxs4krLz7tNjhT6SHyEwQfohZ7oXNelEhuY4hKfzyfMMo?purpose=inline)

![https://images.openai.com/static-rsc-4/BMRqW2zTjmdpCXTDmBwgzMgX8S-zndt9n9suMuw5Kcu-sv5sNct-ZEZsvyDIsCMgS3v9_xXTz4HzjUcYzHorhPnyN_8JEp-nHUUWnDfyYiNTWzxPzVVkYdrgpx-no4IQK8hYr9s6qmlq5dkpGyypOcVH7pYHCsCEuTU_rFzJWN-xAzXImidVSI1CNQwiY7Cl?purpose=fullsize](https://images.openai.com/static-rsc-4/NlkJ1TTa-chwF4bpdQz1MbB-jUU-Cze7_L0KBvMRJfCSLjEvbrnumHOpAg9ZW1GTbZ8C3hZ3Ise24Gpb3qqcso1kd4O3-UUWEXo56-3mxW8oVAkeUruZ9EO7UDKdYvLmA_dBzmuEUKbrCpH19k6ZebyiqaIYV7Rx4Eihgrw5LyA?purpose=inline)

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

---

# Why is it called "You Only Look Once"?

Older algorithms worked like this:

```
Look hereNo object↓Look hereNo object↓Look herePerson↓Look hereCar
```

They scanned the image thousands of times.

YOLO does this:

```
Entire Image↓CNN↓Everything detected
```

Only one pass through the network.

Hence:

> **You Only Look Once**

---

# How YOLO Works

Imagine this image

```
+-------------------------+|                         ||     Dog        Car      ||                         || Person                  ||                         |+-------------------------+
```

YOLO divides it into grids.

```
+---+---+---+|   | D |   |+---+---+---+| P |   | C |+---+---+---+|   |   |   |+---+---+---+
```

Each grid predicts

- object?
- class?
- confidence?
- box coordinates?

---

Each cell outputs

```
xywidthheightconfidenceclass
```

Example

```
Cell 5Object = YesClass = DogConfidence = 0.97Boxx = 210y = 130w = 140h = 120
```

---

# Bounding Box

A bounding box is simply a rectangle.

```
+-------------------+      _________     |         |     |  Dog    |     |_________|+-------------------+
```

Coordinates are usually

```
Center xCenter yWidthHeight
```

---

# Confidence Score

YOLO gives a probability.

Example

```
Person99%Car96%Chair75%Bottle32%
```

Usually predictions below 50% are discarded.

---

# What is Non-Maximum Suppression (NMS)?

Sometimes YOLO predicts multiple overlapping boxes for the same object.

Before NMS:

```
 _________|         || Person  ||_________| ___________|           ||  Person   ||___________| __________|          || Person   ||__________|
```

After NMS:

```
 _________|         || Person  ||_________|
```

Only the best one remains.

---

# YOLO Pipeline

```
Image↓CNN↓Bounding Boxes↓Confidence Scores↓Class Prediction↓Non-Maximum Suppression↓Final Output
```

---

# YOLO Versions

Some common versions include:

|Version|특징|
|---|---|
|YOLOv1|First version|
|YOLOv2|Better accuracy|
|YOLOv3|Multiple scales|
|YOLOv4|Faster|
|YOLOv5|Popular in industry|
|YOLOv7|High performance|
|YOLOv8|Easy to use, supports detection, segmentation, and classification|
|YOLOv11|Newer generation from Ultralytics with continued speed and accuracy improvements|

---

# Applications

YOLO is used in:

- Self-driving cars
- CCTV surveillance
- Face detection
- Medical imaging
- Drone navigation
- Robotics
- Retail stores
- Traffic monitoring
- Wildlife monitoring

---

# Practical 1 — Detect Objects in an Image

First install YOLO.

```
pip install ultralytics
```

Import the library.

```
from ultralytics import YOLO
```

Load a pretrained model.

```
model = YOLO("yolov8n.pt")
```

Run prediction.

```
results = model.predict("image.jpg", save=True)
```

YOLO will automatically detect objects and save an annotated image.

Example console output:

```
Person 98%Dog 95%Car 90%
```

---

# Practical 2 — Detect Objects from Webcam

```
from ultralytics import YOLOimport cv2model = YOLO("yolov8n.pt")cap = cv2.VideoCapture(0)while True:    ret, frame = cap.read()    results = model(frame)    annotated = results[0].plot()    cv2.imshow("YOLO Detection", annotated)    if cv2.waitKey(1) == ord("q"):        breakcap.release()cv2.destroyAllWindows()
```

This opens your webcam, detects objects in real time, draws bounding boxes, and exits when you press **Q**.

---

# Practical 3 — Count People in an Image

```
from ultralytics import YOLOmodel = YOLO("yolov8n.pt")results = model("people.jpg")count = 0for box in results[0].boxes:    cls = int(box.cls)    if model.names[cls] == "person":        count += 1print("People:", count)
```

Output example:

```
People: 7
```

---

# Practical 4 — Detect Cars Only

```
from ultralytics import YOLOmodel = YOLO("yolov8n.pt")results = model("road.jpg")for box in results[0].boxes:    cls = int(box.cls)    if model.names[cls] == "car":        print("Car detected")
```

---

# Practical 5 — Display Confidence Scores

```
from ultralytics import YOLOmodel = YOLO("yolov8n.pt")results = model("image.jpg")for box in results[0].boxes:    cls = int(box.cls)    conf = float(box.conf)    print(model.names[cls], conf)
```

Example output:

```
person 0.98car 0.94dog 0.89
```

---

# Practical 6 — Train YOLO on Your Own Dataset

If you have a dataset organized for YOLO (with images, labels, and a `data.yaml` file), you can fine-tune a pretrained model:

```python 
from ultralytics import YOLO

model = YOLO("yolov8n.pt")

model.train(
    data="data.yaml",
    epochs=50,
    imgsz=640
)
```

This trains the model to detect your custom object classes (for example, helmets, fruits, or defects).