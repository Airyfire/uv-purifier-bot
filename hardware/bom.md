# 🛒 Bill of Materials

## Experiment Phase (Proof of Concept)

| Item | Spec | Link | Status |
|------|------|------|--------|
| PM2.5 Air Quality Sensor | Qingping — laser scattering | [Amazon](https://www.amazon.com/Qingping-Scattering-Principle-Accurate-Measurement/dp/B0FSZ633MB/) | 🛒 To Order |
| HEPA + UV Air Purifier | POMORON MJ002H — 1250 ft² | [Amazon](https://www.amazon.com/POMORON-MJ002H-Purifiers-Generator-Particles/dp/B09KMT9J7L/) | 🛒 To Order |

> Qty: 3x PM2.5 sensors (near, middle, stagnant zone)

---

## Robot Build Phase (Target Specs)

| Component | Spec | Notes |
|-----------|------|-------|
| UV-C Lamp | 254 nm, ≥ 25W | Mercury lamp; handle with care |
| Fan | CFM 350–400 | Must generate suction strong enough to pull stagnant air |
| HEPA Filter | H13 or H14 | Fine enough to capture spores |
| PM2.5 Sensor | Continuous logging | For onboard air quality monitoring |
| Temperature Sensor | Mounted on UV lamp | Auto-shutoff on overheat |
| Fuse / Overcurrent Limiter | Rated for circuit load | Electrical safety |
| Plastic Duct/Enclosure | UV-C absorbing plastic | Prevents UV leakage outside unit |
| Robot Base / Chassis | Mobile platform | ~0.5 m³ target volume |
| Obstacle Detection Sensor | IR or ultrasonic | Safety — slow movement + stop on detection |
| Battery Pack | TBD capacity | Must power fan + lamp + sensors for target runtime |

---

## Notes
- UV LEDs were considered as an alternative to the UV lamp but rejected for proof-of-concept due to lower intensity and higher cost. May revisit for a later revision.
- Battery capacity requirements TBD after fan and lamp wattage are finalized.
