# Datasets Repository

This directory contains metadata, download manifests, data schemas, and sample subsets of datasets used for computer vision and sensor time-series research.

## Large File Storage Policy
- Raw image sets, video streams, and large training tensors (> 50 MB) must not be checked into Git directly.
- Store large assets using Git LFS, cloud bucket links (e.g., Hugging Face Datasets / Zenodo), or automated download scripts (`download_dataset.sh`).
- Local directory contains schema definitions, validation splits, and small golden test sets.
