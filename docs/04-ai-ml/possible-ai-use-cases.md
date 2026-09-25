# Possible AI and Machine Learning Use Cases

## 1. What It Is
This document outlines the hypothetical applications of machine learning, deep neural networks, and classical computer vision algorithms across the sensing, cutting, quality verification, and maintenance workflows of the smart mulberry cutting machine.

## 2. Why It Matters
AI must not be introduced arbitrarily. Each candidate application must be evaluated against classical mechanical and algorithmic alternatives to determine if machine learning adds measurable value, efficiency, or biosecurity beyond deterministic approaches.

## 3. Key Concepts & Candidate Use Cases Matrix

*(Note: All use cases listed below are proposed research directions and must be experimentally validated before declaring feasibility or technical superiority).*

| Use case | Input | Possible model | Output | Dataset required | Validation |
|---|---|---|---|---|---|
| **1. Mulberry Leaf Detection** | RGB camera feed of intake conveyor | Lightweight detector (e.g., YOLO-nano, MobileNet-SSD, or Classical HSV Color Masking) | Bounding box / binary segmentation mask of leaf biomass | 2,000+ labeled images of mulberry leaves on conveyor belt under varied lighting | Precision/Recall vs. ground-truth manual labels; inference latency on target SBC |
| **2. Leaf vs. Stem Classification** | Cropped optical ROI of feed stream | Binary/Multi-class CNN (MobileNetV3, SqueezeNet, or SVM on GLCM texture features) | Classification label: Leaf Lamina vs. Tender Shoot vs. Woody Stem | 5,000+ categorized image crops of leaves, petioles, and stems | Cross-entropy loss, Confusion matrix, F1-score across cultivars (V-1, S-36) |
| **3. Size & Geometry Estimation** | Calibrated top-down RGB image | Contour analysis, Convex Hull (Classical CV) or Instance Segmentation (YOLO-seg, Mask R-CNN) | Leaf surface area ($cm^2$), stem diameter ($mm$), length ($mm$) | 1,000 calibrated images paired with caliper and planimeter measurements | Mean Absolute Error (MAE) in millimeters compared to physical caliper readings |
| **4. Quality Assessment (Tenderness / Age)** | RGB / Multispectral imagery (color, gloss, vein density) | Multi-class CNN, ResNet-18, or Spectral Ratio Index ($R_{NIR}/R_{Red}$) | Maturity grade: Chawki-grade (Tender) vs. Semi-mature vs. Coarse mature | 3,000 annotated images linked with leaf position (node 1–15) and moisture lab tests | Correlation with laboratory oven-dry moisture % and leaf protein content |
| **5. Material Condition / Defect Detection** | RGB images of leaf dorsal and ventral surfaces | Object detection / Patch classifier (YOLOv8, Vision Transformer ViT-tiny, or UNet) | Defect flags: Leaf spot, Tukra, Powdery mildew, Dust, Soil contamination | 4,000+ images of diseased leaves and clean controls across growth stages | ROC-AUC, False Positive Rate (minimizing healthy leaf rejection) |
| **6. Cutting-Quality Prediction** | Optical macro-images of cut leaf edges | High-resolution CNN feature extractor or Classical edge roughness metrics | Cut quality index: Clean shear vs. Crushed/Torn margin percentage | 1,500 macro-photographs of cut edges paired with microscopical bruise assessments | Verification against microscopic cellular leakage staining (Evan's Blue dye) |
| **7. Blade Degradation Detection** | Accelerometer (vibration) + Current sensor + Audio mic time-series | 1D-CNN, LSTM, Random Forest, or Spectral Kurtosis / FFT Peak Tracking | Estimated tool health (% remaining life, "Sharp", "Worn", "Replace") | 200+ hours of synchronized sensor recordings across fresh, worn, and chipped blades | Predictive accuracy vs. physical microscope blade profile measurements |
| **8. Foreign Object / Anomaly Detection** | Intake camera + Inductive metal proximity sensor | Autoencoder (anomaly detection), One-Class SVM, or YOLO object detector | Binary alert: Normal biomass vs. Foreign hazard (stone, wire, nail, plastic) | Unsupervised normal biomass images + test sets containing common farm debris | Detection rate (100% target for metal/stones) and false alarm frequency |

## 4. Engineering Relevance
- **Edge Deployment Constraint**: All candidate models must run locally on embedded hardware with power budgets < 15W and memory limits < 4GB RAM.
- **Hierarchical Decision Strategy**: Simple, deterministic thresholding (e.g., current limit for jam detection) should be executed first in firmware (microsecond latency); complex deep learning (e.g., disease detection) runs asynchronously without blocking mechanical cutting.

## 5. Questions to Investigate
- Does leaf size estimation need deep learning, or does classical Otsu thresholding and contour hierarchy achieve identical accuracy at 1/10th the compute power?
- Can acoustic blade degradation detection function reliably amid the background mechanical noise of motors, gearboxes, and bearings?
- What is the false-positive rejection rate of disease-detection models on dusty but otherwise healthy leaves?

## 6. Sources
1. Goodfellow, I., Bengio, Y., and Courville, A. (2016). *Deep Learning*, MIT Press.
2. Li, Y., et al. (2021). *Agricultural robotics and machine vision: A review*, Computers and Electronics in Agriculture.
3. Central Silk Board (CSB), *Technical Reports on Automation Feasibility in Sericulture*.
