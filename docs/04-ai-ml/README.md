# 04 - AI and Machine Learning Research

This directory contains research, architectural trade-offs, and experimental designs for artificial intelligence, computer vision, and machine learning models proposed for the smart mulberry cutting machine.

## Document Index

1. [`computer-vision.md`](computer-vision.md) — Optical inspection principles, lighting geometries, camera sensor options, and computer vision pipelines for agriculture.
2. [`possible-ai-use-cases.md`](possible-ai-use-cases.md) — Exploration of candidate use cases (leaf detection, instar matching, blade degradation, anomaly rejection) with detailed trade-off matrix.
3. [`dataset-requirements.md`](dataset-requirements.md) — Data schema, image resolution, environmental variation, annotation protocols, and ethical/open-source dataset planning.
4. [`model-research.md`](model-research.md) — Comparative evaluation of candidate model families (Classical CV, lightweight CNNs, YOLO variants, MobileNet, Vision Transformers, TinyML).
5. [`edge-ai.md`](edge-ai.md) — Embedded compute hardware (Raspberry Pi, ESP32-S3, Hailo, Jetson, K210), quantization (INT8/FP16), latency, and thermal envelopes.

## AI / ML Research Philosophy
- **Hypothesis, Not Solution**: AI is a potential tool, not an assumed requirement. Classical thresholding, physical sensors, or deterministic algorithms are preferred where they prove faster, cheaper, and more robust.
- **Model Agnostic**: No single neural architecture (YOLO, ViT, etc.) is prematurely chosen before baseline empirical dataset benchmarking.
- **Offline / Edge First**: Systems must run locally without requiring constant cloud connectivity or internet access, reflecting rural farming realities.
