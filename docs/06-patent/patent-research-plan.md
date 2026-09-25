# Patent Research Plan and Methodology

## 1. What It Is
The patent research plan defines the systematic process, classification taxonomies, search syntax, query strings, and validation protocols used to perform prior-art searches and freedom-to-operate (FTO) landscape analyses.

## 2. Why It Matters
Conducting an ad-hoc or unorganized keyword search frequently misses key patents that use non-obvious terminology (e.g., "comminution apparatus" or "vegetative biomass fragmentation" instead of "leaf cutter"). A structured methodology ensures exhaustive coverage of the patent landscape before finalizing design decisions.

## 3. Key Concepts & Search Protocols

### International Patent Classification (IPC) & Cooperative Patent Classification (CPC)
The following primary and secondary classification codes define the target search space:

| Classification Code | Definition / Scope |
|---|---|
| **A01F 29/00** | Cutting apparatus especially adapted for cutting hay, straw, or fodder. |
| **A01F 29/01** | Cutting apparatus with feeding arrangements (e.g., feed rollers, conveyors). |
| **A01F 29/04** | Cutting apparatus with rotary cutting drums or cylinders. |
| **A01F 29/06** | Cutting apparatus with knives mounted on a disc or wheel. |
| **A01K 67/04** | Silkworms; Rearing devices or appliances therefor. |
| **B26D 1/00** | Cutting machines; Cutting devices with reciprocating or rotary cutting members. |
| **B26D 5/00** | Devices for controlling, monitoring, or regulating cutting apparatus. |
| **G01N 33/00** | Investigating or analyzing agricultural materials. |
| **G06T 7/00** | Image analysis (e.g., object detection, defect inspection in agriculture). |

### Search Strings & Boolean Queries
Target query combinations for Google Patents, Espacenet, and InPASS:
1. `(mulberry OR "silkworm feed" OR "sericulture") AND (cutter OR chopper OR shredder OR slicer)`
2. `(A01F29/00 OR A01F29/04) AND ("feed roller" OR "variable speed" OR "adaptive" OR "sensor")`
3. `("chaff cutter" OR "forage cutter") AND ("blade wear" OR "current monitoring" OR "jam detection" OR "anti-jam")`
4. `(A01K67/04) AND (feed* OR leaf OR cut*)`
5. `("cutting quality" OR "edge sharpness") AND (acoustic OR vibration OR torque) AND (blade OR knife)`

## 4. Engineering Relevance: Freedom-to-Operate (FTO) Review
- If an existing active patent claims "an agricultural chaff cutter wherein feed roller speed is varied based on motor current", our design must either:
  1. License the technology.
  2. Design around the patent claims (e.g., by using alternative control parameters or different physical kinematic arrangements).
  3. Verify whether the patent is expired, abandoned, or geographically restricted.
- *Legal Reminder*: **Patentability requires a formal prior-art and legal assessment.**

## 5. Questions to Investigate
- What are the major active patents held by agricultural equipment manufacturers (e.g., CLAAS, Deere, New Holland, Kubota) relating to rotary forage cutter feed control?
- Are there specific patents from the Central Silk Board or Chinese sericultural research institutes on mechanized mulberry choppers?
- What are the status and expiration dates of early Indian patents filed under class `A01F 29/00`?

## 6. Sources
1. World Intellectual Property Organization (WIPO), *IPC Manual and Guidelines*.
2. European Patent Office (EPO), *Espacenet Search Guide*.
3. Controller General of Patents, Designs and Trade Marks (CGPDTM), *InPASS User Guide*.
