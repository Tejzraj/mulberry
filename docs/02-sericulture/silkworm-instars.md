# Silkworm Instars

## 1. What It Is
An instar is the developmental stage of the silkworm larva between successive moults (ecdyses). The domesticated silkworm *Bombyx mori* typically undergoes 4 moults, dividing its larval phase into 5 distinct instars (tetramoulters).

## 2. Why It Matters
Silkworm larvae undergo rapid morphological, physiological, and mouthpart transformations across the five instars. A 1st instar larva is tiny (~3 mm long, 0.45 mg) with weak, delicate mandibles capable of nibbling only tender leaf laminae edges, whereas a 5th instar larva is massive (~70–80 mm long, 4–5.5 g) with heavily sclerotized, serrated mandibles that can chew through fibrous veins and succulent bark. Consequently, the physical dimension and mechanical texture of mulberry feed must match larval mouthpart mechanics.

## 3. Key Concepts
- **Chawki Stages (Young-Age Rearing)**:
  - **1st Instar**: Duration ~3–3.5 days. Larvae emerge as black "ants" (kego). Mouthparts are miniature and tender. Feed requirement: highly succulent, top-tender leaves chopped into fine squares (0.5 cm × 0.5 cm).
  - *First Moult*: Cease feeding for 20–24 hours. Head capsule loosens.
  - **2nd Instar**: Duration ~2.5–3 days. Larvae turn lighter brownish-gray. Feed requirement: slightly larger chopped leaves (1.0 cm to 1.5 cm squares).
  - *Second Moult*: Cease feeding for 20–24 hours.
- **Late-Age Stages**:
  - **3rd Instar**: Duration ~3.5–4 days. Transition stage. Larvae turn white/creamy. Feed requirement: larger chopped leaves (2 cm to 3 cm) or semi-whole leaves.
  - *Third Moult*: Cease feeding for 24–28 hours.
  - **4th Instar**: Duration ~4–5 days. High feeding vigor; can ingest whole leaves or sliced branches. Feed requirement: whole leaves or coarsely cut shoots (~5–10 cm).
  - *Fourth Moult*: Cease feeding for 28–32 hours; final larval moult.
  - **5th Instar**: Duration ~6–8 days. Voracious appetite (consumes ~80% of total lifetime feed). Mandibles fully developed; feeds on whole leaves, shoot twigs, and midribs. Rapid silk gland hypertrophy.

## 4. Engineering Relevance
- **Variable Particle Geometry**: A smart cutting machine cannot rely on a single fixed cutting blade pitch or feed speed. It must support multiple discrete modes or continuously variable cut lengths:
  - Micro-cutting / fine chopping (0.5 cm – 1.0 cm) for Chawki.
  - Medium chopping (2.0 cm – 4.0 cm) for 3rd instar.
  - Coarse / shoot sectioning (5.0 cm – 15.0 cm) or bypass for late age.
- **Bruising Sensitivity**: Chawki cut pieces have a very high perimeter-to-surface-area ratio. If the blade tears or crushes the tissue rather than severing it with clean shear, excessive sap exudation and oxidative blackening will occur, causing young larvae to reject the feed.
- **Detection of Target Instar Setting**: The machine control interface should allow sericulturists to select the target instar (or verify via vision/presets) to automatically adjust blade speed, feed-roller speed, and shear clearance.

## 5. Questions to Investigate
- What is the maximum acceptable blade edge radius (sharpness in micrometers) to avoid cellular crushing of 1st instar leaves?
- How does the cut edge perimeter of a 0.5 cm square compare to moisture loss rate over 4 hours under typical chawki room conditions (27°C, 85% RH)?
- Can a single blade drum mechanism achieve both 0.5 cm leaf squares and 10 cm stem cuts through feed-rate modulation, or are swappable/multi-stage mechanisms necessary?

## 6. Sources
1. Central Sericultural Research and Training Institute (CSRTI), Mysore, *Chawki Rearing Manual*, Central Silk Board.
2. Krishnaswami, S. (1978). *New Technology of Silkworm Rearing*, Bulletin No. 2, CSRTI Mysore.
3. Rajan, R.K., and Himantharaj, M.T. (2005). *A Textbook on Silkworm Rearing*, Central Silk Board, Bangalore.
