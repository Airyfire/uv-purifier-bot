# ⚠️ Safety Guidelines

## UV-C Safety

- **UV-C (200–280 nm)** is the safest UV band for enclosed use — it does not penetrate human skin deeply.
- However, direct exposure is still hazardous. UV-C must **never be openly exposed** during operation.
- Use a plastic cover/duct enclosure — plastic absorbs UV-C, preventing external leakage.
- Germicidal UV also produces **ozone**, which is harmful to the environment. Ensure proper venting or ozone-free UV-C lamps are used.

## Electrical Safety

- Add **fuses and overcurrent limiters** on all circuits to prevent short circuits.
- UV lamps emit significant heat — a **temperature sensor** must be mounted on the lamp.
  - If temperature exceeds safe threshold → automatically shut off the lamp.
- Fan failure detection: if the fan stops while the lamp is on, the system must shut down immediately to prevent heat buildup.

## Motion Safety

- The robot must move **slowly at all times** to avoid being a physical hazard.
- **Obstacle detection sensors** (e.g., IR or ultrasonic) must be active during all movement.
- The robot should stop immediately when an unexpected obstacle is detected within a safe threshold distance.

## Airflow Design Safety

- Air entrance and exit must be on **separate walls**, positioned as far apart as possible, to ensure consistent UV exposure and prevent short-circuiting airflow.
- Short pathways that would allow air to bypass the UV exposure zone must be avoided.
- The UV lamp must be positioned **2–5 cm** from the duct wall for optimal irradiance.
