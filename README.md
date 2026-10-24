<div align="center">

<!-- ANIMATED NEON HEADER -->

<img src="https://readme-typing-svg.demolab.com?font=Orbitron&weight=800&size=27&duration=2500&pause=700&color=00F7FF&center=true&vCenter=true&width=850&lines=⚡+COMPUTER+VISION+PROJECT+⚡;CNN+%7C+R-CNN+%7C+FAST+R-CNN;FASTER+R-CNN+%7C+OBJECT+DETECTION;ENTER+THE+NEURAL+NETWORK+UNIVERSE" alt="Animated project title" />

<br/>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:09001A,50:17002F,100:001F3F&height=5&section=header" width="100%" alt="Neon divider"/>

### 💠 DEEP LEARNING × COMPUTER VISION × OBJECT DETECTION 💠

**Understanding the evolution of object detection through four neural-network approaches.**

<br/>

[![Python](https://img.shields.io/badge/Python-3.10%2B-00F7FF?style=for-the-badge&logo=python&logoColor=black)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-FF00FF?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-00FF99?style=for-the-badge&logo=opencv&logoColor=black)](https://opencv.org/)
[![Colab](https://img.shields.io/badge/Google-Colab-00F7FF?style=for-the-badge&logo=googlecolab&logoColor=black)](https://colab.research.google.com/)
[![License](https://img.shields.io/badge/License-MIT-FF00FF?style=for-the-badge)](LICENSE)

<br/>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:001F3F,50:4B0082,100:09001A&height=5&section=header" width="100%" alt="Neon divider"/>

### 🔴 SYSTEM STATUS: EXPLORING THE FUTURE OF OBJECT DETECTION 🔵

</div>

---

# 🌌 `01 // PROJECT OVERVIEW`

## ⚡ Welcome to the Neural Vision Lab

Computer vision enables machines to understand and interpret visual information. From identifying everyday objects to locating vehicles and pedestrians, deep learning has transformed the way computers analyze images.

This project explores four important approaches:

- 🔵 **CNN** — Convolutional Neural Network
- 🟣 **R-CNN** — Region-Based Convolutional Neural Network
- 🟢 **Fast R-CNN** — An improved region-based detection approach
- 🔴 **Faster R-CNN** — An object detector with a learned Region Proposal Network

The project focuses on understanding their architectures, feature-extraction strategies, region-proposal mechanisms, computational costs, and evaluation methods.

> 💡 **Core research question:** How does integrating region proposals and sharing convolutional features affect the efficiency and performance of object detection?

### 🎯 Project Mission

Our objectives are to:

- 🧠 Understand convolutional feature extraction.
- 🔍 Explore region proposal generation.
- 📦 Understand bounding-box prediction and object localization.
- ⚡ Study computational improvements across region-based detectors.
- 🧪 Experiment with PASCAL VOC 2007.
- 📊 Record meaningful model-performance measurements.
- 🔬 Understand the trade-offs between computational efficiency and detection quality.
- 🚀 Build a foundation for more advanced computer vision systems.

---

# 🧬 `02 // FOUR NEURAL NETWORK APPROACHES`

## 🔵 MODEL 01 — CONVOLUTIONAL NEURAL NETWORK

### `IMAGE → FEATURE EXTRACTION → CLASSIFICATION`

A Convolutional Neural Network learns spatial patterns from images using convolutional filters, nonlinear activation functions, and pooling operations.

Early layers may identify edges and textures, while deeper layers learn increasingly complex visual representations.

**⚙️ Architecture components**

1. **Convolutional layers:** Extract visual features.
2. **Activation functions:** Introduce nonlinear learning.
3. **Pooling layers:** Reduce spatial dimensions.
4. **Fully connected or classification layers:** Produce class predictions.

**✨ Advantages**

- Effective visual feature learning.
- Supports image classification.
- Can provide a backbone for object-detection systems.
- Offers a relatively straightforward starting point for computer vision experiments.

**⚠️ Limitations**

A standard CNN classifier does not inherently generate bounding boxes. Object detection requires additional components for localization and classification.

**🌍 Applications:** Image recognition, image categorization, medical-image analysis, and feature extraction.

---

## 🟣 MODEL 02 — REGION-BASED CNN (R-CNN)

### `IMAGE → REGION PROPOSALS → CNN FEATURES → CLASSIFICATION`

R-CNN approaches object detection by identifying candidate regions that may contain objects and extracting CNN features from each candidate region.

The extracted features are then used to classify objects, with bounding-box refinement improving localization.

**⚙️ Workflow**

1. Receive an input image.
2. Generate candidate regions, commonly using Selective Search.
3. Prepare the proposed regions for CNN processing.
4. Extract features from each region.
5. Classify regions and refine bounding boxes.

**✨ Advantages**

- Introduces region-based object detection.
- Predicts object categories and locations.
- Provides an important foundation for later region-based detectors.

**⚠️ Limitations**

The original R-CNN pipeline repeatedly computes CNN features for different regions. This creates significant computational overhead and makes training and inference slower.

**🌍 Applications:** Object localization, image understanding, and research into region-based detection.

---

## 🟢 MODEL 03 — FAST R-CNN

### `IMAGE → SHARED FEATURE MAP → RoI POOLING → DETECTION`

Fast R-CNN improves on the original R-CNN approach by computing convolutional features for the entire image and sharing them across region proposals.

RoI pooling extracts fixed-size features from proposed regions, enabling classification and bounding-box regression.

**⚙️ Workflow**

1. Pass the complete image through a CNN backbone.
2. Generate candidate object regions.
3. Map the candidate regions onto the feature map.
4. Apply RoI pooling to obtain fixed-size features.
5. Predict object classes and bounding-box offsets.

**✨ Advantages**

- Shares convolutional computation across proposals.
- Reduces redundant feature extraction.
- Supports classification and localization in a unified network.
- Improves computational efficiency compared with original R-CNN.

**⚠️ Limitations**

The original Fast R-CNN pipeline relies on an external region-proposal algorithm such as Selective Search. Proposal generation can remain a significant source of latency.

**🌍 Applications:** Region-based object detection and efficient feature reuse.

---

## 🔴 MODEL 04 — FASTER R-CNN

### `IMAGE → CNN BACKBONE → RPN → RoI FEATURES → DETECTIONS`

Faster R-CNN introduces a Region Proposal Network (RPN), which learns to identify candidate object regions using convolutional features.

The proposal network and detection network share image features, integrating proposal generation into the overall architecture.

**⚙️ Workflow**

1. Extract feature maps from the input image.
2. Generate candidate regions using the RPN.
3. Score candidate proposals and refine their coordinates.
4. Extract region features through RoI-based operations.
5. Predict object categories.
6. Refine bounding boxes to improve localization.

**✨ Advantages**

- Learns region proposals instead of depending on external Selective Search.
- Shares features between proposal generation and detection.
- Supports object classification and localization.
- Provides an integrated architecture for object detection.

**⚠️ Limitations**

- Requires more complex architecture and training.
- Computational demands depend on backbone, image size, and proposal settings.
- Performance depends on training data, hyperparameters, and evaluation conditions.

**🌍 Applications:** Autonomous driving research, object localization, robotics, and image understanding.

---

# 📊 `03 // NEON COMPARISON MATRIX`

| ⚙️ Feature | 🔵 CNN | 🟣 R-CNN | 🟢 Fast R-CNN | 🔴 Faster R-CNN |
|---|---|---|---|---|
| Primary task | Classification | Detection | Detection | Detection |
| Region proposals | Not needed for standard classification | External | External | Learned RPN |
| Feature extraction | Whole image | Repeated for regions | Shared feature map | Shared feature map |
| RoI pooling | Not required for standard classification | Original pipeline differs | Yes | RoI-based feature extraction |
| Bounding-box prediction | Not in standard classifier | Yes | Yes | Yes |
| Proposal generation learned | Not applicable | No | No | Yes |
| Redundant CNN computation | Architecture-dependent | High | Reduced | Reduced |
| Main advantage | Feature learning | Region-based detection | Shared feature computation | Integrated proposal generation |
| Main limitation | No localization in standard classifier | Computational overhead | External proposals | More complex detector |

### 🧠 Understanding the Evolution

**CNN → R-CNN → Fast R-CNN → Faster R-CNN**

- 🔵 **CNN:** Learns features from images.
- 🟣 **R-CNN:** Applies CNN features to candidate regions.
- 🟢 **Fast R-CNN:** Shares convolutional features across regions.
- 🔴 **Faster R-CNN:** Learns region proposals with an RPN.

This progression illustrates how object-detection research sought to reduce redundant computation while retaining the ability to classify and localize objects.

> ⚠️ A CNN classification score cannot be fairly compared directly with detection mAP. For a valid experiment, evaluate classification and object detection using appropriate metrics.

---

# 🗂️ `04 // PROJECT STRUCTURE`

```text
Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/
│
├── CNN_Classification.ipynb
├── R_CNN_Proposal.ipynb
├── Fast_R_CNN_Proposal.ipynb
├── Faster_R_CNN.ipynb
├── README.md
└── LICENSE
```

📌 The structure above intentionally excludes a `pic` folder.

---

# 🗃️ `05 // DATASET — PASCAL VOC 2007`

## 🌐 A Benchmark for Visual Recognition

The PASCAL VOC 2007 dataset is used for object-recognition and detection experiments.

It includes images with object-category labels and bounding-box annotations.

### 🏷️ Example categories

🚗 Car · 🚲 Bicycle · 🐕 Dog · 🐈 Cat · 🧍 Person · 🪑 Chair · 🚌 Bus · 🍾 Bottle

### 📦 Dataset preparation

1. Download or load the dataset.
2. Read the image annotations.
3. Extract object labels and bounding-box coordinates.
4. Prepare images for the relevant model.
5. Run training or inference.
6. Compare predictions with ground-truth annotations.

🔗 **Official dataset documentation:**  
https://www.robots.ox.ac.uk/~vgg/projects/pascal/VOC/voc2007/

⚠️ Follow the dataset's applicable usage terms. Do not upload the full dataset to GitHub unless permitted.

---

# 🚀 `06 // EXECUTION GUIDE`

## 💻 Option A — Google Colab

| 🧪 Model | ▶️ Open Notebook |
|---|---|
| 🔵 CNN Classification | [Launch CNN](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/CNN_Classification.ipynb) |
| 🟣 R-CNN Proposals | [Launch R-CNN](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/R_CNN_Proposal.ipynb) |
| 🟢 Fast R-CNN Proposals | [Launch Fast R-CNN](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/Fast_R_CNN_Proposal.ipynb) |
| 🔴 Faster R-CNN | [Launch Faster R-CNN](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/Faster_R_CNN.ipynb) |

### ⚡ Steps

1. Open the required notebook.
2. Select **Runtime → Change runtime type**.
3. Select a GPU if available.
4. Run the cells in order.
5. Wait for dependencies, dataset files, and pretrained weights to load.
6. Inspect the model outputs and evaluation results.

## 🖥️ Option B — Local Environment

Clone the repository:

```bash
git clone https://github.com/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN.git
cd Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN
```

Install basic dependencies:

```bash
python -m pip install jupyter torch torchvision numpy matplotlib pillow opencv-contrib-python
```

Launch Jupyter:

```bash
jupyter notebook
```

Use a PyTorch installation compatible with your hardware and CUDA configuration.

---

# 📈 `07 // PERFORMANCE & EVALUATION LAB`

## 🔬 What Should Be Measured?

| 📊 Metric | 💡 Meaning |
|---|---|
| 🎯 Detection mAP | Evaluates object-detection quality |
| 📦 IoU | Measures overlap between predicted and ground-truth boxes |
| ⏱️ Inference time | Measures processing time per image |
| ⚡ Throughput | Measures images processed per second |
| 🧠 Training time | Measures total training duration |
| 💾 Model size | Measures storage occupied by weights |
| 🖥️ Resource consumption | Records CPU/GPU memory usage |

### 🧪 Experimental protocol

For a meaningful comparison:

- Use the same dataset split for comparable detectors.
- Keep preprocessing consistent.
- Record training epochs and hyperparameters.
- Document the hardware and software environment.
- Use consistent IoU thresholds and mAP evaluation settings.
- Record whether timing includes proposal generation and preprocessing.
- Clearly separate image classification metrics from detection metrics.
- Report only measurements actually produced by the experiments.

### 📌 Results table template

| Model | Evaluation task | Metric | Measured result |
|---|---|---|---|
| CNN | Classification | Accuracy | Add measured value |
| R-CNN | Object detection | mAP | Add measured value |
| Fast R-CNN | Object detection | mAP | Add measured value |
| Faster R-CNN | Object detection | mAP | Add measured value |

**Do not fill this table with estimated results.** The metric and evaluation protocol should be documented for every model.

---

# 🌍 `08 // REAL-WORLD APPLICATIONS`

### 🚗 Autonomous Driving
Detecting vehicles, pedestrians, and other road objects.

### 🛡️ Surveillance
Identifying objects and tracking visual activity.

### 🤖 Robotics
Recognizing objects and locating them in the environment.

### 🏭 Industrial Inspection
Identifying products, components, and possible defects.

### 🚦 Traffic Monitoring
Detecting road users and analyzing traffic scenes.

### 🖼️ Image Understanding
Locating objects and interpreting visual content.

---

# 🔮 `09 // FUTURE SCOPE`

Potential improvements include:

- 📊 Building a unified object-detection evaluation pipeline.
- 🎯 Computing mAP at documented IoU thresholds.
- ⏱️ Measuring inference time under consistent conditions.
- 📉 Plotting training and validation curves.
- 📦 Saving model checkpoints and result files.
- 🧪 Testing different backbones and hyperparameters.
- 🚀 Comparing additional object-detection architectures.
- 📚 Documenting reproducible experiments and limitations.

---

# 📚 `10 // RESEARCH REFERENCES`

1. **R-CNN:** Girshick et al., *Rich Feature Hierarchies for Accurate Object Detection
