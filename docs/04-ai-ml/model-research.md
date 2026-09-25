# Model Architecture Research and Trade-Offs

## 1. What It Is
Model architecture research evaluates candidate computational algorithms—ranging from classical image processing pipelines and shallow statistical classifiers to modern convolutional neural networks (CNNs), YOLO object detectors, and Vision Transformers (ViTs)—for potential deployment in the smart cutting machine.

## 2. Why It Matters
Deploying an excessively complex neural network increases system cost, power consumption, latency, and thermal footprint, potentially requiring expensive GPU coprocessors that make the machine economically inaccessible to sericulturists. Conversely, overly simplistic models may fail under variable farm lighting or novel leaf orientations.

## 3. Key Concepts & Architecture Trade-Offs

### Candidate Algorithmic Families

| Model Family / Algorithm | Computational Complexity | Latency on Edge CPU (e.g., RPi 4/5) | Strengths | Limitations | Candidate Project Application |
|---|---|---|---|---|---|
| **Classical CV (Otsu, Canny, Contours, HSV)** | Ultra-Low (Few MFLOPs) | 5 – 15 ms (ARM CPU) | Zero training required; explainable; deterministic; runs on ultra-cheap microcontrollers. | Fragile under variable ambient lighting and shadows; cannot classify subtle diseases. | Particle cut length measurement; basic conveyor occupancy detection. |
| **Lightweight CNN Classifiers (MobileNetV3, SqueezeNet)** | Low (0.2–0.5 GFLOPs) | 15 – 30 ms (INT8 CPU) | Highly efficient; small memory footprint (< 15 MB); robust feature representation. | Whole-image classification; lacks precise spatial bounding boxes without sliding windows. | Leaf maturity grading (Chawki vs. Late-age); bulk disease presence flag. |
| **Real-Time Object Detectors (YOLO-nano, EfficientDet-Lite)** | Moderate (1.5–5 GFLOPs) | 30 – 70 ms (CPU) / 8–15 ms (with NPU) | Simultaneous localization and classification of multiple leaves, stems, and debris. | Requires annotated bounding box datasets; higher memory and thermal load. | Multi-object leaf/stem detection; foreign debris and hazard identification. |
| **Instance Segmentation (YOLO-seg, Fast-SAM)** | Moderate-High (10–25 GFLOPs) | 80 – 200 ms (CPU) / 20–40 ms (NPU) | Pixel-accurate boundary masks; exact surface area and stem diameter calculation. | High computational overhead; requires fine-grained polygon training labels. | Precision biomass density estimation; complex stem-geometry mapping. |
| **Vision Transformers (ViT-tiny, MobileViT)** | High (5–15 GFLOPs) | 60 – 150 ms (CPU) | Superior global context modeling and long-range feature capture. | Requires massive pretraining data; slower inference on low-power edge devices without specialized tensor accelerators. | Advanced multiscale disease and biosecurity screening. |
| **TinyML / 1D-CNN (Signal Processing)** | Ultra-Low (KFLOPs) | 1 – 5 ms (Cortex-M4/M7) | Runs directly on microcontrollers; analyzes raw current, vibration, and audio time-series. | Limited to sensor waveforms; does not process optical imagery. | Real-time blade wear detection; motor stall anticipation. |

## 4. Engineering Relevance
- **Edge Deployment Target**:
  - The computational architecture should adopt a **two-tier processing model**:
    1. *Real-Time Deterministic Tier (Microcontroller)*: Fast sensor acquisition (current, Hall RPM, E-stop, stepper PWM) running at > 1 kHz in C/C++ firmware on an ARM Cortex-M or ESP32.
    2. *Asynchronous Vision Tier (Edge SBC / NPU)*: Optical quality assessment and foreign object screening running at 15–30 FPS on a secondary embedded board (e.g., Raspberry Pi 5 with Hailo-8L accelerator or RK3588).
- **Quantization & Optimization**:
  - All deep learning models must undergo Post-Training Quantization (PTQ) or Quantization-Aware Training (QAT) to INT8 precision using ONNX Runtime, TFLite, or OpenVINO to minimize RAM and execution latency.

## 5. Questions to Investigate
- Does an INT8 quantized YOLOv8-nano model retain sufficient mean average precision (mAP) to detect 5 mm leaf spots on vibrating conveyors?
- What is the inference energy (Joules per frame) of candidate models on low-cost edge platforms?
- Can classical color thresholding serve as an initial wake-up filter to run neural network inference only when biomass is detected in the field of view?

## 6. Sources
1. Howard, A., et al. (2019). *Searching for MobileNetV3*, ICCV.
2. Jocher, G., et al. (2023). *YOLO by Ultralytics*, GitHub / Open-source benchmark repository.
3. Warden, P., and Situnayake, D. (2019). *TinyML: Machine Learning with TensorFlow Lite on Arduino and Ultra-Low-Power Microcontrollers*, O'Reilly Media.
