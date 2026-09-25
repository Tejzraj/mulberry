# Computer Vision in Mulberry Processing

## 1. What It Is
Computer vision (CV) refers to the algorithmic acquisition, preprocessing, analysis, and extraction of high-dimensional semantic and geometric data from optical imagery of mulberry plant materials entering or exiting the cutting machine.

## 2. Why It Matters
Mulberry feed preparation in sericulture requires sorting by biological maturity (tender chawki vs. mature late-age), verifying absence of foliar pathogens, detecting foreign debris (stones, twine, wire), and verifying output cut geometry. Automated optical inspection offers a potential non-contact method to perform these checks continuously in real time.

## 3. Key Concepts & Technical Principles

### Optical Imaging in Agricultural Environments
- **Illumination Control**: Ambient sunlight in farm sheds varies wildly (100 lux on cloudy mornings to > 20,000 lux in open yards). Optical inspection requires an enclosed imaging tunnel with controlled, diffused LED illumination (high CRI, polarized light to eliminate specular leaf reflections).
- **Camera Sensor Hardware**:
  - Global shutter CMOS sensor vs. rolling shutter: Global shutter is strongly preferred for high-speed moving belts to prevent motion blur and geometric distortion.
  - Resolution: 1080p (2 MP) to 5 MP provides sufficient spatial detail (< 0.2 mm/pixel) over a 200–300 mm feed belt width.
- **Multispectral / NIR Considerations**:
  - Mulberry leaves have high NIR reflectance (750–900 nm) due to spongy mesophyll cell structure. Near-infrared (NIR) imaging could potentially distinguish moisture levels and early fungal blight before visible necrosis appears.

### Algorithmic Pipeline Stages
```
[Raw Image Capture]
        ↓
[Preprocessing (Undistortion, Color Balance, ROI Masking)]
        ↓
[Feature Extraction / Segmentation (Color, Texture, Edges)]
        ↓
[Inference / Classification (Traditional CV / Edge Deep Learning)]
        ↓
[Decision Output (Material Class, Cut Setting, Rejection Signal)]
```

## 4. Engineering Relevance
- **Speed & Latency**: A conveyor running at 0.1 to 0.3 m/s requires an inference throughput of 15 to 30 frames per second (FPS). Latency must remain < 50 ms to trigger a diverter/rejection mechanism before material reaches the cutter.
- **Environmental Robustness**: Dust, latex splatters, and moisture from cut stems will accumulate on optical lenses. The optical enclosure must incorporate protective sacrificial sapphire/glass windows and positive-pressure air curtains or mechanical wipers.

## 5. Questions to Investigate
- Can standard RGB cameras distinguish between 2nd-instar suitable leaves and 4th-instar leaves under controlled illumination, or is multispectral sensing necessary?
- What is the minimum frame rate and exposure time required to eliminate motion blur at a 0.25 m/s belt speed?
- How severely does dust accumulation degrade image segmentation accuracy over a 4-hour cutting shift?

## 6. Sources
1. Davies, E.R. (2012). *Computer and Machine Vision: Theory, Algorithms, Practicalities* (4th ed.), Academic Press.
2. Central Silk Board (CSB), *Research Bulletin on Image Processing Applications in Sericulture*.
3. Patel, K.K., Kar, A., Jha, S.N., and Khan, M.A. (2012). *Machine vision system: a tool for quality inspection of food and agricultural products*, Journal of Food Science and Technology, 49(2), 123-141.
