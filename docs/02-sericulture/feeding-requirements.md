# Silkworm Feeding Requirements Across Instars

## 1. What It Is
Silkworm feeding requirements refer to the instar-specific quantitative and qualitative nutritional guidelines for *Bombyx mori* larvae, including physical leaf piece dimensions, moisture content, leaf age/position on the shoot, feeding frequency, and total biomass consumption.

## 2. Why It Matters
Silkworms cannot search for food; feed must be presented to them directly in their beds in an edible, accessible form. Because larval mouthparts, biting strength, and gut capacity grow dramatically across the 5 instars, presenting oversized, fibrous, or bruised leaves to young larvae causes starvation, dehydration, and high mortality. Conversely, manually chopping small pieces for thousands of mature 5th instar larvae is economically unviable and labor-prohibitive.

## 3. Key Concepts & Instar Requirements Matrix

The table below synthesizes established sericultural guidelines (Central Silk Board / CSRTI Mysore benchmarks) and maps them to engineering implications for the smart cutting machine.

| Silkworm stage | Feeding characteristics | Mulberry requirement | Machine implication | Evidence |
|---|---|---|---|---|
| **1st Instar (Chawki)** | Extremely small mouthparts (~0.2–0.3 mm mandible span); delicate biting power; can only nibble succulent cut edges; highly prone to desiccation. | Tender, succulent apical leaves (3rd to 4th leaf from top); moisture 78–82%; protein 25–27%; cut into tiny square pieces (0.5 cm × 0.5 cm). | Fine chopping required; zero tearing or bruising; sharp shear cut to prevent sap weeping; anti-mashing feed roller. | CSRTI Mysore Chawki Guidelines; Krishnaswami (1978). Machine implication: To be investigated experimentally. |
| **2nd Instar (Chawki)** | Growing mouthparts; increased biting force; feeding vigor expands; active movement across tray bed. | Tender leaves (4th to 6th leaf from top); moisture 75–80%; cut into square pieces (1.0 cm × 1.0 cm to 1.5 cm × 1.5 cm). | Adjustable cutting pitch; medium-fine chopping; high cut edge precision; low shear clearance (< 0.1 mm). | CSB Hand Book of Sericulture Technologies (2014). Machine implication: To be investigated experimentally. |
| **3rd Instar** | Intermediate larval stage; stronger mandibles; capable of chewing through secondary leaf veins; appetite accelerates. | Semi-mature leaves (5th to 8th leaf from top); moisture 70–75%; cut into pieces of 2.0 cm × 2.0 cm to 3.0 cm × 3.0 cm, or fed as whole small leaves. | High-throughput mode; coarser blade spacing or faster conveyor advance; petiole cutting ability without jamming. | CSRTI Mysore Silkworm Rearing Manual; Dandin & Giridhar (2014). Machine implication: To be investigated experimentally. |
| **4th Instar** | Voracious appetite; strong serrated mandibles; easily feeds on whole leaves, petioles, and tender green stems. | Mature, nutrient-dense leaves (7th to 12th leaf); moisture 68–72%; fed as whole leaves or shoots sectioned to 5–10 cm lengths. | High biomass throughput (kg/min); ability to process woody stems without motor stall; coarse shear mechanism. | CSB Technical Guidelines; FAO Bulletin 107. Machine implication: To be investigated experimentally. |
| **5th Instar** | Accounts for ~80–85% of total lifetime feed ingestion; massive body size; feeds continuously day and night; consumes whole foliage and shoot bark. | Fully mature, robust leaves and whole shoots; moisture 65–70%; high dry matter and carbohydrate content; whole shoots or 10–15 cm cuts. | Heavy-duty cutting/defoliation; high cutting torque; anti-jamming torque sensing; high capacity throughput. | CSRTI Mysore Guidelines; Tazima (1978). Machine implication: To be investigated experimentally. |

## 4. Engineering Relevance: Why Silkworm Age / Instar Matters to the Machine
1. **Dynamic Particle Sizing**: The cutting machine cannot be a single-speed, single-geometry chopper. It must dynamically adjust cut length between 0.5 cm (1st instar) and 10–15 cm or whole shoot delivery (5th instar).
2. **Cutting Mechanics & Edge Quality**:
   - For 1st/2nd instars, any tearing, crushing, or bruising of the lamina crushes mesophyll cells, releasing cellular sap that oxidizes into a dark, unpalatable border and causes rapid desiccation within 1–2 hours. The cutting action must be pure scissor-like shear with negligible clearance.
   - For late instars, throughput speed and motor torque handling become the dominant constraints, while cut edge precision is less biologically critical.
3. **Biomass Heterogeneity & Lignification**: Early instar feed consists exclusively of tender individual leaves (pliable, thin, low cut resistance). Late instar feed involves entire shoots with lignified xylem stems (stiff, fibrous, high shear resistance). The machine must withstand or modulate its drive systems for both loading regimes.

## 5. Questions to Investigate
- What is the quantitative rate of moisture loss (% loss per hour) from 0.5 cm cut leaf squares versus 2.0 cm cut leaf squares under standard room conditions?
- What is the cutting energy (Joules per cut) required for a pack of tender chawki leaves versus a mature mulberry stem (diameter 8–12 mm)?
- Can a vision or sensor-based subsystem reliably identify or verify the incoming leaf grade (tender vs. mature) to prevent feeding incorrect material?

## 6. Sources
1. Central Sericultural Research and Training Institute (CSRTI), Mysore, *Chawki Rearing Manual*, Central Silk Board.
2. Krishnaswami, S. (1978). *New Technology of Silkworm Rearing*, Bulletin No. 2, CSRTI Mysore.
3. Dandin, S.B., and Giridhar, K. (2014). *Handbook of Sericulture Technologies*, CSRTI Mysore.
4. Tazima, Y. (1978). *The Silkworm: An Important Laboratory Tool*, Kodansha Ltd., Tokyo.
