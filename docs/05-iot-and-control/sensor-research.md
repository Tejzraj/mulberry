# Sensor Research and Instrumentation

## 1. What It Is
Sensor research evaluates physical sensing transducers and instrumentation topologies for capturing real-time electrical, mechanical, kinematic, optical, and environmental states of the cutting machine and the plant biomass.

## 2. Why It Matters
Without real-time sensing, a cutting machine operates blind (open-loop), incapable of detecting incoming biomass density spikes, preventing motor stall jams, identifying blade dulling, or adjusting to ambient humidity shifts that alter leaf moisture.

## 3. Key Concepts & Sensor Evaluation Matrix

*(Note: The utility and sensitivity of each sensor listed below represent proposed research directions and must be experimentally characterized).*

| Sensor | Measurement | Why useful | Possible placement | Expected signal | Limitations |
|---|---|---|---|---|---|
| **Camera (Global Shutter CMOS)** | 2D RGB / Multispectral optical reflectance | Non-contact detection of leaf maturity, surface area, stem presence, and foliar disease | Overhead intake tunnel looking down at conveyor belt | 1080p video frames @ 30 FPS; 8-bit RGB arrays | Susceptible to lens fouling from dust/sap; sensitive to ambient lighting changes; requires high compute. |
| **Vibration Sensor (MEMS Accelerometer)** | Acceleration along 1–3 axes ($g$ or $m/s^2$) | Detects blade-ledger impact shocks, mechanical unbalance, bearing wear, and chatter | Rigidly bolted to cutter shaft bearing blocks | Time-series acceleration waveform; FFT vibration spectrum (10 Hz – 10 kHz) | Signal contaminated by motor vibration; high mounting surface stiffness required; temperature drift. |
| **Microphone (Acoustic Sensor)** | Airborne sound pressure waves ($Pa$ or $dBA$) | Detects acoustic signature difference between clean shear "snip" and dull blade "crunch/crush" | Acoustically shielded chamber adjacent to ledger bar | Continuous audio waveform (20 Hz – 20 kHz); spectral acoustic power | Heavy interference from ambient farm noise, gearbox whining, and motor hum; directional shielding needed. |
| **Motor Current Sensor (Hall-Effect / Shunt)** | Drive motor phase / DC bus current ($A$) | Direct electrical proxy for mechanical cutting resistance, instantaneous torque load, and stall warning | Integrated onto motor driver PCB or main DC/AC power rail | Continuous analog voltage ($0-5V$ or $4-20mA$) proportional to instantaneous current | Measures aggregate motor load, including bearing friction; cannot isolate individual leaf vs. stem cuts without high-bandwidth filtering. |
| **Torque Sensor (Inline Reaction / Strain Gauge)** | True shaft torque ($N\cdot m$) | Direct ground-truth measurement of mechanical torque required during cutting stroke | Inline between motor shaft and cutter drum shaft, or reaction flange | High-bandwidth analog voltage / digital frequency proportional to torque | High component cost ($> $300); mechanical complexity; delicate slip rings (if dynamic inline type). |
| **RPM Sensor (Optical / Hall Effect)** | Cutter drum & feed roller angular velocity ($RPM$) | Verifies instantaneous rotational speed, detects deceleration under heavy stem loads, calculates cut length | Affixed to rotating shaft hub with multi-toothed target wheel | Digital pulse train (e.g., 60 pulses/rev); square wave frequency | Optical sensors foul from dust; Hall sensors require precise magnetic target alignment (< 2 mm gap). |
| **Load Cell (Strain Gauge Cantilever)** | Biomass weight on feed hopper ($kg$ / $g$) | Quantifies input mass rate, verifies total batch weight, and calculates specific cutting energy ($kJ/kg$) | Beneath the intake conveyor frame or feed tray suspension | Small differential millivolt signal amplified via HX711 / instrumentation op-amp | Mechanical vibration from cutting drum introduces dynamic noise; tare drift under temperature change. |
| **Temperature Sensor (Digital I2C / RTD)** | Ambient air temperature and motor housing temperature (°C) | Monitors motor thermal rise and detects high room temperature accelerating leaf wilting | Internal electrical enclosure and surface of drive motor stator | Digital readings via I2C/1-Wire (e.g., DS18B20, SHT31) | Slow thermal response time (thermal mass of housing); only reflects localized temperatures. |
| **Humidity Sensor (Capacitive RH)** | Ambient relative humidity (%) | Flags low humidity conditions (< 60% RH) that cause rapid cut leaf desiccation in rearing halls | Mounted on external chassis bracket under protective vented shield | Digital RH percentage (0–100% RH $\pm 2\%$) | Sensitive to condensation and aerosolized chemical disinfectants (formalin, chlorine). |
| **Biomass Moisture Sensor (Capacitive / NIR)** | Plant tissue water content (% wet basis) | Verifies incoming leaf succulence before cutting; helps distinguish tender vs coarse leaves | Contact plates on feed guide or non-contact optical NIR reflectance | Analog voltage or dielectric permittivity index | Contact electrodes foul rapidly with sap; non-contact NIR is costly and requires careful optical calibration. |

## 4. Engineering Relevance
- **Minimal Viable Sensor Suite for Early Prototype**:
  - Phase 1–5 instrumentation will prioritize:
    1. Current sensor (Hall effect) for jam detection and torque estimation.
    2. Hall RPM sensor on cutter drum for precise angular velocity and slip tracking.
    3. Tri-axial MEMS accelerometer on cutter bearing block for vibration benchmarking.
    4. Top-down CMOS camera for baseline dataset collection.
- **Signal Conditioning**: High-speed analog signals (current, vibration, acoustics) require anti-aliasing low-pass filters and isolated power supplies to prevent motor PWM switching noise from corrupting data.

## 5. Questions to Investigate
- Can a low-cost current shunt ($< $2) provide the same anti-jam warning fidelity as an expensive inline torque transducer ($> $300)?
- At what frequency band does blade-ledger contact occur during normal shearing vs. dull rubbing?
- What signal-to-noise ratio (SNR) is achievable for acoustic cutting measurements in an open sericulture shed?

## 6. Sources
1. Fraden, J. (2016). *Handbook of Modern Sensors: Physics, Designs, and Applications* (5th ed.), Springer.
2. Srivastava, A.K., et al. (2006). *Engineering Principles of Agricultural Machines*, ASABE.
3. Central Silk Board (CSB), *Technical Specifications for Sericulture Appliances*.
