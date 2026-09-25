# Mulberry Pests and Diseases

## 1. What It Is
Mulberry is susceptible to various fungal, bacterial, viral diseases and insect pests that degrade foliage biomass, alter leaf biochemistry, and leave toxic or infectious residues.

## 2. Why It Matters
Feeding silkworms diseased or pest-infested mulberry leaves triggers nutritional deficiencies, gastrointestinal disorders, and disease outbreaks in the rearing bed. Identifying and rejecting contaminated leaves prior to feeding is vital for colony survival.

## 3. Key Concepts
- **Common Diseases**:
  - *Leaf Spot (Cercospora moricola)*: Circular brownish necrotic spots that enlarge, dry up, and create shot-holes.
  - *Powdery Mildew (Phyllactinia corylea)*: White powdery fungal patches on the ventral leaf surface, reducing leaf moisture and protein content.
  - *Leaf Rust (Cerotelium fici)*: Brownish-red pustules on the lower leaf surface, turning yellow and causing premature leaf drying.
  - *Bacterial Blight (Pseudomonas syringae pv. mori)*: Water-soaked spots on leaves that turn dark brown/black with chlorotic halos, curling young leaves.
- **Major Pests**:
  - *Thrips (Pseudodendrothrips mori)*: Puncture leaf epidermal cells and suck sap; leaves show silver-white streaks and curl upwards.
  - *Mealybug (Maconellicoccus hirsutus)*: Causes "Tukra" disease characterized by severe apical shoot curling, crinkled dark-green leaves, and stunted shoots. Tukra-affected leaves have altered protein and sugar ratios unsuitable for silkworms.
  - *Spiralling Whitefly (Aleurodicus dispersus)*: Secretes sticky honeydew fostering sooty mold growth on leaves.

## 4. Engineering Relevance
- **Automated Bio-Security & Quality Sorting**: Computer vision can be trained to detect visible surface anomalies: white powdery fungal patches, Tukra apical deformation, brown necrotic spots, and sooty mold.
- **Rejection Mechanism**: If a contaminated section is detected on a feed conveyor, a pneumatic blow-off nozzle or diverter gate could divert it away from the cutting chamber.
- **Blade Hygiene & Residue**: Diseased leaves with sap exuded from fungal lesions or honeydew leave sticky residues on blade edges, requiring non-stick coatings or automated wiper scrapers.

## 5. Questions to Investigate
- Can a standard RGB camera with controlled LED illumination detect early powdery mildew or leaf spot symptoms under moving feed conditions?
- What false positive rate is acceptable when auto-rejecting suspect leaves to prevent wasting healthy feed?
- How do pest residues affect the friction coefficient and wear of cutter feed rollers?

## 6. Sources
1. Govindaiah, Sharma, D.D., Rajadurai, S., and Naik, V.N. (2005). *Mulberry Crop Protection*, Central Silk Board, Bangalore.
2. Qadri, S.M.H., et al. (2010). *Diseases and Pests of Mulberry and Their Management*, CSRTI, Berhampore.
3. Central Silk Board, *Plant Protection in Sericulture*, Research Bulletin Series.
