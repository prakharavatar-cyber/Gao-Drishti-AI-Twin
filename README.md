# GaoDrishti AI: Smart Village Digital Twin

**From reactive repairs to predictive care.**

GaoDrishti AI is an AI-powered 3D digital twin for villages. It watches water, sanitation and infrastructure, spots problems before they become emergencies, and turns every alert into a prioritized work order that reaches the right office.

Built for the **SustainAI 2026 Ideathon** by a team from VIT Bhopal University.

> **Status: Phase 1 prototype.** The live demo runs entirely in your browser on **simulated sensor data**. See [What is real and what is simulated](#what-is-real-and-what-is-simulated).

---

## The problem

Villages cannot see problems coming. Six issues stay hidden until they become severe:

- Contaminated water
- Groundwater depletion
- Sewage overflow
- Garbage build-up
- Potholes
- Waterlogging

Today they are found only through manual checks or complaints. Records are scattered across departments, and officials have no single real-time view. Action starts only after the problem has escalated, which hits households, farmers, children and the elderly hardest.

## The solution

**Collect → Detect → Predict → Prioritize → Recommend**

| Module | What it does | Input → Output |
|---|---|---|
| **Water AI** | Flags abnormal pH, TDS, turbidity, water level and flow | Sensor data → anomaly alerts |
| **Predictive AI** | Forecasts groundwater depletion, shortages, sewage overflow and maintenance needs | Time series → risk forecast |
| **Computer Vision** *(planned)* | Spots potholes, garbage, waterlogging and blocked drains from images | Camera images → issue alerts |

Alerts are ranked by **severity × location × population affected × asset importance**, then routed to the right jurisdiction (Panchayat, Block, District or Municipal).

## Live demo

Open https://www.linkedin.com/safety/go/?url=https%3A%2F%2Flnkd.in%2FdDkT6GPH&urlhash=Rjgk&mt=XcSakoB4thrjGJBbuCgJVFNynDjCMuFcuT3WXCdU6_y6n1ZJILbzsvaW7-DNFeTCEACSK5c4eRLInMWUjSX96ZCxoFUAKFcln-zkRxVOqGCDn7bIlodDKN2gFNM&isSdui=true&lipi=urn%3Ali%3Apage%3Ad_flagship3_detail_base%3BEwLmlQMlSyGj2hbyf2VkIQ%3D%3D in any modern browser. No install or build step is needed.

A hosted version is available at: **_add your GitHub Pages link here_**

Click **Run guided demo** for a walkthrough, or use the **Inject a scenario** buttons to trigger faults yourself.

## What the demo shows

- **Interactive 3D village** with wells, hand pumps, groundwater sensors, water tank, rainwater pits, drains, roads, street lights and street cameras.
- **Click any asset** to see its live readings, trend, AI risk score, forecast and recommended action.
- **Scenario injection**: contaminate water, block a drain, create potholes, fail street lights, dry an open well, over-pump a borewell, fail a sensor or a camera, and toggle day or night.
- **Automatic work orders** for every alert, with verification and closure tracking.
- **Auto-drafted reports** to the SDM office and the Pradhan office, plus an SMS to villagers.
- **Citizen app**: residents report potholes, lights, cameras and other issues with a photo, in **Hindi or English**. The request goes to the Pradhan office, becomes a work order, and the resident is notified when it is fixed.
- **Pradhan office monitor** with all reports, SMS status and acknowledgements.
- **Basti (urban slum) view**: a denser settlement where shared taps and open drains score higher priority because more people are affected. Issues route to the **Nagar Nigam** office and ward heads, then to the SDM for verification.
- **Compound-risk logic**: for example, low drain flow combined with a rising level suggests a blockage.
- **Offline-safe design**: a sensor or camera that stops reporting raises its own alert and work order.

## How it works

```
Sensors / cameras  →  AI engine  →  Central database  →  3D digital twin
                                                              ↓
Updated records  ←  Maintenance  ←  Work orders  ←  Govt. dashboard
```

**Alert-to-action loop:**
`Sensor or citizen report → AI detects anomaly → High risk flagged → Work order created → Officer verifies → Maintenance carried out → Database updated`

## What is real and what is simulated

| Component | In this repo today | Planned |
|---|---|---|
| 3D digital twin | Working (Three.js, single HTML file) | React-based app with GIS layers |
| Sensor data | **Simulated** in the browser | ESP32 nodes over LoRa / Wi-Fi / 4G |
| Anomaly detection | Rule-based thresholds on pH, TDS, turbidity, level and flow | Scikit-learn models |
| Forecasting | Trend slope over recent readings | Time-series forecasting models |
| Computer vision | Simulated camera and photo reports | YOLO + OpenCV |
| Backend and database | None (in-memory) | FastAPI + PostgreSQL / MySQL |
| SMS and report delivery | Simulated | SMS gateway and official channels |

## Planned architecture

| Layer | Technology |
|---|---|
| Field and edge | ESP32 with pH, TDS/EC, turbidity, level and flow sensors; cameras and drones |
| Network | LoRa, Wi-Fi, 4G |
| Backend and database | FastAPI, PostgreSQL / MySQL |
| AI / ML | Python, Scikit-learn, OpenCV, YOLO |
| Frontend | React, Three.js, Leaflet / OpenStreetMap |
| Reporting | Excel and PDF exports |
| Users | Gram Panchayat, Water & Sanitation Dept., District / SDM, Municipal bodies |

## Roadmap

- [x] **Phase 1 · Ideathon**: 3D digital village, simulated IoT data, AI detection, dashboard and citizen app
- [ ] **Phase 2 · Pilot village**: real sensors, LoRa communication, real-time database, local government dashboard
- [ ] **Phase 3 · Multi-village**: multiple Panchayats, district dashboard, automated reporting, GIS integration
- [ ] **Phase 4 · District / State**: government system integration, large-scale predictive analytics, resource allocation

**Future scope:** drone inspection, satellite data, smart irrigation, flood prediction, advanced groundwater forecasting, automated SMS alerts.

## Impact and SDG alignment

| SDG | Contribution |
|---|---|
| **SDG 6** Clean Water & Sanitation | Early alerts on contamination and groundwater depletion |
| **SDG 9** Industry, Innovation & Infrastructure | Predictive maintenance with low-cost sensing |
| **SDG 11** Sustainable Cities & Communities | Safer, better-managed villages and urban settlements |
| **SDG 12** Responsible Consumption | Garbage detection and verified collection |

## Repository contents

```
GaoDrishti_Digital_Twin.html   # Self-contained interactive demo
LICENSE                        # MIT
README.md
```

## Team GaoDrishti AI

| Name | Role |
|---|---|
| **Prakhar Kapoor** | Team lead |
| **Vaishnavi Dixit** | Team member |
| **S Rithanya** | External academic team |

VIT Bhopal University, SCAI & SBET
