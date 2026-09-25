# Dataset Requirements and Collection Protocols

## 1. What It Is
The dataset requirements specify the data volume, modalities, resolution, lighting diversity, ground-truth annotation standards, and storage taxonomy required to train, validate, and benchmark proposed machine learning models for mulberry inspection.

## 2. Why It Matters
A machine learning model is only as robust as the variance and ground-truth fidelity of its training distribution. In agricultural machine vision, models trained on clean laboratory benchtop photographs invariably fail in dusty, vibrating farm environments with variable ambient sunlight.

## 3. Key Concepts & Dataset Taxonomy

### Data Modalities
1. **RGB Optical Imagery**:
   - Camera: High-speed global shutter CMOS sensor (1080p to 4K).
   - Angle: Perpendicular top-down view (90°) and oblique angle (45°) of intake conveyor.
   - Illumination variants: Controlled white LED diffuse ring, direct sunlight simulation, variable shadow conditions.
2. **Time-Series Vibration & Acoustic Signals**:
   - Accelerometer (3-axis MEMS or piezoelectric, $\ge 10 \text{ kHz}$ sampling rate).
   - Acoustic microphone (omnidirectional, 44.1 kHz, 24-bit audio).
   - Synchronized motor shunt current and Hall RPM sensor logs (1 kHz sampling).
3. **Cut Quality Macro-Images**:
   - High-magnification (50×–200×) optical microscope captures of cut edges to quantify cellular margin crushing.

### Proposed Class Schema for Mulberry Vision
- `leaf_tender_chawki`: 1st–4th leaves from shoot apex, succulent, light green.
- `leaf_mature_late_age`: 5th–15th leaves, dark green, leathery, thick.
- `shoot_green_tender`: Apical stem, diameter < 4 mm, soft.
- `shoot_woody_mature`: Basal stem, diameter 5–15 mm, brown/grey bark, fibrous.
- `defect_leaf_spot`: Necrotic brown/black spots (*Cercospora moricola*).
- `defect_mildew`: White powdery patches (*Phyllactinia corylea*).
- `defect_tukra`: Curled, thickened leaves from mealybug infestation.
- `hazard_foreign_object`: Stones, soil clods, metallic wire, twine, insects.

### Annotation Standards
- Bounding boxes and polygonal masks formatted in standard COCO JSON and YOLO TXT conventions.
- Minimum inter-annotator agreement score ($\kappa > 0.85$) across agricultural domain experts for disease labeling.

## 4. Engineering Relevance
- **Dataset Partitioning**: Rigorous 70% Train / 15% Validation / 15% Test split partitioned strictly at the *farm/batch level* (not random frame shuffling) to prevent temporal data leakage.
- **Hardware-in-the-Loop Validation**: Test sets must include deliberate edge cases: wet glistening leaves, wilted limp leaves, overlapping tangled stems, and vibrating conveyor frames.

## 5. Questions to Investigate
- What is the minimum number of unique leaf samples required to achieve > 90% mAP on leaf/stem segmentation?
- How much does synthetic data augmentation (color jitter, motion blur, random perspective) improve model generalization to new mulberry cultivars?
- What data compression formats preserve fine edge resolution without slowing down disk I/O during batch training?

## 6. Sources
1. Central Silk Board (CSB), *Mulberry Foliar Pathogen Identification Guide*.
2. Lin, T.Y., et al. (2014). *Microsoft COCO: Common Objects in Context*, ECCV.
3. Lu, Y., and Young, S. (2020). *A survey of public datasets for computer vision tasks in precision agriculture*, Computers and Electronics in Agriculture, 178, 105760.
