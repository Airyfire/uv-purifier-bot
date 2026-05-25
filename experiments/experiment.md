# Experiment 1: Stationary Purifier Stagnant Zone Test

**Status:** ✅ Complete

## Research Question
Does a stationary HEPA air purifier effectively reduce particulate concentration in stagnant zones of a room?

## Hypothesis
In a room with low natural airflow, particulate concentration in stagnant zones (corners, under desks) decreases significantly slower than near the purifier itself.

## Setup

### Environment
- Small indoor room (bedroom / classroom corner)
- Windows closed, HVAC off (to eliminate uncontrolled airflow)

### Sensor Placement

| Sensor | Location |
|--------|----------|
| A | Near purifier (~1–2 ft) |
| B | Middle of room |
| C | Stagnant zone (corner / behind furniture / under desk) |

All sensors: **PM2.5 particle concentration**

### Pollution Source
- Incense stick (preferred — consistent, controllable)
- Source location kept **identical across all trials**

### Equipment
- [PM2.5 Sensors (Qingping)](https://www.amazon.com/Qingping-Scattering-Principle-Accurate-Measurement/dp/B0FSZ633MB/)
- [HEPA + UV Air Purifier — POMORON MJ002H (1250 ft² coverage)](https://www.amazon.com/POMORON-MJ002H-Purifiers-Generator-Particles/dp/B09KMT9J7L/)

## Procedure

1. **Baseline** — Everything off. Record PM2.5 at all 3 sensors.
2. **Pollute** — Burn incense for 30–60 seconds. Let disperse for 1–2 minutes.
3. **Activate purifier** — Turn on HEPA purifier. Begin recording.
4. **Record** — Log PM2.5 at all sensors every 30 seconds for 15–30 minutes.

## Baseline Readings (Pre-Pollution)

| Sensor | Location | Reading |
|--------|----------|---------|
| A | Near purifier | 1.0 µm/m³ |
| B | Middle | 1.2 µm/m³ |
| C | Stagnant zone | 1.5 µm/m³ |

## Expected Results

| Zone | Expected Pattern |
|------|-----------------|
| Near purifier | Sharp, fast drop in PM2.5 |
| Middle | Moderate decline |
| Stagnant zone | Slow decline, possible plateau or fluctuation |

## Raw Data

> 📂 See [`data/`](data/) folder for time-series readings.

## Results

### Post-Pollution Readings (t = 0, purifier just turned on)

| Sensor | Location | PM2.5 (µg/m³) | Change from Baseline |
|--------|----------|---------------|----------------------|
| A | Near purifier | 115.6 | +114.6 |
| B | Middle | 123.3 | +122.1 |
| C | Stagnant zone | 97.8 | +96.3 |

### After 1 Hour of Purifier Running (t = 60 min)

| Sensor | Location | PM2.5 (µg/m³) | % Reduction from peak |
|--------|----------|---------------|-----------------------|
| A | Near purifier | 4.2 | **96.4%** |
| B | Middle | 5.6 | **95.5%** |
| C | Stagnant zone | 14.3 | **85.4%** |

## Analysis

### Key Finding: Stagnant Zone Cleans Significantly Slower
Despite starting with the *lowest* peak pollution (97.8 µg/m³ vs 115–123 near/middle), the stagnant zone ended with the **highest remaining concentration** (14.3 µg/m³) — more than **3× higher** than near the purifier (4.2) after a full hour.

### Why the Stagnant Zone Started Lower
This is actually expected behavior: the pollution source's particles dispersed *less* into the stagnant corner due to limited airflow there. Less air movement means both slower arrival of pollutants **and** slower removal — the stagnant zone is effectively isolated from the room's natural air circulation.

### Cleaning Rate Comparison

| Zone | Peak → 1hr | Remaining above baseline |
|------|-----------|--------------------------|
| Near purifier | 115.6 → 4.2 | +3.2 above baseline (1.0) |
| Middle | 123.3 → 5.6 | +4.4 above baseline (1.2) |
| **Stagnant zone** | **97.8 → 14.3** | **+12.8 above baseline (1.5)** |

The stagnant zone still had **4× more excess particulates** than the near zone after 60 minutes, even though it started with less pollution.

### Implication for Robot Design
This confirms the core motivation for a mobile purifier. A stationary purifier placed elsewhere in the room takes significantly longer — or may never fully clean — stagnant dead zones. A robot that moves to these zones and draws air directly would dramatically reduce residual particulate concentration.

## Conclusion

**Hypothesis confirmed.** Stagnant zones clean substantially slower than areas near a stationary purifier. After 60 minutes, the stagnant zone retained ~85.4% reduction vs ~96.4% near the purifier — a meaningful gap that worsens over shorter timeframes and in larger rooms. This justifies the mobile robot approach: by physically moving the purifier intake to stagnant zones, we can treat the entire room uniformly rather than leaving dead zones under-cleaned.

### Next Step → Experiment 2
Run the same test with the purifier mounted on a mobile robot that navigates to the stagnant zone and measure whether residual PM2.5 equalizes across all three sensors faster.
