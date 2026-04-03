# InsurEdge 🛵⚡
### AI-Powered Parametric Micro-Insurance for Gig Workers

> Protecting delivery riders from income loss caused by disruptions they never saw coming — and never caused.

---

## Table of Contents
1. [Overview](#overview)
2. [Problem Statement](#problem-statement)
3. [How It Works](#how-it-works)
4. [AI Models](#ai-models)
   - [Risk Score Model](#1-risk-score-model)
   - [Trust Score Model](#2-trust-score-model)
   - [Dynamic Premium Model](#3-dynamic-premium-model-planned)
5. [Disruption Factor Coverage](#disruption-factor-coverage)
6. [Parametric Trigger System](#parametric-trigger-system)
7. [Fraud & Market Crash Defense](#fraud--market-crash-defense)
8. [System Architecture](#system-architecture)
9. [Tech Stack](#tech-stack)
10. [Datasets](#datasets)
11. [Repo Structure](#repo-structure)
12. [Future Scope](#future-scope)

---

## Overview

**InsurEdge** is a parametric micro-insurance platform built specifically for gig economy delivery workers. It monitors real-world disruption conditions, predicts rider risk, evaluates behavioral trust, and processes compensation automatically — with no manual claim filing.

The platform serves riders on **Swiggy, Zomato, Blinkit, and Zepto** whose weekly earnings collapse during events completely outside their control: floods, extreme heat, riots, zone shutdowns, or infrastructure failures.

| Field | Details |
|---|---|
| Insurance Type | Weekly parametric micro-insurance |
| Claim Mechanism | Automated — no manual filing required |
| Core Intelligence | Risk Score · Trust Score · Dynamic Premium · Fraud Detection |
| Primary Users | Gig delivery workers in urban India |

---

## Problem Statement

Delivery riders earn based on hours worked and orders completed. Dozens of external disruptions can erase a week's earnings in hours — and today, riders have zero financial protection against any of them.

**InsurEdge closes this gap** with a system that detects disruptions, validates them against real data, and pays out fairly and automatically.

| Disruption Category | Example | Current Protection |
|---|---|---|
| Weather | Heavy rainfall, flooding | None |
| Environmental | Hazardous AQI, extreme heat | None |
| Civil unrest | Protests, riots, curfews | None |
| Conflict / Security | Military operations, border incidents, strikes | None |
| Infrastructure | Power outages, road collapses | None |
| Traffic | Severe congestion, accidents | None |
| Platform | Delivery zone shutdowns | None |

---

## How It Works

InsurEdge runs a continuous intelligence pipeline across four stages:

```
Rider Onboarding
       ↓
Risk Score Prediction  ←  Environmental + Road Accident Data
       ↓
Trust Score Evaluation ←  Insurance Claim Behavior Data
       ↓
Premium Calculation    ←  Risk + Trust + Exposure
       ↓
Live Trigger Monitoring ← Weather / AQI / Traffic / Civil APIs
       ↓
Fraud & Anomaly Checks
       ↓
Automated Payout
```

Every stage is data-driven. No human approver sits in the critical path for routine claims.

---

## AI Models

### 1. Risk Score Model

**Purpose:** Predict how dangerous a rider's working environment is on a 0–100 scale.

**Dataset:** [Indian Road Accident Dataset 2022–2025](https://www.kaggle.com/datasets/sehaj1104/indian-road-accident-dataset-20222025) (Kaggle)

**Approach:** A composite risk score is engineered from accident-correlated features, then three regressors are trained and the best-performing model (by R²) is selected automatically.

| Model Tried | Metric Used for Selection |
|---|---|
| Random Forest Regressor | R², MAE, RMSE |
| XGBoost Regressor | R², MAE, RMSE |
| CatBoost Regressor | R², MAE, RMSE |

**Key Features Used:**
- `traffic_density` — congestion level of working area
- `weather` — rainfall intensity, fog, storm conditions
- `visibility` — riding safety proxy
- `accident_severity` — historical accident weight for the zone

**Output Labels:**

| Score Range | Risk Category |
|---|---|
| 0 – 20 | Very Low Risk |
| 21 – 40 | Low Risk |
| 41 – 60 | Moderate Risk |
| 61 – 80 | High Risk |
| 81 – 100 | Severe Risk |

The risk score feeds directly into premium calculation and trigger sensitivity tuning.

---

### 2. Trust Score Model

**Purpose:** Estimate how reliable a rider is as an insurance participant — distinguishing genuine users from those showing suspicious claim behavior.

**Dataset:** [Car Insurance Claim Prediction](https://www.kaggle.com/datasets/ifteshanajnin/carinsuranceclaimprediction-classification) (Kaggle)

**Approach:** A **CatBoostClassifier** is trained to predict claim probability. Trust Score is derived as:

```
Trust Score = (1 - Claim_Probability) × 100
```

**Output:**

| Trust Score | Label | Insurance Effect |
|---|---|---|
| 80 – 100 | High Trust | Fast-tracked payouts, stable premium |
| 60 – 79 | Medium Trust | Standard processing |
| 0 – 59 | Low Trust | Additional verification, higher premium band |

**Premium Band Assignment (from Trust Score):**

```python
if trust_score >= 80:   → "Low Premium"
elif trust_score >= 60: → "Standard Premium"
else:                   → "High Premium"
```

The trust score acts as a behavioral modifier layered on top of the environment-based risk score.

---

### 3. Dynamic Premium Model *(Planned)*

The premium model will combine Risk Score + Trust Score + working hours + zone exposure into a single weekly premium figure. It replaces the flat-rate band system with a continuous regression output.

| Input | Role |
|---|---|
| Risk Score (0–100) | Primary pricing driver |
| Trust Score (0–100) | Behavioral adjustment |
| Weekly Working Hours | Exposure duration |
| Zone Type | Urban density multiplier |
| Historical Disruption Rate | Area volatility |

Estimated output range: ₹20 – ₹60/week based on synthetic simulations.

---

## Disruption Factor Coverage

InsurEdge is designed to scale beyond weather. The table below covers current triggers and planned expansions:

### Currently Monitored
| Factor | Data Source | Trigger Condition |
|---|---|---|
| Rainfall | Weather API | > threshold mm/hr |
| Flooding | Flood alert APIs | Zone flood alert active |
| AQI | AQI APIs | Hazardous AQI category |
| Extreme Heat | Weather API | Temperature > 42°C |
| Traffic Congestion | Maps / Traffic API | Severe congestion flag |
| Delivery Zone Shutdown | Platform data (mock) | Inactivity detected |

### Planned Expansions *(Future Scope)*

| Factor | Category | Implementation Plan |
|---|---|---|
| **War / Military Operations** | Conflict | Government alert APIs + district-level conflict feeds; trigger if rider's zone is under active security lockdown or curfew due to military activity |
| **Riots & Civil Unrest** | Conflict | News sentiment APIs + police alert feeds; cluster detection for sudden same-area claim spikes |
| **Strikes & Shutdowns** | Operational | Trade union / government public notices; manual whitelist of verified bandh events |
| **Terrorist Incidents** | Security | National security alert APIs; geographic radius trigger around incident zone |
| **Border Conflicts (Local)** | Security | Ministry of Home Affairs API feeds; affects riders in border district zones |
| **Infrastructure Collapse** | Disaster | Road authority APIs; bridge closures, highway blocks |
| **Power Grid Failures** | Infrastructure | State electricity board outage feeds; extended blackouts disrupting platform operations |
| **Epidemic / Disease Outbreak** | Health | Health ministry alerts; localized lockdown or containment zone triggers |
| **Earthquake / Natural Disaster** | Disaster | IMD + NDMA feeds; seismic or disaster zone classification |
| **Political Rallies / VIP Movement** | Operational | Traffic authority notifications; route closures exceeding X hours |

> **Implementation Note:** Each new factor requires (a) a reliable real-time data source, (b) a validated threshold, and (c) an external-reality check to prevent fraudulent exploitation. New factors are only added to the trigger system once all three conditions are met.

---

## Parametric Trigger System

Unlike traditional insurance, InsurEdge does not ask riders to prove their loss. It verifies conditions against real data and activates payouts automatically.

**A payout is triggered when:**
1. A verified disruption event meets threshold conditions
2. The rider was active / registered in the affected zone
3. Trust Score passes minimum threshold
4. No fraud signals are detected

**A payout is held when:**
- Trigger condition was not externally verifiable
- Rider location data is inconsistent
- Suspicious claim clustering is detected
- Trust Score falls below the hold threshold

---

## Fraud & Market Crash Defense

Parametric systems are attractive targets for coordinated fraud. InsurEdge defends against this with a multi-layer validation stack:

| Threat | Defense Layer |
|---|---|
| GPS Spoofing | Location consistency checks against historical routes |
| Mass Coordinated Claims | Cluster anomaly detection — sudden same-zone claim spikes |
| Fake Disruption Claims | All triggers verified against external API data |
| New Suspicious Accounts | Trust Score cold-start penalty |
| Repeated Abuse Patterns | Trust Score decay on suspicious claim history |

**Market Crash Scenario** (e.g. a fraud ring exploits a rain event):

```
Suspicious cluster detected
         ↓
External weather API verification
         ↓
Individual trust scores checked
         ↓
Location history cross-referenced
         ↓
High-risk claims held for review
Genuine riders paid normally
```

---

## System Architecture

```
┌─────────────────────────────────────────────┐
│                  Frontend                   │
│           Flutter Web / Android             │
└────────────────────┬────────────────────────┘
                     │
┌────────────────────▼────────────────────────┐
│                   Backend                   │
│                  FastAPI                    │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│  │   Risk   │  │  Trust   │  │ Premium  │  │
│  │  Model   │  │  Model   │  │  Model   │  │
│  └──────────┘  └──────────┘  └──────────┘  │
│         ┌───────────────────────┐           │
│         │  Fraud / Trigger Engine│          │
│         └───────────────────────┘           │
└──────┬─────────────────────┬────────────────┘
       │                     │
┌──────▼──────┐     ┌────────▼────────────┐
│  Supabase   │     │   External APIs     │
│ PostgreSQL  │     │ Weather · AQI       │
│  (Storage)  │     │ Traffic · Maps      │
└─────────────┘     │ Alert Feeds (future)│
                    └─────────────────────┘
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Flutter |
| Backend | FastAPI (Python) |
| Database | Supabase / PostgreSQL |
| ML Development | Python, Google Colab |
| ML Models | CatBoost, XGBoost, Random Forest |
| ML Libraries | Pandas, NumPy, Scikit-learn, Joblib |
| Visualization | Matplotlib, Seaborn |
| Deployment | Vercel (frontend) + cloud backend |
| External APIs | OpenWeatherMap, AQI APIs, Google Maps |
| Payments (Mock) | Razorpay Sandbox |

---

## Datasets

| Model | Dataset | Source |
|---|---|---|
| Risk Score | Indian Road Accident Dataset 2022–2025 | [Kaggle](https://www.kaggle.com/datasets/sehaj1104/indian-road-accident-dataset-20222025) |
| Trust Score | Car Insurance Claim Prediction | [Kaggle](https://www.kaggle.com/datasets/ifteshanajnin/carinsuranceclaimprediction-classification) |
| Premium Model *(planned)* | Synthetic + domain-derived | Internal generation |
| Fraud Model *(planned)* | Anomaly / behavioral signals | Internal generation |

---


## Future Scope

| Feature | Description |
|---|---|
| War / Conflict Triggers | Integrate government & security alert APIs to trigger payouts in active conflict or curfew zones |
| Epidemic Triggers | Health ministry feeds for containment zone detection |
| Infrastructure Failure Triggers | Power grid and road authority outage APIs |
| Risk Heatmaps | City-level disruption visualization for zone-aware pricing |
| Explainability Layer | Per-rider explanation of why premium changed or claim was held |
| Adaptive Fraud Intelligence | Online learning for evolving fraud patterns |
| Multi-Platform Support | Expand beyond food delivery to cab, logistics, and field workers |
| Instant Wallet Payouts | UPI-linked payout disbursement within hours of trigger |

---

> **InsurEdge** — Because gig workers shouldn't carry risks they didn't create.
