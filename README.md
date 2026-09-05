# UrjaSetu

<p align="center">
  <strong>Smart Energy Orchestration Platform for Government Campuses</strong>
</p>

<p align="center">
  Connecting Solar, Wind, Battery and Grid into one intelligent energy system
</p>

---

## Project Overview

UrjaSetu is a software layer that coordinates existing solar, wind, battery and grid infrastructure into one intelligent energy management system.

It requires no new solar panels, batteries or major hardware infrastructure. Instead, it works on top of existing campus energy infrastructure to monitor, forecast, optimize and recommend better energy decisions.

---

## Why UrjaSetu?

Modern campuses may have:

- Solar panels
- Wind turbines
- Battery storage
- Grid electricity

However, these systems often operate independently.

UrjaSetu acts as the coordination layer between these resources. It continuously monitors the energy ecosystem and recommends what should happen next.

Examples include:

- Charge the battery when surplus renewable energy is available.
- Shift energy-intensive loads to a better time.
- Use stored energy when grid electricity is expensive.
- Export surplus energy when appropriate.

---

## Virtual Power Plant

UrjaSetu applies the concept of a Virtual Power Plant to government campuses.

```text
                 +--------------------------+
                 |   STATE-LEVEL DASHBOARD |
                 +------------+-------------+
                              |
             +----------------+----------------+
             |                |                |
       +-----v-----+    +-----v-----+    +-----v-----+
       | CAMPUS 01 |    | CAMPUS 02 |    | CAMPUS 03 |
       +-----+-----+    +-----+-----+    +-----+-----+
             |                |                |
       Solar / Wind      Solar / Wind      Solar / Wind
       Battery / Grid    Battery / Grid    Battery / Grid
````

Each campus becomes its own coordinated energy system, while the government can monitor multiple campuses through one centralized dashboard.

---

## How UrjaSetu Works

```text
Solar
   |
Wind
   |
Battery
   |
Grid
   |
   v
+-------------------+
|  Data Collection  |
+---------+---------+
          |
          v
+-------------------+
| Translator Layer  |
| Modbus / MQTT /   |
| OPC-UA            |
+---------+---------+
          |
          v
+-------------------+
| Forecasting Engine|
| Weather + Usage   |
+---------+---------+
          |
          v
+-------------------+
|    Digital Twin   |
+---------+---------+
          |
          v
+-------------------+
| Optimization      |
| Engine            |
+---------+---------+
          |
          v
+-------------------+
| Recommendation    |
| Engine            |
+---------+---------+
          |
          v
+-------------------+
| Human Confirmation |
+---------+---------+
          |
          v
+-------------------+
| Action & Reporting|
+-------------------+
```

### Workflow

1. Data comes in from solar, wind, battery, grid and smart meters.
2. The translator layer converts different equipment protocols into a common format.
3. Forecasting predicts generation and demand using weather and usage patterns.
4. The digital twin creates a unified live model of campus energy.
5. The optimization engine determines the most efficient action.
6. The recommendation engine converts technical results into simple action cards.
7. A human reviews and confirms the recommendation.
8. The system reports savings, energy usage and carbon impact.

---

## Core Features

| Feature                | Description                                                      |
| ---------------------- | ---------------------------------------------------------------- |
| Live Dashboard         | Real-time solar, wind, battery and grid monitoring               |
| Short-Term Forecasting | Predicts generation and demand 6–24 hours ahead                  |
| Recommendation Engine  | Converts forecasts into actionable decisions                     |
| Explainability Panel   | Explains why each recommendation was generated                   |
| What-If Simulator      | Tests scenarios before making investments or operational changes |
| Cost Reports           | Tracks energy savings                                            |
| Carbon Reports         | Tracks avoided carbon emissions                                  |
| Vendor-Neutral Adapter | Supports different equipment manufacturers                       |
| Multi-Campus View      | Enables centralized government-level monitoring                  |
| Safety-First Design    | Human confirmation before operational changes                    |

---

## Recommendation Engine

The recommendation engine is the decision-making component of UrjaSetu.

Instead of presenting facility staff with complicated energy data, the system generates understandable recommendations.

Example:

```text
+-----------------------------------------------+
|              RECOMMENDATION                   |
+-----------------------------------------------+
|                                               |
|  Charge Battery Now                           |
|                                               |
|  Surplus solar energy is expected during      |
|  the next 2 hours.                            |
|                                               |
|  Estimated Benefit: Rs. XXX                   |
|                                               |
|       [ APPROVE ]        [ REJECT ]            |
|                                               |
+-----------------------------------------------+
```

Every recommendation includes an explanation so users can understand why the system suggested a particular action.

---

## What-If Simulator

The What-If Simulator allows decision-makers to evaluate possible changes before spending money or modifying operations.

### Example: Additional Solar Capacity

```text
Add 5 Solar Panels
        |
        v
Projected Generation
        |
        v
Projected Savings
        |
        v
Carbon Reduction
```

### Example: Load Shifting

```text
Shift Workshop Operating Hours
        |
        v
New Energy Demand Pattern
        |
        v
Grid Cost Difference
        |
        v
Projected Savings
```

This enables data-driven planning instead of trial and error.

---

## Energy Intelligence

UrjaSetu combines multiple data sources to create a unified view of campus energy.

```text
             WEATHER DATA
                   |
                   v
           +---------------+
           |  FORECASTING  |
           +-------+-------+
                   |
                   v
Solar --------> DIGITAL <-------- Wind
                TWIN
                   |
             Battery + Grid
                   |
                   v
             OPTIMIZATION
                   |
                   v
            RECOMMENDATION
```

The forecasting engine uses weather information, campus schedules and historical usage to estimate future generation and demand.

---

## Expected Impact

UrjaSetu aims to improve renewable-energy utilization through intelligent coordination.

```text
Current Illustrative Range
          55–65%
             |
             | Coordination
             v
Target Illustrative Range
          75–85%
```

Potential benefits include:

* Reduced electricity costs
* Better renewable-energy utilization
* More efficient battery operation
* Lower carbon emissions
* Improved energy planning
* Centralized monitoring
* Data-driven decision making

These figures are illustrative ranges rather than guaranteed results. Actual performance should be calculated using pilot data and the project simulator.

---

## Safety-First Architecture

UrjaSetu is designed as an advisory system.

```text
AI / Optimization
       |
       v
 Recommendation
       |
       v
 Human Review
       |
   +---+---+
   |       |
   v       v
APPROVE   REJECT
   |
   v
 ACTION
```

The system does not automatically take control of campus infrastructure. A human confirms the recommendation before any operational change.

---

## Vendor-Neutral Architecture

Different energy devices may use different communication protocols.

UrjaSetu provides an adapter layer that converts these different protocols into a common format.

```text
Solar Inverter ---- Modbus ----+
                               |
Battery ---------- MQTT -------+
                               |
Smart Meter ------- OPC-UA ----+----> UrjaSetu
                               |
Wind System -------------------+
```

This allows existing infrastructure from different vendors to work with the same software platform.

---

## Multi-Campus Government View

UrjaSetu is designed to scale beyond a single campus.

```text
                 STATE DASHBOARD
                       |
          +------------+------------+
          |            |            |
          v            v            v
       Campus A     Campus B     Campus C
          |            |            |
       Energy        Energy        Energy
          |            |            |
       Savings       Savings       Savings
          |            |            |
          +------------+------------+
                       |
                       v
                STATEWIDE IMPACT
```

The Directorate can monitor energy savings and impact across participating campuses through a centralized interface.

---

## Feasibility

UrjaSetu is designed around infrastructure that already exists.

```text
Solar Panels
     +
Batteries
     +
Smart Meters
     +
Grid Connection
     |
     v
UrjaSetu Software Layer
```

The platform follows a zero-new-hardware approach wherever possible.

A low-cost gateway device may be used at sites where legacy equipment cannot communicate digitally.

---

## System Architecture

```text
                    +----------------------+
                    |      FRONTEND        |
                    |   Live Dashboard     |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    |       BACKEND        |
                    |   APIs & Processing   |
                    +----------+-----------+
                               |
             +-----------------+-----------------+
             |                 |                 |
             v                 v                 v
       +-----------+     +-----------+     +-----------+
       | Forecast  |     | Digital   |     | Optimizer |
       |  Engine   |     |   Twin    |     |   Engine  |
       +-----+-----+     +-----+-----+     +-----+-----+
             |                 |                 |
             +-----------------+-----------------+
                               |
                               v
                    +----------------------+
                    | Recommendation Engine|
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    | Human Confirmation   |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    | Reports & Analytics  |
                    +----------------------+
```

---

## Technology Stack

| Layer        | Purpose                                 |
| ------------ | --------------------------------------- |
| Python       | Data processing and AI/ML               |
| AI/ML        | Energy forecasting and optimization     |
| IoT          | Sensor and smart-meter integration      |
| APIs         | Communication between system components |
| Database     | Energy data and historical records      |
| Dashboard    | Real-time monitoring and analytics      |
| Digital Twin | Unified energy-state representation     |
| Optimization | Energy scheduling and decision-making   |

---

## Future Scope

```text
Current Prototype
       |
       v
Advanced Optimization
       |
       v
AI / Reinforcement Learning
       |
       v
Real Hardware Integration
       |
       v
Electricity Billing Integration
       |
       v
SMS and Push Notifications
       |
       v
Gamified Energy Saving
       |
       v
Statewide Expansion
```

Future development can include:

* Advanced mathematical optimization
* AI and reinforcement learning
* Real hardware integration
* Electricity billing integration
* SMS and push notifications
* Gamified energy-saving systems
* Expansion across technical education institutions
* Integration with additional energy infrastructure

---

## Business Model

### B2G SaaS

UrjaSetu can operate as a Business-to-Government Software-as-a-Service platform.

```text
Per-Campus Subscription
          +
Tiered Pricing
          +
Low-Cost Gateway Setup
          +
State-Level Enterprise Contract
          +
Future Energy Trading Facilitation
```

The model focuses on software licensing and subscriptions instead of requiring large upfront hardware investments.

---

## Project Links

The following links can be added once the project resources are available:

| Resource          | Link                      |
| ----------------- | ------------------------- |
| GitHub Repository | `YOUR_GITHUB_LINK`        |
| Live Demo         | `YOUR_DEMO_LINK`          |
| Project Website   | `YOUR_WEBSITE_LINK`       |
| Documentation     | `YOUR_DOCUMENTATION_LINK` |
| Demo Video        | `YOUR_VIDEO_LINK`         |
| Presentation      | `YOUR_PRESENTATION_LINK`  |

---

## Project Vision

> Public campuses already own the hardware for clean energy. What they are missing is the brain that makes it work together.

UrjaSetu provides that brain through a vendor-neutral, explainable and software-first energy orchestration platform.

```text
Solar
  +
Wind
  +
Battery
  +
Grid
  |
  v
URJASETU
  |
  v
Energy Intelligence
  |
  +---- Cost Savings
  |
  +---- Renewable Utilization
  |
  +---- Carbon Reduction
  |
  +---- Better Decision Making
```

---

## UrjaSetu

**Connecting Energy. Optimizing Tomorrow.**

Built for smarter campuses, cleaner energy and scalable government impact.

```

This version has **zero ECC references, zero ECC links, and zero emojis**.
```
