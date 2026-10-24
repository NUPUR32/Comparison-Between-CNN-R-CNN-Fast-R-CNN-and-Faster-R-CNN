<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:050014,50:6A00F5,100:00F5FF&height=220&section=header&text=OBJECT%20DETECTION&fontSize=42&fontColor=FFFFFF&animation=fadeIn&fontAlignY=38&desc=Comparative%20Deep%20Learning%20Study&descAlignY=58&descSize=18" width="100%" />

# ⚡ Comparative Performance Evaluation of CNN, R-CNN, Fast R-CNN, and Faster R-CNN

### An Experimental Study Using the PASCAL VOC 2007 Dataset

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=17&duration=2800&pause=900&color=00F5FF&center=true&vCenter=true&width=750&lines=Exploring+the+Evolution+of+Object+Detection;CNN+%7C+R-CNN+%7C+Fast+R-CNN+%7C+Faster+R-CNN;Accuracy+%7C+Efficiency+%7C+Computational+Cost" alt="Animated project description" />

<br>

<img src="https://img.shields.io/badge/Python-3.10%2B-00F5FF?style=for-the-badge&logo=python&logoColor=black" />
<img src="https://img.shields.io/badge/PyTorch-Deep%20Learning-FF4B4B?style=for-the-badge&logo=pytorch&logoColor=white" />
<img src="https://img.shields.io/badge/Dataset-PASCAL%20VOC%202007-9D4EDD?style=for-the-badge" />
<img src="https://img.shields.io/badge/Platform-Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=black" />

<br><br>

**A comparative study of deep learning architectures, focusing on feature extraction, region proposals, detection performance, and computational efficiency.**

</div>

---

## 🌌 Project Overview

Object detection is a fundamental computer vision task that identifies objects in an image and determines their locations using bounding boxes.

This project investigates the development of deep learning-based vision systems through four approaches:

- **CNN (Convolutional Neural Network)**
- **R-CNN (Region-based Convolutional Neural Network)**
- **Fast R-CNN**
- **Faster R-CNN**

Using the **PASCAL VOC 2007 dataset**, the project explores the differences between image classification and object detection, the evolution of region-proposal techniques, and the trade-offs between detection performance and computational cost.

The goal is to establish a structured experimental comparison and understand how each approach handles visual feature extraction, candidate-region processing, and object localization.

## 🎯 Project Objectives

- 🧠 Understand the architecture and working principles of four CNN-based approaches.
- 🖼️ Explore image classification, region proposals, and bounding-box prediction.
- 📦 Use PASCAL VOC 2007 as the common dataset for the experiments.
- 🎯 Examine object localization and class prediction.
- ⚡ Compare computational requirements and inference speed where measurements are available.
- 📊 Evaluate suitable performance metrics and organize the results for comparison.
- 🔬 Understand the evolution from conventional CNN-based methods to region-proposal networks.

---

## 🧬 Models Under Investigation

### 1. CNN — Convolutional Neural Network

CNNs learn hierarchical visual features from images using convolutional layers, activation functions, and pooling operations.

In a conventional image-classification setup, a CNN predicts image-level classes. It does not automatically produce object bounding boxes unless it is extended with an object-detection architecture.

**Key characteristics:**
- Learns spatial and visual features.
- Uses convolutional filters to extract image representations.
- Can perform image classification.
- Serves as a foundation for many object-detection systems.

### 2. R-CNN — Region-based CNN

R-CNN generates candidate object regions, extracts each region, and processes the proposals through a CNN to obtain features for classification.

**Key characteristics:**
- Uses region proposals, traditionally generated using Selective Search.
- Extracts CNN features for individual candidate regions.
- Performs classification and bounding-box refinement.
- Requires substantial computation because proposals are processed separately.

### 3. Fast R-CNN

Fast R-CNN improves the original R-CNN approach by processing the complete image through a CNN and extracting region-specific features from a shared feature map.

**Key characteristics:**
- Computes convolutional features once per image.
- Uses RoI Pooling to obtain fixed-size region features.
- Performs classification and bounding-box regression.
- Reduces redundant convolutional computation.
- Still relies on an external region-proposal method in its original form.

### 4. Faster R-CNN

Faster R-CNN introduces a **Region Proposal Network (RPN)** that learns to generate candidate object regions using shared convolutional features.

**Key characteristics:**
- Integrates region-proposal generation into the detection framework.
- Shares convolutional features between the RPN and detection network.
- Predicts object classes and refines bounding boxes.
- Reduces dependence on external region-proposal algorithms.
- Provides an end-to-end trainable two-stage object-detection architecture.

---

## 📊 Architecture Comparison

| Feature | CNN Classifier | R-CNN | Fast R-CNN | Faster R-CNN |
|---|---|---|---|---|
| Primary purpose | Image classification | Object detection | Object detection | Object detection |
| Region proposals | Not required for classification | External proposals | External proposals | Learned using RPN |
| Feature extraction | CNN | CNN per proposal | Shared CNN feature map | Shared CNN feature map |
| RoI-based processing | Not in a conventional classifier | Region-wise CNN processing | RoI Pooling | RoI-based detection |
| Bounding-box prediction | Not in a conventional classifier | Yes | Yes | Yes |
| Main advantage | Simple feature learning | Introduces CNN-based region detection | Reduces repeated feature extraction | Learns region proposals |
| Main limitation | Does not localize objects by default | High computational cost | External proposal generation | More complex architecture |

> **Important:** A conventional CNN classifier is not directly equivalent to an object detector. Detection metrics such as mAP should only be compared when the CNN baseline includes a suitable detection and localization mechanism. Document any differences in model configuration when reporting results.

---

## 🗂️ Dataset — PASCAL VOC 2007

The experiments use the **PASCAL Visual Object Classes (VOC) 2007 dataset**, a widely used benchmark for object recognition and detection.

The dataset provides images and annotations containing object classes and bounding-box coordinates.

### Dataset Details

| Property | Description |
|---|---|
| Dataset | PASCAL VOC 2007 |
| Task | Object recognition and detection |
| Annotation format | XML |
| Object localization | Bounding boxes |
| Number of object categories | 20 |
| Common benchmark splits | Train, validation, and test |
| Typical image content | Images containing one or more annotated objects |

### Object Categories

The 20 categories are:

`aeroplane`, `bicycle`, `bird`, `boat`, `bottle`, `bus`, `car`, `cat`, `chair`, `cow`, `diningtable`, `dog`, `horse`, `motorbike`, `person`, `pottedplant`, `sheep`, `sofa`, `train`, and `tvmonitor`.

### Dataset Preparation

The typical workflow involves:

1. Downloading the VOC 2007 images and annotations.
2. Reading image files and their corresponding XML annotations.
3. Extracting class labels and bounding-box coordinates.
4. Preparing training and evaluation data.
5. Applying the transformations required by each model.
6. Visualizing sample images and ground-truth bounding boxes.

**Official dataset information:** [PASCAL VOC](http://host.robots.ox.ac.uk/pascal/VOC/)

---

## 🧪 Experimental Methodology

The project follows a structured workflow to make the experiments easier to reproduce and understand.

```text
              PASCAL VOC 2007
                     |
                     v
           Dataset Preparation
                     |
                     v
          Image and XML Processing
                     |
                     v
       +-------------+-------------+
       |             |             |
       v             v             v
   CNN Baseline    R-CNN       Fast R-CNN
       |             |             |
       |             |             |
       +-------------+-------------+
                     |
                     v
                Faster R-CNN
                     |
                     v
          Evaluation and Analysis
                     |
                     v
          Comparative Results
```

### Experimental Steps

**Step 1 — Dataset preparation**

Load images and annotations, validate bounding boxes, and establish consistent data splits.

**Step 2 — Model implementation**

Set up the required architecture and preprocessing pipeline for each approach.

**Step 3 — Training**

Train the applicable models using the selected training split and documented hyperparameters.

**Step 4 — Prediction**

Generate class predictions and, for detection models, predicted bounding boxes.

**Step 5 — Evaluation**

Measure appropriate performance metrics using the same evaluation split wherever possible.

**Step 6 — Comparison**

Organize the results into tables and plots to examine accuracy, localization quality, inference speed, and computational requirements.

---

## 📈 Evaluation Metrics

The following metrics can be used to assess the models. Actual values should be added after running the experiments.

| Metric | Purpose |
|---|---|
| Classification Accuracy | Measures the proportion of correctly classified examples when classification accuracy is appropriate for the task. |
| Mean Average Precision (mAP) | Evaluates object-detection performance across classes using precision-recall information. |
| Intersection over Union (IoU) | Measures the overlap between a predicted bounding box and its ground-truth box. |
| Inference Time | Measures the time needed to produce a prediction for an image. |
| Throughput | Measures the number of images processed per second. |
| Model Size | Measures the storage required for model weights. |
| Training Time | Measures the time needed to train a model under the specified experimental setup. |

### Recommended Comparison Table

Populate this table with measured results from your notebooks.

| Model | Evaluation Metric | Inference Time | Model Size | Notes |
|---|---|---|---|---|
| CNN | To be measured | To be measured | To be measured | Classification baseline or detection variant |
| R-CNN | To be measured | To be measured | To be measured | Depends on proposal count and feature extraction |
| Fast R-CNN | To be measured | To be measured | To be measured | Depends on external region proposals |
| Faster R-CNN | To be measured | To be measured | To be measured | Uses an RPN |

**Fair-comparison requirements:**
- Use consistent dataset splits.
- Document image sizes, proposal counts, and confidence thresholds.
- Record hardware and software configurations.
- Use an appropriate detection metric when comparing object detectors.
- Distinguish measured results from theoretical expectations.
- Do not report unmeasured values as experimental findings.

---

## 💻 Technology Stack

| Technology | Purpose |
|---|---|
| Python | Programming language |
| PyTorch | Deep learning and model training |
| OpenCV | Image processing and Selective Search, where available |
| NumPy | Numerical operations |
| Matplotlib | Visualization and plotting |
| XML parsing | Reading PASCAL VOC annotations |
| Google Colab | Cloud-based experimentation |
| Git and GitHub | Version control and project hosting |

The exact dependencies may differ between notebooks. Install the libraries required by the notebook you intend to run.

---

## 📁 Repository Structure

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

Each notebook contains the implementation or experimental workflow associated with its corresponding approach.

---

## 🚀 Run the Project

### Option 1 — Google Colab

Google Colab allows you to run the notebooks in a browser without setting up a complete local deep learning environment.

Open the notebooks:

| Notebook | Open in Colab |
|---|---|
| CNN Classification | [Open Notebook](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/CNN_Classification.ipynb) |
| R-CNN | [Open Notebook](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/R_CNN_Proposal.ipynb) |
| Fast R-CNN | [Open Notebook](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/Fast_R_CNN_Proposal.ipynb) |
| Faster R-CNN | [Open Notebook](https://colab.research.google.com/github/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN/blob/main/Faster_R_CNN.ipynb) |

**Steps:**

1. Open the notebook you want to run.
2. Select **Runtime → Change runtime type**.
3. Choose a GPU runtime if available and suitable.
4. Run the notebook cells in order.
5. Allow the dataset and required model weights to download.
6. Review the training logs, predictions, and evaluation results.

> Runtime availability, package compatibility, download permissions, and execution time may vary. Check the installation cells in each notebook before running it.

### Option 2 — Run Locally

Clone the repository:

```bash
git clone https://github.com/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN.git
```

Move into the project directory:

```bash
cd Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Install the required libraries according to the selected notebook. For example:

```bash
pip install torch torchvision numpy matplotlib opencv-contrib-python-headless
```

Install Jupyter if needed:

```bash
pip install notebook
jupyter notebook
```

Some notebooks may require additional dependencies. Follow their installation cells and verify compatibility with your Python and PyTorch versions.

---

## 🖼️ Expected Outputs

Depending on the implementation, the notebooks may produce:

- Training and validation loss plots.
- Classification predictions.
- Object-detection bounding boxes.
- Predicted class labels and confidence scores.
- Evaluation metrics.
- Inference-time measurements.
- Comparative tables and graphs.

Add representative screenshots of actual outputs to your repository once the experiments are complete.

---

## 🔍 Key Research Questions

This project is designed to investigate the following questions:

1. How does the original R-CNN approach differ from Fast R-CNN in feature extraction?
2. How does Faster R-CNN improve region-proposal generation?
3. What trade-offs exist between model complexity and inference speed?
4. How do region-proposal strategies affect the object-detection pipeline?
5. Which metrics are suitable for comparing classification and detection models?
6. How do implementation choices and experimental settings influence the observed results?

---

## 🏁 Conclusion

This project studies four approaches to visual recognition and object detection, from conventional CNN-based classification to region-based detection architectures.

By examining R-CNN, Fast R-CNN, and Faster R-CNN on a common benchmark, the project highlights the progression toward shared feature extraction and learned region proposals.

The final conclusions should be based on the measured experimental results, including the selected evaluation metrics, runtime, and computational setup.

---

## 🔮 Future Scope

Potential extensions include:

- Testing on additional object-detection datasets.
- Comparing additional backbone networks.
- Evaluating detection performance at different IoU thresholds.
- Measuring GPU memory usage and inference throughput.
- Experimenting with different input resolutions and proposal counts.
- Adding precision-recall curves and per-class average precision.
- Comparing two-stage detectors with modern one-stage approaches such as YOLO.

---

## 👩‍💻 Project Information

**Project Title:** Comparative Performance Evaluation of CNN, R-CNN, Fast R-CNN, and Faster R-CNN  
**Dataset:** PASCAL VOC 2007  
**Domain:** Deep Learning and Computer Vision  
**Platform:** Google Colab / Python  
**Repository:** [View on GitHub](https://github.com/NUPUR32/Comparison-Between-CNN-R-CNN-Fast-R-CNN-and-Faster-R-CNN)

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:050014,50:6A00F5,100:00F5FF&height=120&section=footer" width="100%" />

### ✨ Turning Images into Insights with Deep Learning ✨

*Explore. Experiment. Evaluate. Improve.*

</div>
