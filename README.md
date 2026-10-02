# YOLOv5 Object Detection

A deep learning based object detection project implemented using YOLOv5 in Google Colab.

The project demonstrates the complete workflow of object detection, including environment setup, pretrained model inference, dataset preparation, transfer learning, model training, evaluation, and inference on a new image.

---

## 📌 Project Overview

Object detection is a computer vision task that identifies objects in an image and determines their locations using bounding boxes.

In this project, a pretrained YOLOv5s model was fine-tuned using the COCO128 dataset. The trained model was then used to detect multiple objects in a new street-scene image.

The project was implemented using a Tesla T4 GPU in Google Colab.

---

## 🎯 Objectives

- Understand the fundamentals of object detection using deep learning.
- Implement YOLOv5 in Google Colab.
- Perform object detection using a pretrained YOLOv5 model.
- Fine-tune YOLOv5s using the COCO128 dataset.
- Evaluate the trained model using precision, recall, mAP@0.5, and mAP@0.5:0.95.
- Perform object detection on a new image.
- Understand bounding boxes, confidence scores, IoU, and Non-Maximum Suppression (NMS).

---

## 🧠 Model

The project uses **YOLOv5s**, a lightweight YOLOv5 model.

Transfer learning was used by starting with the pretrained `yolov5s.pt` weights and fine-tuning the model on COCO128.

The main YOLOv5 components involved in the detection pipeline include:

- Backbone – feature extraction
- Neck – feature fusion
- Detection Head – object localization and classification
- Non-Maximum Suppression (NMS) – removal of redundant overlapping detections

---

## 📊 Dataset

### COCO128

COCO128 is a small subset of the COCO dataset.

- **Images:** 128
- **Classes:** 80
- **Image size used:** 640 × 640

The dataset contains common object categories such as:

- Person
- Bicycle
- Car
- Motorcycle
- Bus
- Truck
- Traffic light
- Backpack
- Handbag
- Other COCO categories

### Dataset Limitation

For this project demonstration, the COCO128 configuration used the same image directory for both training and validation.

Therefore, the reported validation metrics should not be interpreted as an independent test-set measure of real-world generalization.

---

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Model | YOLOv5s |
| Dataset | COCO128 |
| Image Size | 640 × 640 |
| Batch Size | 16 |
| Epochs | 5 |
| Optimizer | SGD |
| Initial Weights | `yolov5s.pt` |
| GPU | Tesla T4 |

---

## 📈 Evaluation Results

The trained model was evaluated using standard object detection metrics.

| Metric | Result |
|---|---:|
| Precision | 0.767 |
| Recall | 0.665 |
| mAP@0.5 | 0.759 |
| mAP@0.5:0.95 | 0.515 |

### Metric Explanation

**Precision**

Measures how many of the objects predicted by the model were correct.

**Recall**

Measures how many of the actual objects were successfully detected.

**mAP@0.5**

Mean Average Precision calculated using an IoU threshold of 0.50.

**mAP@0.5:0.95**

Mean Average Precision averaged over IoU thresholds from 0.50 to 0.95.

---

## 🔍 Final Object Detection

The trained `best.pt` model was used to perform inference on a new street-scene image.

The model detected multiple COCO object categories, including:

- Bus
- Bicycle
- Truck
- Traffic light
- Person
- Car
- Backpack
- Handbag
- Motorcycle

The output contains bounding boxes, class labels, and confidence scores for the detected objects.

---

## 🔄 Project Workflow

```text
Input Image
     ↓
YOLOv5s Pretrained Model
     ↓
COCO128 Fine-Tuning
     ↓
Model Training
     ↓
best.pt
     ↓
New Image
     ↓
Object Detection
     ↓
Bounding Boxes
+ Class Labels
+ Confidence Scores



```

---

## 🛠️ Technologies Used

- Python
- PyTorch
- YOLOv5
- Google Colab
- CUDA
- Tesla T4 GPU
- COCO128 Dataset

---

## 📁 Project Files

```text
YOLOv5-Object-Detection/
│
├── OBJECT DETECTION USING YOLOv5.ipynb
└── README.md
```

---

## ⚠️ Limitations

1. COCO128 contains only 128 images and is relatively small for general-purpose model training.
2. The model was trained for only 5 epochs.
3. The same image directory was used for training and validation in the configured COCO128 setup.
4. The model is limited to the object categories available in the pretrained COCO classes.
5. The final street image was used for inference and was not part of the training dataset.

---

## 🚀 Future Scope

- Use a larger and more diverse dataset.
- Create a custom dataset with application-specific object classes.
- Train the model for more epochs.
- Use a separate independent test dataset.
- Perform hyperparameter optimization.
- Extend the system to real-time video object detection.
- Deploy the trained model in a web or mobile application.
- Improve detection of small and partially occluded objects.

---

## 📓 Notebook

The complete implementation is available in:

**`OBJECT DETECTION USING YOLOv5.ipynb`**

The notebook demonstrates the complete pipeline from YOLOv5 installation and dataset preparation to model training, evaluation, and final object detection.
