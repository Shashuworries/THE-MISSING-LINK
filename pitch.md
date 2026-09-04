# UrjaSetu — Complete Reference for Slide Prep
### SIH Problem Statement SVH26004 | Hybrid Renewable Energy Generation Solution (Govt. of Rajasthan, DTE)

This document breaks the UrjaSetu concept into clean, presentable parts so your whole team knows exactly what to say about every screen, feature, and term before you walk into the room.

---

## PART 1 — Landing Page / Title Slide Content

**Product name:** UrjaSetu ("Urja" = energy, "Setu" = bridge — bridges solar, wind, battery, and grid)

**Tagline / One-liner (put this on your title slide):**
> UrjaSetu is a vendor-neutral, AI-driven Virtual Power Plant platform that unifies a campus's solar, wind, battery and grid connection, forecasts generation and demand, and issues real-time operational recommendations to maximize renewable self-consumption and minimize cost and carbon — with zero new hardware and zero specialized training.

**30-second elevator pitch (memorize this, say it in your opening 20 seconds):**
> Public campuses in Rajasthan already have solar panels, wind turbines and batteries — but each runs in isolation, so surplus solar gets dumped, batteries cycle on fixed timers, and campuses still pull from the grid at the worst possible hours. UrjaSetu is a vendor-neutral software layer that fuses live sensor data with short-term weather forecasts to treat solar + wind + battery + grid as one coordinated Virtual Power Plant (VPP). It tells facility staff — in plain language, with one click — exactly when to charge the battery, when to shift a load, and when it's safe to export, maximizing self-consumption without a single rupee of new hardware.

**The core reframe judges are looking for:**
The problem statement itself says: *"The crux of the challenge is orchestration, not hardware procurement."* Your entire pitch should be built around this line. Don't sell hardware ideas — sell the software brain that coordinates hardware that already exists.

**Three phrases to echo back to judges almost verbatim (they wrote these, so repeating them shows you read the brief carefully):**
1. "Vendor-neutral" — you have a hardware/protocol abstraction layer, not a single-brand point solution.
2. "Without specialised training" — the UI is built for non-technical facilities staff, not data scientists.
3. "Minimal additional hardware expenditure" — this is a software-only deployment on top of existing meters and inverters.

**Problem Statement metadata (for your title/context slide):**

| Field | Detail |
|---|---|
| Problem Statement ID | SVH26004 |
| Title | Hybrid Renewable Energy Generation Solution |
| Organization | Government of Rajasthan |
| Department | Directorate of Technical Education (DTE) |
| Category | Software |
| Theme | Clean & Green Technology |

---

## PART 2 — All Features, Explained in Full

### 2.1 Core USPs (your "why we win" slide)

| # | Feature | What it actually does | Why it matters to judges |
|---|---|---|---|
| 1 | **Vendor-neutral adapter layer** | Translates proprietary protocols (Modbus RTU/TCP, MQTT, OPC-UA) from different solar/wind/battery vendors into one common data schema, so any inverter, turbine controller, BMS, or smart meter can plug in regardless of manufacturer. | Directly answers the problem statement's explicit "vendor-neutral" requirement. |
| 2 | **Explainable recommendations** | Every suggestion (e.g., "Charge battery now — 40% surplus solar expected next 2h") is shown with a plain-language reason, not just a number. | Builds trust with non-technical staff; differentiates from black-box ML dashboards. |
| 3 | **Digital Twin + What-If Simulator** | Facility heads can simulate scenarios ("what if we add 5 more panels," "what if the workshop shifts to 2 PM") and see projected impact before spending money. | Highest wow-factor live-demo feature; cheap to build, high perceived value. |
| 4 | **State-wide scalability (multi-tenant by design)** | One central DTE dashboard aggregates savings/carbon across all institutions; each campus also gets its own local view. | The client is a *Directorate*, not one college — this design choice makes the impact look 10x bigger. |
| 5 | **Zero-hardware-cost narrative** | Reuses existing meters/inverters/sensors. The only possible new cost is a low-cost gateway device (even a Raspberry Pi) per site, and only if a legacy device lacks a digital interface. | Matches "minimal additional hardware expenditure" requirement exactly. |
| 6 | **Regulatory tailwind (VNM/GNM)** | Rajasthan's regulator (RERC) has just introduced Virtual Net Metering and Group Net Metering — meaning "Virtual Power Plant" isn't just your marketing metaphor, it maps onto a real, current state policy mechanism. | Most competing teams won't know this — it's a strong, differentiated feasibility argument. |
| 7 | **Human-in-the-loop safety model** | Recommendations are advisory by default, not autonomous control — a human confirms critical actions. | Removes liability concerns, which matters a lot when pitching to a government education department. |

### 2.2 System Modules (the architecture, explained module by module)

1. **Adapter Layer (Vendor-Neutral)** — Translates Modbus RTU/TCP, MQTT, and OPC-UA signals from different vendors' hardware into one common data schema. This module *is* the literal answer to the "vendor-neutral" requirement — build at least one real adapter (e.g., a Modbus simulator) and document the interface for the rest.

2. **Time-Series Data Store** — Stores generation, consumption, weather, and battery state-of-charge (SOC) at short intervals, using a time-series-optimized database since this is fundamentally sensor-stream data.

3. **Forecasting Engine** — Produces two forecasts, refreshed every 15–30 minutes:
   - *Generation forecast*: solar (irradiance + cloud cover + historical panel output) and wind (wind-speed forecast + turbine power curve).
   - *Demand forecast*: short-term load forecasting from historical consumption patterns plus calendar awareness (class schedules, hostel occupancy, lab hours).

4. **Digital Twin / VPP Core** — A virtual model representing the campus's entire energy state at any instant — combined generation, combined load, battery SOC, grid import/export — as one asset instead of four separate ones. This abstraction is what lets the optimizer reason about the whole system at once.

5. **Optimization & Dispatch Engine** — Given forecasts and current state, decides when to charge/discharge the battery, which loads can be shifted (and to when), and whether to export or curtail. Start with a rule-based/heuristic engine for the hackathon (fast to build, easy to explain), with a documented roadmap toward MILP or reinforcement-learning optimization for production.

6. **Recommendation & Alert Layer** — Converts optimizer output into plain-language, actionable messages for facility staff. This is the module that answers "no specialized training."

7. **Carbon & Cost Reporting** — Auto-generated dashboards showing ₹ saved, kWh self-consumed vs. grid-drawn, and CO₂ avoided — critical for the "Clean & Green Technology" theme and for ESG-style reporting DTE can show to the state government.

8. **Scenario / What-If Simulator** — Lets a facility head test "add more panels," "shift lab hours," or "add another battery" against historical data before committing budget. This is the single best live-demo feature.

9. **Multi-Campus Aggregator (DTE view)** — A rolled-up dashboard across all participating campuses, turning the product from "one college's tool" into "a state asset" — the scale a Directorate actually cares about.

### 2.3 Screens to Build (in priority order for the demo)

| Priority | Screen | What it shows |
|---|---|---|
| 1 | **Live Overview** | Current generation mix (solar/wind/battery/grid), battery SOC gauge, today's forecast curve overlay. |
| 2 | **Recommendations Panel** | Plain-language action cards, each with a one-line "why." |
| 3 | **Reports** | ₹ saved, kWh self-consumed, CO₂ avoided, and trend over time. |
| 4 | **What-If Simulator** | Sliders/inputs for "add panels" or "shift load," with an instant projected-impact chart. |
| 5 | **DTE Multi-Campus View** | A state map or list showing aggregate savings across sample campuses. |

### 2.4 Feature Prioritization (MoSCoW — useful for a "scope" slide)

**Must have:**
- Realistic data simulator (solar/wind/load/battery time series per campus) — needed since there's no real hardware access during the hackathon.
- Live dashboard: current generation mix, battery SOC, grid draw.
- Short-term forecast (6–24h) for generation + demand — directly requested in the problem statement.
- Recommendation engine (battery charge/discharge windows, load-shift suggestions, export/curtail calls) — this *is* the "orchestration" the problem statement asks for.
- Cost & carbon savings report.

**Should have:**
- At least one real protocol adapter (Modbus simulator) with a documented spec for others — proves "vendor-neutral" isn't just marketing.
- What-if scenario simulator.
- Explainability panel ("why this recommendation").
- Multi-campus/DTE aggregate view.

**Could have:**
- Reinforcement-learning-based optimizer (good as a "future roadmap" slide even if unbuilt).
- SMS/push alerts via a free-tier API.
- Gamified nudges for hostel/lab energy behavior.

**Won't do this round:** real hardware deployment, full cybersecurity hardening, live DISCOM billing integration — mention only as future work.

### 2.5 Demo Data Strategy (explain this if judges ask "how is this live without real hardware?")

Since there's no real solar array or wind turbine wired up, the system runs on a synthetic data generator that's grounded in real conditions:
- **Solar profile:** bell-curve output tied to time-of-day, modulated by a simulated cloud-cover factor pulled from a real weather API for a real Rajasthan location.
- **Wind profile:** power-curve model driven by a simulated wind-speed time series with realistic variability.
- **Load profile:** typical institutional daily curve — morning ramp, midday peak from labs/HVAC, evening hostel peak — with day-of-week variation.
- **Battery model:** simple state-of-charge state machine responding to charge/discharge commands from the optimizer.
- **Surprise events:** occasional sudden cloud cover or load spikes injected before the demo, so the recommendation engine visibly reacts in real time (simulator runs on a fast clock — 1 simulated hour ≈ a few real seconds).

### 2.6 Risks & Mitigations (good for a Q&A-readiness slide)

| Risk | Mitigation |
|---|---|
| Forecast inaccuracy during monsoon/heavy cloud cover | Show confidence intervals, not point forecasts; fall back to conservative "safe mode" recommendations. |
| Rural campus connectivity issues | Edge caching — local recommendations continue even if cloud sync drops. |
| Vendor protocol lock-in | Adapter layer architecture is the explicit mitigation. |
| Data security of grid/energy data | Role-based access, encryption in transit/at rest. |
| Autonomous control causing unsafe grid action | System stays advisory/human-in-the-loop by default; operator confirms critical actions. |
| Judges doubting "zero specialized training" claim | Hand the UI to a judge and let them click through it live. |

---

## PART 3 — Abbreviations & Glossary

Use this as a quick-reference sheet so every team member can define any term a judge throws at them.

| Abbreviation / Term | Full Form / Meaning |
|---|---|
| **VPP** | Virtual Power Plant — a software system that coordinates distributed energy resources (solar, wind, battery, grid) as if they were one single power plant. |
| **SIH** | Smart India Hackathon |
| **DTE** | Directorate of Technical Education (Government of Rajasthan) |
| **RERC** | Rajasthan Electricity Regulatory Commission — the state's power sector regulator |
| **VNM** | Virtual Net Metering — a regulatory mechanism allowing distributed renewable assets to be metered and credited as one virtual, aggregated asset |
| **GNM** | Group Net Metering — similar to VNM, but for a group of connected consumers sharing renewable credits |
| **SOC** | State of Charge — the current charge level of a battery, expressed as a percentage |
| **BMS** | Battery Management System — the hardware/firmware that monitors and controls a battery pack |
| **SCADA** | Supervisory Control and Data Acquisition — industrial control system software used to monitor equipment like wind turbines |
| **Modbus (RTU/TCP)** | A widely used industrial communication protocol for connecting electronic devices (common in solar inverters, meters, and controllers) |
| **MQTT** | Message Queuing Telemetry Transport — a lightweight messaging protocol commonly used for IoT sensor data |
| **OPC-UA** | Open Platform Communications Unified Architecture — an industrial interoperability standard for exchanging data between devices from different vendors |
| **MoSCoW** | A prioritization framework: **M**ust have, **S**hould have, **C**ould have, **W**on't have (this round) |
| **MILP** | Mixed-Integer Linear Programming — a mathematical optimization method used for scheduling/dispatch decisions |
| **RL** | Reinforcement Learning — a machine learning approach where an agent learns actions through trial-and-error rewards (mentioned as a future-roadmap optimizer) |
| **DISCOM** | Distribution Company — the utility company responsible for electricity distribution to consumers |
| **ESG** | Environmental, Social, and Governance — a reporting framework often used for sustainability metrics like the carbon-avoided numbers this platform generates |
| **Digital Twin** | A virtual, real-time model of a physical system (here, the campus's full energy state) used for simulation and decision-making |
| **Self-consumption** | The percentage of renewable energy generated on-site that is actually used on-site, rather than exported or wasted |
| **Curtailment** | Deliberately reducing renewable generation output (e.g., solar) when it can't be used or exported |
| **Load-shifting** | Moving a flexible electricity demand (e.g., a lab activity) to a time when renewable supply is higher, to increase self-consumption |

---

## PART 4 — Recommended Tech Stack (for an "implementation feasibility" slide)

| Layer | Recommendation | Why |
|---|---|---|
| Frontend | React (Vite) + Tailwind + Recharts/Chart.js | Fast to build, clean charts for generation/forecast curves |
| Backend/API | FastAPI (Python) | Keeps ML and API in one language — speed advantage in a time-boxed hackathon |
| Real-time layer | WebSockets (FastAPI) or MQTT broker (Mosquitto, simulated) | Gives the demo a genuinely "live" feel |
| Database | PostgreSQL + TimescaleDB extension (or InfluxDB) | Purpose-built for time-series sensor data |
| Forecasting | Prophet or a gradient-boosted regressor (LightGBM/XGBoost) | Fast to demo and explain; LSTM mentioned as a stretch/roadmap item |
| Optimization | Rule-based engine for MVP; PuLP/OR-Tools (MILP) as next step; RL (stable-baselines3) as long-term roadmap | A well-reasoned rule engine judges can follow beats an opaque model they can't |
| Weather/irradiance data | Open-Meteo (free, no key) or NASA POWER; Solcast as a premium production option | Needed for solar/wind generation forecasting |
| Adapter/simulation | Python scripts emulating Modbus/MQTT sensor streams | The actual data source, since no real hardware is available |
| Auth | Firebase Auth or simple JWT | Kept simple — not the differentiator |
| Deployment | Docker Compose; Render/Railway/Vercel free tiers | Reliable and quick for a live demo link |

---

## PART 5 — Feasibility & Regulatory Fit (your strongest differentiator slide)

- RERC already permits net metering up to 500 kW for rooftop solar consumers, with net billing for larger systems.
- RERC's Third Amendment Regulations (2025) introduced VNM and GNM, allowing distributed renewable projects (up to 1 MW) to be metered and credited as a *virtual, aggregated* asset — across government, commercial, and institutional consumer categories, aligned with Rajasthan's Integrated Clean Energy Policy 2024.
- **Say this explicitly on stage:** the "Virtual Power Plant" framing isn't just a technical metaphor — it maps directly onto a real, current state regulatory mechanism DTE campuses could plug into for real financial benefit. This signals genuine domain research, not just tech-stack assembly.
- *Verify current RERC tariff/VNM-GNM figures directly before quoting exact numbers live* — regulatory numbers move.

---

## PART 6 — Impact Numbers (frame as illustrative, not verified fact)

- Uncoordinated rooftop solar + isolated battery setups typically achieve **~55–65% self-consumption** of generated renewable energy.
- Coordinated dispatch (battery timed to true surplus/deficit, load-shifting recommendations) can realistically push that toward **~75–85%**, reducing grid dependence during peak tariff hours.
- Frame every number as *"typical ranges reported in campus-scale VPP pilots, to be validated with real site data during a pilot deployment."*
- Best move on stage: calculate the ₹/CO₂ savings live from your own simulator during the demo rather than quoting a canned figure — a number your dashboard computes live is far more credible than one printed on a slide.

---

## PART 7 — Judges' Q&A Cheat Sheet

| Likely Question | Your Answer |
|---|---|
| How does this scale to 50 campuses without 50 separate deployments? | Multi-tenant architecture, one adapter spec, centralized DTE aggregator view. |
| What happens without internet connectivity? | Local edge fallback with cached rules; sync resumes when connectivity returns. |
| Why should a facility manager trust an AI recommendation? | Explainability panel + advisory-only, human-confirmed actions. |
| What's the actual cost to deploy this at a real campus? | Software-only deployment on existing meters/inverters; only new cost is a low-cost gateway device per site, and only if needed. |
| How is this different from just buying a bigger battery? | A bigger battery without coordination logic still cycles on fixed schedules and misses real surplus/deficit windows — this is the "orchestration, not procurement" argument from the problem statement itself. |

---

## Quick Slide-by-Slide Mapping

1. Title — UrjaSetu branding + problem statement ID (Part 1)
2. Problem — grid dependence, isolated assets, no orchestration (Part 1)
3. Big Idea — one-liner + VPP analogy (Part 1)
4. Architecture — the 9-module diagram, simplified (Part 2.2)
5. What Makes This Different — USPs (Part 2.1)
6. Live Demo — dashboard + what-if simulator (Part 2.3, 2.5)
7. Feasibility & Regulatory Fit (Part 5)
8. Impact & Numbers, clearly labeled as pilot-stage projections (Part 6)
9. Scalability Plan — campus → all DTE institutions → statewide (Part 2.1, #4)
10. Roadmap & Ask — RL optimizer, real IoT integration, DISCOM API tie-in (Part 2.4, "Could have")

**Judging criteria to keep visible while designing every slide:** Novelty, Technical Complexity, Clarity of presentation, Feasibility of implementation, Practicability/real-world usability, Sustainability/scalability of impact. Address all six explicitly — don't assume the demo speaks for itself.
