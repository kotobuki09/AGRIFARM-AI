# AGRIFARM-AI: Intelligent Management System for Climate-Resilient Smart Agriculture

**AGRIFARM-AI** is an autonomous agricultural management platform integrating hybrid VLC/RF networks, multi-agent reinforcement learning, and agentic AI for precision farming in controlled environments.

---

## 🚧 Status: Under Active Development
Current phase: **Architecture Design**

---

## Project Overview

AGRIFARM-AI is an ambitious research project developing an **Intelligent Management System (IMS)** for climate-resilient smart agriculture. The system integrates cutting-edge technologies to enable autonomous precision farming in controlled environments.

### Key Innovation Areas

| Area | Technology | Impact |
|------|------------|--------|
| **Communication** | Hybrid VLC/RF Networks | 73% RF reduction, crop-safe |
| **Decision Making** | Multi-Agent RL (MARL) | Autonomous coordination |
| **Intelligence** | Agentic AI + LLM | Natural language farming advice |
| **Privacy** | Federated Learning | Cross-border knowledge sharing |

---

## System Architecture

### Core IMS Components

The system extends our proven IMS architecture (ACM MobiCom 2023) with four specialized agricultural agents:

#### 🔄 Agri-IHC (Intelligent Handover Controller)
- **Function:** Seamless VLC/RF network transitions
- **Agricultural Adaptation:** VLC-priority in grow zones; RF for mobile robots
- **Target:** <250ms handover latency

#### 📍 Agri-ETL (Edge Tracking & Localization)
- **Function:** Federated learning-based positioning
- **Agricultural Adaptation:** Drone/robot tracking; worker localization via WiFi Doppler
- **Target:** <30cm accuracy in greenhouse

#### 💧 Agri-ARS (Adaptive Resource Management)
- **Function:** ML-based resource allocation
- **Agricultural Adaptation:** Precision irrigation scheduling; sensor prioritization
- **Target:** 40% water savings, 30% fertilizer reduction

#### ⚡ Agri-EHM (Energy Harvesting Management)
- **Function:** LED brightness optimization
- **Agricultural Adaptation:** Dual-purpose grow lights (PAR + VLC)
- **Target:** 25% energy cost reduction

---

## 15-Dimensional Agricultural State Space

Our MARL agents operate on an expanded state space validated with agronomic literature:

### Environmental Variables (5)
```
SoilMoisture       [0-100%]     Volumetric water content
AirTemperature     [15-40°C]    Metabolic rate driver
RelativeHumidity   [20-100%]    Disease pressure indicator
SolarRadiation     [0-1000 W/m²] Photosynthesis driver
CO2Concentration   [400-1000 ppm] CEA optimization
```

### Crop State Variables (4)
```
GrowthStage        [BBCH 0-9]   Seedling → Harvest
LeafAreaIndex      [0-8 m²/m²]  Canopy development
CropStressIndex    [0-1]        NDVI-derived stress
DaysToHarvest      [0-120]      Countdown timer
```

### Soil Variables (3)
```
SoilpH             [4-9]        Nutrient availability
ElectricalConductivity [0-8 dS/m] Salinity indicator
NPKLevel           [Low/Med/High] Composite nutrient index
```

### Network Variables (3)
```
RSSIcurrent        [-90 to -30 dBm] Signal strength
APType             [VLC=1, RF=0]    Access point type
SensorLoad         [0-100%]         Network utilization
```

---

## Climate Resilience Causal Chain

Complete pathway from forecast to validated outcome:

```
┌─────────────────┐
│ 1. Data Collection │ IoT sensors + ERA5 climate data
│    (Real-time)      │ Every 15 minutes
└────────┬────────┘
         ▼
┌─────────────────┐
│ 2. Prediction      │ SEACLID regional model + LLM
│    (48-72 hours)   │ Heat stress, drought, pest risk
└────────┬────────┘
         ▼
┌─────────────────┐
│ 3. Decision        │ LLM + RAG knowledge base
│    Support         │ "Reduce irrigation 20% now"
└────────┬────────┘
         ▼
┌─────────────────┐
│ 4. Action          │ IMS-ARS automated execution
│    Execution       │ OR farmer SMS notification
└────────┬────────┘
         ▼
┌─────────────────┐
│ 5. Outcome         │ Treatment vs. control plot
│    Validation      │ Quantified yield improvement
└─────────────────┘
```

---

## MARL Coordination Mechanism

### Agent Interaction Model

**Coordination:** Centralized Training, Decentralized Execution (CTDE)

**Value Decomposition:** QMIX algorithm

**Convergence:** Nash equilibrium via fictitious play (<1000 episodes)

### Reward Functions

| Agent | Reward Formula |
|-------|----------------|
| **IHC** | r = RSSI_quality - 0.1 × handover_cost |
| **ARS** | r = yield_proxy - 0.05 × water_cost - 0.1 × energy_cost |
| **EHM** | r = energy_stored - 0.2 × light_impact_on_crop |

---

## Federated Learning Framework (AgriFL)

Privacy-preserving cross-border agricultural intelligence:

### Data Schema

| Sensor Type | Frequency | Volume/Season |
|-------------|-----------|---------------|
| Soil moisture | 15 min | 50 MB |
| Temperature/humidity | 15 min | 20 MB |
| Camera (pest/disease) | 1 hr | 500 MB |
| Weather station | 1 hr | 10 MB |
| **Total** | | **~580 MB** |

### Privacy Guarantees
- **Differential Privacy:** ε ≤ 0.5
- **Secure Aggregation:** No raw data leaves farm
- **Cluster-based FL:** Tropical (ASEAN) + Temperate (EU)

---

## Target KPIs

| Metric | Baseline | Target |
|--------|----------|--------|
| Yield improvement | - | +15% under climate stress |
| Water use efficiency | - | +40% |
| Nitrogen use efficiency | - | +30% |
| Pest/disease reduction | - | -50% |
| Energy consumption | - | -25% |

---

## Technology Stack

### Hardware
- **Edge Gateways:** Jetson Nano (<50ms inference)
- **VLC Platform:** OpenVLC 1.3 + BeagleBone Black
- **Sensors:** Low-cost nodes (€50/unit vs. €200+ commercial)

### Software
- **MARL Framework:** QMIX with PyTorch
- **Foundation Model:** LLaMA-3.1-8B (5M agricultural tokens)
- **FL Framework:** AgriFL with Byzantine-robust aggregation
- **Climate APIs:** ERA5, SEACLID

---

## Development Timeline

```
2026        2027        2028        2029
  │           │           │           │
  ├──Phase 1──┼──Phase 2──┼──Phase 3──┼──Phase 4──┤
  │           │           │           │           │
  │ Design    │ Integration│ Validation│ Transfer  │
  │ Farmer    │ MARL Train │ 4 Trials │ Open-Source│
  │ Co-Design │ Edge AI    │ Impact   │ Commercial │
  └───────────┴───────────┴──────────┴───────────┘
```

---

## Publications & Resources

### Related Publications
- ACM MobiCom 2023: IMS Architecture for Hybrid VLC/RF
- LNEE 2024: Offline RL for Agricultural IoT (90.4% success)
- IEEE ICCC: VLC/WiFi MAC Optimization

### Links
- 📂 GitHub: [kotobuki09/AGRIFARM-AI](https://github.com/kotobuki09/AGRIFARM-AI)
- 📄 Documentation: *Under development*

---

> **🌱 Vision:** Every smallholder farmer equipped with AI-powered climate resilience, accessible through open-source technology and natural language interfaces.

---

## 👨‍💼 Author

<table>
  <tr>
    <td>
      <a href="https://kngo.netlify.app/">
        <img src="images/profile.png" alt="NGO TRUNG KIEN" width="120" style="border-radius: 50%;">
      </a>
    </td>
    <td>
      <strong>NGÔ TRUNG KIÊN</strong><br>
      🌐 <a href="https://kngo.netlify.app/">kngo.netlify.app</a><br>
      📧 kiennt@hsb.edu.vn<br>
      🏫 Hanoi School of Business and Management (HSB)<br>
      📱 Faculty: Non-Traditional Security
    </td>
  </tr>
</table>

---
