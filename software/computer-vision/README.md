# Computer Vision & Edge Inference

This directory contains computer vision scripts, data preprocessing tools, model training notebooks, and edge inference deployment pipelines.

## Responsibilities
- Conveyor frame capture and color calibration routines.
- Classical CV baseline: Otsu thresholding, leaf contour area calculation, and stem width measurement.
- Deep Learning inference: ONNX Runtime / HailoRT wrapper for real-time leaf maturity classification and foliar defect detection.
- Asynchronous communication of vision metadata to the supervisory control loop.

## Development Stack
- Python 3.10+, OpenCV (`cv2`), PyTorch, Albumentations, ONNX Runtime.
- Export pipelines targeting INT8 quantized ONNX models and Hailo HEF compiled binaries.
