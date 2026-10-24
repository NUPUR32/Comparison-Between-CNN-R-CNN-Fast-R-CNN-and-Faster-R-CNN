# Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN
<div align="center">

# ⚡💜 CNN × R-CNN × FAST R-CNN × FASTER R-CNN 💜⚡

### 🔮 A NEON-STYLE COMPUTER VISION PROJECT 🔮

**Exploring the Evolution of Deep Learning-Based Object Detection**

<br>

[![Python](https://img.shields.io/badge/Python-3.10+-00F5FF?style=for-the-badge&logo=python&logoColor=black)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-FF00FF?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-00FF99?style=for-the-badge&logo=opencv&logoColor=black)](https://opencv.org/)
[![Google Colab](https://img.shields.io/badge/Google-Colab-00F5FF?style=for-the-badge&logo=googlecolab&logoColor=black)](https://colab.research.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-FF00FF?style=for-the-badge)](LICENSE)

<br>

**🔹 FOUR ARCHITECTURES · ONE COMPUTER VISION JOURNEY · ENDLESS POSSIBILITIES 🔹**

</div>

---

## 🌌 `01` — PROJECT VISION

> 💡 **Can we make object detection faster without sacrificing detection quality?**

This project explores the evolution of convolutional neural networks and region-based object detection architectures. It examines how CNN feature extraction, region proposals, shared feature maps, and learned proposal networks contribute to object detection.

The project covers four approaches:

| ⚡ Model | 🎯 Primary Focus |
|---|---|
| 🔵 **CNN** | Image classification and feature extraction |
| 🟣 **R-CNN** | Region-based object detection |
| 🟢 **Fast R-CNN** | Shared CNN features and RoI pooling |
| 🔴 **Faster R-CNN** | Integrated Region Proposal Network |

🎯 **Mission:** Understand the architecture, workflow, computational cost, and evaluation of each approach through Python-based experiments.

---

## 🧬 `02` — THE FOUR MODELS

### 🔵 01. CONVOLUTIONAL NEURAL NETWORK

**`FEATURE EXTRACTION → CLASSIFICATION`**

CNNs learn visual features such as edges, textures, shapes, and higher-level patterns using convolutional and pooling layers.

✨ **Key Features**
- 🧠 Learns hierarchical image representations.
- 🔍 Extracts spatial features.
- ⚡ Supports efficient image classification.
- 🧩 Can serve as the backbone of an object detector.

**Limitation:** A standard CNN classifier predicts image-level labels; it does not inherently generate object bounding boxes.

---

### 🟣 02. REGION-BASED CNN (R-CNN)

**`REGION PROPOSALS → CNN FEATURES → CLASSIFICATION`**

R-CNN identifies candidate regions in an image and processes each region using a CNN to extract features for object classification and bounding-box refinement.

✨ **Key Features**
- 🎯 Generates candidate object regions.
- 🔬 Extracts features from individual proposals.
- 📦 Supports bounding-box prediction.
- 🐢 Repeated feature extraction makes the original approach computationally expensive.

---

### 🟢 03. FAST R-CNN

**`SHARED FEATURES → RoI POOLING → DETECTION`**

Fast R-CNN processes the entire image through a CNN backbone and uses the resulting feature map for multiple region proposals.

✨ **Key Features**
- ⚡ Shares convolutional computation across proposals.
- 🧩 Uses RoI pooling to obtain fixed-size region features.
- 🎯 Predicts object classes and bounding-box offsets.
- 🚀 Reduces redundant computation compared with original R-CNN.

---

### 🔴 04. FASTER R-CNN

**`BACKBONE → REGION PROPOSAL NETWORK → RoI DETECTION`**

Faster R-CNN introduces a Region Proposal Network (RPN) that learns to generate candidate object regions using shared image features.

✨ **Key Features**
- 🤖 Learns region proposals through an RPN.
- 🔗 Shares features between proposal generation and detection.
- 📦 Predicts object classes and refines bounding boxes.
- ⚡ Avoids relying on external Selective Search during normal proposal generation.

---

## 📊 `03` — NEON MODEL COMPARISON

| ⚙️ Feature | 🔵 CNN | 🟣 R-CNN | 🟢 Fast R-CNN | 🔴 Faster R-CNN |
|---|---|---|---|---|
| Main task | Classification | Detection | Detection | Detection |
| Region proposals | Not required for classification | External | External | Learned RPN |
| Shared CNN features | Depends on architecture | ❌ | ✅ | ✅ |
| RoI pooling | Not required for standard classification | Original pipeline differs | ✅ | RoI-based feature extraction |
| Bounding boxes | Not in standard classifier | ✅ | ✅ | ✅ |
| Proposal generation learned | Not applicable | ❌ | ❌ | ✅ |
| Main strength | Feature learning | Region-based detection | Efficient feature reuse | Integrated proposal generation |

> ⚠️ **Fair-comparison rule:** CNN image-classification accuracy is not directly comparable to object-detection mAP. Use metrics appropriate to each task and clearly document the evaluation protocol.

---

## 🗂️ `04` — PROJECT ARCHITECTURE

```text
⚡ Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN
│
├── 🧠 CNN_Classification.ipynb
│   └── Image classification and CNN features
│
├── 🔍 R_CNN_Proposal.ipynb
│   └── Region proposal demonstration
│
├── ⚡ Fast_R_CNN_Proposal.ipynb
│   └── Region proposals and Fast R-CNN concepts
│
├── 🚀 Faster_R_CNN.ipynb
│   └── Faster R-CNN object detection
│
├── 📘 README.md
│   └── Project documentation
│
└── 📄 LICENSE
    └── MIT License
```

---

## 🗃️ `05` — DATASET: PASCAL VOC 2007

### 🌐 The Visual World in Data

This project is intended to use the **PASCAL VOC 2007** dataset for object-detection experiments.

📦 The dataset includes:
- 🖼️ Images containing real-world objects.
- 📍 Annotated object bounding boxes.
- 🏷️ Object-category labels.
- 🎯 Ground-truth annotations for model evaluation.

**Example categories:**

`🚗 Car` · `🚲 Bicycle` · `🐕 Dog` · `🐈 Cat` · `🧍 Person` · `🪑 Chair` · `🚌 Bus`

🔗 **Official Dataset:**  
https://www.robots.ox.ac.uk/~vgg/projects/pascal/VOC/voc2007/

📌 Dataset handling and use must comply with the applicable dataset terms.

---

## 🚀 `06` — LAUNCH YOUR EXPERIMENT

### 💻 Option A: Google Colab

Run the notebooks in a cloud-based Python environment.

| 🧪 Experiment | ▶️ Launch |
|---|---|
| 🔵 CNN Classification | [OPEN NOTEBOOK](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/CNN_Classification.ipynb) |
| 🟣 R-CNN Proposals | [OPEN NOTEBOOK](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/R_CNN_Proposal.ipynb) |
| 🟢 Fast R-CNN Proposals | [OPEN NOTEBOOK](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/Fast_R_CNN_Proposal.ipynb) |
| 🔴 Faster R-CNN | [OPEN NOTEBOOK](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/Faster_R_CNN.ipynb) |

**⚡ Execution steps**

1. Open a notebook in Colab.
2. Select **Runtime → Change runtime type**.
3. Select a GPU if available.
4. Run the cells in order.
5. Allow required datasets and pretrained weights to download.
6. Inspect the predictions, training output, and evaluation results.

⚠️ The R-CNN and Fast R-CNN notebooks are named proposal demonstrations. Confirm that they implement complete detectors before treating their outputs as full detection results.

### 🖥️ Option B: Run Locally

Clone the repository:

```bash
git clone https://github.com/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN.git
```

Enter the project directory:

```bash
cd Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN
```

Install the basic dependencies:

```bash
python -m pip install jupyter torch torchvision numpy matplotlib pillow opencv-contrib-python
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

📌 Install any additional dependencies required by the individual notebooks.

---

## 📈 `07` — PERFORMANCE LAB

### 🔬 What Should Be Compared?

| 📊 Metric | 🧾 Purpose |
|---|---|
| 🎯 Detection mAP | Measures object-detection performance |
| 📦 IoU | Measures overlap between predicted and ground-truth boxes |
| ⏱️ Inference time | Measures time taken to process an image |
| ⚡ Throughput | Measures images processed per second |
| 🧠 Training time | Records the time needed to train a model |
| 💾 Model size | Measures storage required for model weights |
| 🖥️ Resource usage | Records CPU/GPU memory consumption |

### 🧪 Experimental Rules

- Use the same dataset split for comparable detection models.
- Keep image preprocessing consistent.
- Record hardware, epochs, and hyperparameters.
- Use consistent IoU thresholds and mAP evaluation settings.
- Document whether timing includes preprocessing and region proposal generation.
- Separate classification metrics from detection metrics.
- Report actual experimental results rather than assumed values.

**No fabricated benchmarks. Only measured results.**

---

## 🌍 `08` — REAL-WORLD APPLICATIONS

| 🌟 Application | 💡 Use Case |
|---|---|
| 🚗 Autonomous Driving | Detecting vehicles, pedestrians, and road objects |
| 🛡️ Surveillance | Identifying objects in video frames |
| 🤖 Robotics | Recognizing and locating objects |
| 🏭 Industrial Inspection | Detecting products and defects |
| 🚦 Traffic Monitoring | Identifying road users |
| 🖼️ Image Understanding | Localizing objects in photographs |

---

## ⚠️ `09` — LIMITATIONS & FUTURE SCOPE

### Current Limitations
- Training performance depends on data, hyperparameters, and model implementation.
- Selective Search can add substantial processing overhead.
- Short training runs are not sufficient for reliable final benchmarks.
- Different tasks require different evaluation metrics.
- Proposal demonstrations alone do not establish full detector performance.

### 🚀 Future Enhancements
- 📊 Implement a consistent evaluation pipeline for all detection models.
- 🎯 Calculate mAP at documented IoU thresholds.
- ⏱️ Measure inference time on the same hardware.
- 📉 Visualize training and validation curves.
- 📦 Save trained model weights and evaluation summaries.
- 🧪 Expand experiments with different training configurations.

---

## 📚 `10` — RESEARCH REFERENCES

1. **R-CNN** — Girshick et al., *Rich Feature Hierarchies for Accurate Object Detection and Semantic Segmentation*, CVPR 2014.
2. **Fast R-CNN** — Ross Girshick, *Fast R-CNN*, ICCV 2015.  
   https://openaccess.thecvf.com/content_iccv_2015/html/Girshick_Fast_R-CNN_ICCV_2015_paper.html
3. **Faster R-CNN** — Ren et al., *Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks*, NeurIPS 2015.
4. **PASCAL VOC 2007** — Official dataset documentation.  
   https://www.robots.ox.ac.uk/~vgg/projects/pascal/VOC/voc2007/

---

## 👩‍💻 `11` — PROJECT AUTHOR

<div align="center">

### 💜 NUPUR

**Computer Science & Engineering | Deep Learning | Computer Vision**

[![GitHub](https://img.shields.io/badge/GitHub-NUPUR32-FF00FF?style=for-the-badge&logo=github&logoColor=white)](https://github.com/NUPUR32)

</div>

---

## 📄 `12` — LICENSE

This project is licensed under the **MIT License**.

See the [`LICENSE`](LICENSE) file for details.

---

<div align="center">

### ⚡ THINK DEEPER. DETECT SMARTER. BUILD BETTER. ⚡

**💜 Built with Python · PyTorch · OpenCV · Google Colab 💜**

⭐ If you find this project useful, consider giving the repository a star!

</div>
