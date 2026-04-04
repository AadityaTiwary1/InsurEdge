# InsurEdge 
### AI-Powered Parametric Micro-Insurance for Gig Workers

> Protecting delivery riders from income loss caused by disruptions they never saw coming — and never caused.

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://python.org)
[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?logo=fastapi)](https://fastapi.tiangolo.com)
[![Flutter](https://img.shields.io/badge/Frontend-Flutter-02569B?logo=flutter)](https://flutter.dev)
[![Supabase](https://img.shields.io/badge/Database-Supabase-3ECF8E?logo=supabase)](https://supabase.com)
[![CatBoost](https://img.shields.io/badge/ML-CatBoost-yellow)](https://catboost.ai)
[![XGBoost](https://img.shields.io/badge/ML-XGBoost-orange)](https://xgboost.readthedocs.io)

---

## Table of Contents

1. [Overview](#1-overview)
2. [Problem Statement](#2-problem-statement)
3. [Why Parametric Insurance](#3-why-parametric-insurance)
4. [How InsurEdge Works — End to End](#4-how-insuredge-works--end-to-end)
5. [AI Models](#5-ai-models)
   - [Risk Score Model](#51-risk-score-model)
   - [Trust Score Model](#52-trust-score-model)
   - [Dynamic Premium Model (Planned)](#53-dynamic-premium-model-planned)
   - [How the Models Work Together](#54-how-the-models-work-together)
6. [Disruption Factor Coverage](#6-disruption-factor-coverage)
7. [Parametric Trigger System](#7-parametric-trigger-system)
8. [Fraud & Market Crash Defense](#8-fraud--market-crash-defense)
9. [Claim Validation & Payout Logic](#9-claim-validation--payout-logic)
10. [System Architecture](#10-system-architecture)
11. [Tech Stack](#11-tech-stack)
12. [Datasets](#12-datasets)
13. [Challenges & Honest Limitations](#13-challenges--honest-limitations)
14. [Future Scope](#15-future-scope)

---

## 1. Overview

**InsurEdge** is an AI-powered parametric micro-insurance platform built specifically for gig economy delivery workers in India. It monitors real-world disruption conditions in near real-time, predicts how risky a rider's working environment is, evaluates each rider's behavioral trustworthiness from their insurance history, calculates a fair personalized weekly premium, and when a genuine disruption strikes processes compensation automatically without requiring the rider to file a single document.

The core philosophy behind InsurEdge is simple: gig workers are not traditional employees. They have no HR department, no paid leave, no sick days, and no employer-backed insurance. When a city floods, when a riot breaks out, when the AQI hits a hazardous level — they lose income silently. Traditional insurance is too slow, too paperwork-heavy, and too expensive to serve workers earning ₹400–₹800 a day. InsurEdge is built from the ground up to fix this.

The platform targets riders working on **Swiggy, Zomato, Blinkit, and Zepto** — delivery networks where income is directly tied to daily hours and order volume. A single disrupted week can mean a rider cannot pay rent or cover household expenses. InsurEdge treats that disruption as an insurable, measurable, and automatically compensable event.

| Field | Details |
|---|---|
| Project Type | AI + FinTech + InsurTech |
| Insurance Model | Weekly parametric micro-insurance |
| Claim Mechanism | Fully automated — no manual filing |
| Core AI Systems | Risk Score Model · Trust Score Model · Dynamic Premium Model · Fraud Detection |
| Primary Users | Gig delivery workers in urban India |
| Target Platforms | Swiggy · Zomato · Blinkit · Zepto |

---

## 2. Problem Statement

India's gig economy employs over 7.7 million workers, with delivery being the largest segment. These workers operate entirely on a "no delivery, no pay" model. Their daily earnings are acutely sensitive to conditions outside their control and those conditions are becoming more severe, more frequent, and more diverse with each passing year.

Consider a typical disruption week. Heavy pre-monsoon rainfall hits Mumbai. Restaurants reduce kitchen hours. Customers cancel orders. Traffic snarls make delivery windows impossible to meet. A rider who normally earns ₹700 a day earns ₹200. This continues for five days. At the end of the week, the rider has lost roughly ₹2,500 and received nothing from anyone. No insurance. No platform support. No government aid. Nothing.

Now extend this problem beyond weather. Curfews are imposed due to communal tensions. A major road collapses and cuts off a delivery zone for three days. A power grid failure shuts down restaurant POS systems across an area. A military operation near a border district locks down an entire city. In every one of these cases, the rider suffers, and the current system offers zero recourse.

| Problem | Impact on the Rider | Gap in Current Systems |
|---|---|---|
| Heavy rainfall / flooding | Reduced mobility, fewer orders, unsafe roads | No compensation mechanism |
| Extreme AQI / heat | Unsafe working conditions, occupational health risk | No income protection |
| Traffic congestion events | Lower delivery efficiency, longer idle time | No dynamic support |
| Civil unrest / curfews | Zone-wide inactivity, platform slowdowns | No parametric coverage |
| War / military operations | Lockdowns, road closures, zone inaccessibility | No coverage exists at all |
| Infrastructure failures | Power outages, road collapses, bridge closures | Not considered by any insurer |
| Epidemic containment zones | Delivery restrictions, low order density | No insurance product covers this |
| Manual claim processes | Riders lack time and literacy for complex claims | No simplified option |
| Fraud in payout systems | Erodes platform financial sustainability | No lightweight anti-fraud layer |

InsurEdge directly addresses all of these gaps through a combination of AI prediction, real-time trigger monitoring, behavioral trust evaluation, and automated payout logic.

---

## 3. Why Parametric Insurance

To understand InsurEdge, it helps to understand what parametric insurance actually is and why it is the right model for gig workers.

Traditional insurance works on an indemnity basis: something bad happens, you file a claim, an adjuster investigates, a decision is made, and eventually weeks or months later you may receive a payout. For a gig worker earning a few hundred rupees a day, this process is entirely **unworkable.** They cannot afford to wait. They cannot afford legal help if a claim is denied. They often lack the documentation to prove what they lost.

**Parametric insurance** works differently. Instead of compensating for a proven loss, it pays out when a predefined, measurable real-world condition is met. If rainfall in a zone exceeds X mm/hr for Y hours, a payout triggers. The rider does not need to prove anything. The real-world data proves it automatically.

This model is already proven in agriculture (crop failure), aviation (flight delays), and catastrophe bonds. InsurEdge adapts it to the micro-scale of urban gig work — with one critical addition: because automatic payouts create fraud risk, InsurEdge layers AI-based trust and fraud evaluation on top of the trigger system to ensure that speed does not come at the cost of integrity.

| Dimension | Traditional Insurance | Parametric Insurance (InsurEdge) |
|---|---|---|
| Claim Initiation | Rider files manually | System detects and triggers automatically |
| Verification Method | Human adjuster + documents | External data APIs + ML validation |
| Payout Speed | Weeks to months | Hours to days |
| Complexity for Rider | High — forms, evidence, follow-ups | Zero — fully passive |
| Fraud Risk | Moderate | Higher — mitigated by trust + fraud layer |
| Suitability for Gig Workers | Low | High |

---

## 4. How InsurEdge Works (End to End)

InsurEdge runs every rider through a continuous intelligence pipeline. Here is what happens from the moment a rider signs up to the moment a payout is processed:

<p align="center">
  <img src="imgs/Workflow.png" width="750"/>
</p>

Every stage in this pipeline is observable and explainable. Riders can see their risk score, trust score, and the reason a claim was held or approved making InsurEdge transparent by design, not just by intention.

This helps the gig workers understand why their scores have been high/low and work accordingly.

---

## 5. AI Models

InsurEdge's intelligence is distributed across three AI models, each solving a distinct part of the insurance problem. The first two are fully implemented; the third is the next stage of development.

---

### 5.1 Risk Score Model

**What it solves:** A core question that has to be answered before any premium can be set is — *how exposed is this rider to income disruption based on where and when they work?* The Risk Score Model answers that question quantitatively on a 0–100 scale.

**Why we built it this way:** Rather than applying a fixed city-level risk category (e.g., "Mumbai = High Risk"), InsurEdge computes a granular score based on actual road, weather, and traffic conditions relevant to the rider's zone. This makes pricing and trigger sensitivity far more accurate than any rule-based approach, and it means that two riders in the same city but different zones can have meaningfully different risk profiles — which they should.

**Dataset Used:** [Indian Road Accident Dataset 2022–2025](https://www.kaggle.com/datasets/sehaj1104/indian-road-accident-dataset-20222025) — a Kaggle dataset covering road accidents across Indian cities with attributes including weather conditions at time of accident, traffic density, visibility levels, and accident severity. This dataset was chosen because road accidents are a strong proxy for dangerous working conditions for delivery riders: they happen more during rain, in congested zones, and under low visibility — the same conditions that disrupt gig delivery work.

**How the Risk Score is constructed:** Since the dataset does not contain a pre-labeled "risk score" column, we engineer the target variable as a weighted composite:

```python
Generated_Risk_Score = 50  # base score
    + traffic_density_encoded × 5
    + weather_encoded         × 4
    + visibility              × (-0.2)   # higher visibility = lower risk
    + accident_severity_encoded × 8
```

The score is clipped to [0, 100]. The weighting reflects domain logic: accident severity and weather severity are the most powerful risk contributors for delivery riders, while better visibility actively reduces risk. This engineered target is then used to train the regression models — we are essentially teaching the models to predict "how dangerous would working here be today?" given real road and weather inputs.

**Model Selection:** Three regressors are trained and benchmarked, and the best model by R² score is automatically selected for deployment. This competitive approach avoids committing to a single algorithm and lets the data decide which model generalizes best to new zones.

| Model | Why It Was Included |
|---|---|
| Random Forest Regressor | Ensemble of decision trees; robust to noisy features and non-linear relationships |
| XGBoost Regressor | Gradient boosting; consistently excellent on structured tabular data |
| CatBoost Regressor | Handles categorical features natively without manual encoding; often best on mixed data |

After training, feature importances are extracted from the winning model. This is used not just for model diagnostics but for explainability — when a rider sees a "High Risk" label on their dashboard, the system can tell them *which* conditions in their zone are driving that score.

**Risk Score Output Labels:**

| Score Range | Risk Category | Meaning for InsurEdge |
|---|---|---|
| 0 – 20 | Very Low Risk | Minimal disruption probability; lower premium band |
| 21 – 40 | Low Risk | Occasional disruption; standard low premium |
| 41 – 60 | Moderate Risk | Regular disruption exposure; mid-range premium |
| 61 – 80 | High Risk | Frequent disruptions; higher premium, tighter monitoring |
| 81 – 100 | Severe Risk | Highly volatile zone; maximum premium, heightened trigger sensitivity |

The risk score feeds directly into premium calculation and trigger sensitivity tuning. In a Severe Risk zone, the system may activate a payout at a lower rainfall threshold than in a Low Risk zone, because the baseline conditions are already more dangerous and the marginal disruption from additional rain is higher.

---

### 5.2 Trust Score Model

**What it solves:** Even in a parametric system, not all riders should be treated identically. Some riders have long, consistent insurance histories with no anomalies. Others show patterns associated with fraud — excessive claim frequency, suspicious timing, or inconsistent behavior. The Trust Score Model quantifies this behavioral reliability on a 0–100 scale, giving the system a second evaluation axis independent of zone risk.

**Why this matters:** A purely trigger-based system without trust evaluation is financially fragile. Anyone could activate a payout by being in the right place when a rain threshold is crossed. The Trust Score adds a behavioral verification dimension: even if the trigger is real, a rider with a very low trust score receives additional scrutiny before their payout is processed. Conversely, a high-trust rider benefits from faster approvals and stable pricing and a reward for consistent, genuine behavior.

**Dataset Used:** [Car Insurance Claim Prediction](https://www.kaggle.com/datasets/ifteshanajnin/carinsuranceclaimprediction-classification) — a Kaggle classification dataset containing insurance policyholder attributes and whether they made a claim. While this is car insurance rather than gig insurance, the behavioral signals it captures — policyholder profile, subscription patterns, vehicle attributes, historical claim behavior that closely mirrorers what InsurEdge needs to evaluate rider insurance behavior. Claim-making behavior is consistent across insurance domains: the features that predict a likely car insurance claimant are meaningfully correlated with the features that predict an insurance risk in gig platforms. This is an appropriate proxy given the absence of a real gig-insurance dataset of comparable scale.

**Model Architecture:** A **CatBoostClassifier** is trained to predict the binary outcome of whether a policyholder made a claim or not. CatBoost is particularly well-suited here because the dataset contains a mix of numerical and categorical features, and CatBoost handles categorical encoding internally without requiring manual preprocessing. The model is wrapped in a full `sklearn` Pipeline with `StandardScaler` for numerical features and `OneHotEncoder` for categorical features, making the entire preprocessing and inference chain deployable as a single serialized object.

**Trust Score Derivation:** Once the classifier is trained, we do not use the binary prediction directly — a hard yes/no on "will this rider commit fraud" would be both too blunt and too easily gamed. Instead, we use the model's **predicted claim probability** and invert it to produce a continuous trust signal:

```python
Trust_Score = round((1 - Claim_Probability) * 100, 2)
```

This means a rider the model believes has only a 10% chance of making a suspicious claim gets a Trust Score of 90 — very reliable. A rider with a 75% predicted claim probability gets a Trust Score of 25 — high scrutiny required. The continuous score is far more useful than a binary flag because it allows fine-grained premium adjustment and tiered claim processing rather than a hard approve/reject gate.

**Trust Score Output and Downstream Effects:**

| Trust Score | Label | Premium Band | Claim Handling |
|---|---|---|---|
| 80 – 100 | High Trust | Low Premium | Fast-tracked; auto-approved if trigger valid |
| 60 – 79 | Medium Trust | Standard Premium | Standard processing pipeline |
| 0 – 59 | Low Trust | High Premium | Additional verification step required |

**Why trust feeds into premium:** A rider who is statistically more likely to generate problematic claims is more expensive to serve from an actuarial standpoint. Rather than refusing to insure them, InsurEdge prices this risk fairly — low-trust riders pay slightly more, but they still have access to coverage. This is more equitable than blanket exclusions and more sustainable than ignoring behavioral risk entirely.

---

### 5.3 Dynamic Premium Model *(Planned)*

**What it will solve:** The current premium system assigns riders to one of three bands (Low / Standard / High) based on their Trust Score. This works as an MVP but is coarse. Two riders can have the same Trust Score but wildly different risk environments — a High Trust rider working 70 hours a week in a flood-prone zone should not pay the same premium as a High Trust rider working 30 hours in a stable zone. The Dynamic Premium Model replaces the band system with a continuous regression output — a precise weekly rupee figure calculated from the full combination of risk, trust, exposure, and zone characteristics.

**Why this upgrade matters:** Dynamic pricing is what makes InsurEdge financially sustainable at scale. If high-risk zones are underpriced, the claim pool runs dry during heavy monsoon months. If low-risk zones are overpriced, riders churn off the platform. Getting pricing right at the individual level and not just at a coarse category level that is what allows InsurEdge to operate profitably while remaining affordable for every rider.

**Planned Input Features:**

| Feature | Role in Premium Calculation |
|---|---|
| Risk Score (0–100) | Primary actuarial driver; directly correlates with expected claim frequency |
| Trust Score (0–100) | Behavioral modifier; lowers premium for reliable riders |
| Weekly Working Hours | Exposure duration — more hours = more risk surface = higher actuarial exposure |
| Zone Type | Urban density multiplier; dense zones have higher traffic and more disruption events |
| Historical Disruption Rate | Zone-level claim frequency over past months; captures seasonal patterns |
| Weather Volatility Index | Seasonal risk score for the city; differentiates stable vs. monsoon-volatile cities |

**Planned Output:** A weekly premium in the ₹20–₹65 range, calibrated so that expected payouts per zone are covered by collected premiums with a sustainable operational margin. The model will be trained on synthetic data initially, with a transition to real policyholder data as the platform scales.

---

### 5.4 How the Models Work Together

The three models are not independent modules but they form a pipeline where each model's output informs the next, and where the combination produces decisions that are better than any single model could achieve alone.

```
Environmental & Road Accident Data
              │
              ▼
    ┌─────────────────┐
    │  Risk Score     │  "How dangerous is this rider's zone?"
    │     Model       │  Output: 0–100 Risk Score + Category
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │  Trust Score    │  "How reliable is this rider's behavior?"
    │     Model       │  Output: 0–100 Trust Score + Premium Band
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │  Premium        │  "What should this rider pay this week?"
    │  Calculation    │  Output: ₹XX/week
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │  Trigger +      │  "Is this claim genuine and eligible?"
    │  Fraud Engine   │  Output: Approve / Hold / Reject
    └─────────────────┘
```
<p align="center">
  <img src="imgs/Models_Workflow.png" width="750"/>
</p>

A rider in a Severe Risk zone with a High Trust Score pays more than a Low Risk zone rider, but gets faster claim approvals. A rider with a Low Trust Score in a Low Risk zone still gets coverage, but at a higher premium and with additional claim scrutiny. The combination produces outcomes that are simultaneously fairer to individuals, more resistant to fraud, and more financially sustainable for the platform than any single-axis approach.

---

## 6. Disruption Factor Coverage

One of InsurEdge's most deliberate design decisions is treating disruption as a **broad category**, not just a weather event. Delivery workers lose income due to an enormous range of conditions — environmental, social, political, infrastructural, and even military. The platform is built to expand its trigger coverage as reliable, verifiable data sources become available for each new category.

### Currently Monitored

These triggers are active in the current system. Before any payout is initiated, conditions are verified against real-time external APIs which are not just checked once but confirmed to have persisted above threshold for a minimum duration window.

| Factor | Data Source | Trigger Condition | Why It Matters for Riders |
|---|---|---|---|
| Rainfall | OpenWeatherMap API | Exceeds threshold mm/hr, sustained | Heavy rain sharply reduces mobility, order availability, and safe riding |
| Flooding | Flood alert / NDMA APIs | Zone flood alert active | Flooded roads make delivery physically impossible |
| AQI (Air Quality) | AQI APIs | Hazardous category activated | Riding in hazardous AQI is a documented occupational health risk |
| Extreme Heat | Weather API | Temperature > 42°C | Heat stress limits safe working hours significantly; fatigue increases risk |
| Traffic Congestion | Google Maps / Traffic APIs | Severe congestion flag sustained | Cuts deliveries completable per hour; directly reduces income |
| Delivery Zone Shutdown | Platform data (mock) | Zone inactivity detected | No orders flowing means no income regardless of rider effort |

### Planned Expansions

Each category below requires a reliable, verifiable real-time data source before being added as a live trigger. InsurEdge will not add a trigger without external verification capability and by doing so it would make the system trivially exploitable by anyone who knows the trigger conditions.

| Factor | Category | How It Affects Riders | Implementation Plan |
|---|---|---|---|
| **War / Military Operations** | Conflict & Security | Active military operations near a city create mandatory curfews, road closures, and platform shutdowns that affect entire districts instantly. Riders in these zones face complete income loss with no warning and no recourse under any existing product. | Integrate Ministry of Home Affairs / NDMA conflict alert feeds. Trigger activates for riders with verified registered zone within a defined radius of the declared conflict area. News API cross-check required to confirm before payout release — prevents exploitation by riders outside the genuine impact zone. |
| **Riots & Civil Unrest** | Conflict & Security | Communal violence, political protests, or public order breakdowns force platform-level delivery pauses and make road travel genuinely dangerous. These events are often hyperlocal — two kilometers can be the difference between a normal day and a complete shutdown. | News sentiment APIs + police advisory feeds combined with cluster detection. If a verified unrest event exists and many riders in the same zone claim simultaneously with consistent location data, the trigger validates. Isolated claims without external corroboration are held. |
| **Terrorist Incidents** | Security | Blast or attack events trigger city-wide security operations, emergency road closures, and public fear that collapses order volumes for 24–72 hours even in areas far from the incident. | National security alert APIs + geographic radius trigger around verified incident zone. Radius is kept tight to prevent exploitation by riders whose areas were not materially affected. |
| **Strikes & Bandhs** | Operational | Trade union strikes and politically declared bandhs shut down restaurants, shops, and transport simultaneously. Platform order volumes drop to near zero, but riders have no income protection despite not being at fault. | Government public notice feeds + verified trade union announcements. A manual whitelist approach is used for confirmed bandh events with official governmental or judicial notification — this prevents fake "bandh" claims without an official declaration. |
| **Border Conflicts (Local)** | Security | Riders operating in border districts — particularly in states like Jammu & Kashmir, Manipur, or Arunachal Pradesh — can face sudden lockdowns due to cross-border security incidents affecting civilian mobility for extended periods. | Ministry of Home Affairs district-level alert APIs. Trigger only activates for riders with a verified registered zone within the declared affected district — not the entire state. |
| **Power Grid Failures** | Infrastructure | Extended power outages shut down restaurant POS systems, cloud kitchen equipment, and the order management apps that platform delivery depends on. Riders cannot receive or complete orders even if roads are clear and weather is fine. | State electricity board outage notification APIs. Trigger requires a verified outage duration exceeding a minimum threshold affecting a minimum percentage of the zone's grid coverage — short localized outages do not qualify. |
| **Infrastructure Collapse** | Infrastructure | Bridge collapses, road washouts, and highway closures can cut off entire delivery zones for days or weeks, making previously serviceable areas physically unreachable regardless of rider effort or willingness. | National Highways Authority of India (NHAI) + state road authority APIs. Zone-level reachability scoring used to determine what fraction of a rider's typical route network is blocked before the trigger activates. |
| **Epidemic / Disease Outbreak** | Health | Containment zones declared during disease outbreaks restrict movement and shut delivery operations in affected areas, sometimes for extended periods. The COVID-19 period demonstrated how rapidly this can eliminate gig worker income with zero notice. | Health Ministry / ICMR alert feeds + state government containment zone notifications. Geo-fenced trigger based on the declared containment perimeter boundary, cross-referenced with the rider's active working zone. |
| **Earthquake / Natural Disaster** | Disaster | Seismic events and their aftershocks can make roads unsafe, damage infrastructure, and trigger evacuation orders that halt all delivery activity. Even a moderate earthquake can close dozens of roads in an urban area simultaneously. | IMD + NDMA disaster alert APIs. Trigger activates only for Richter magnitude ≥ defined threshold within a defined radius of the rider's zone — minor seismic events below the disruption threshold do not qualify. |
| **Political Rallies / VIP Movement** | Operational | Major political events and VIP convoy movement trigger temporary road closures that can lock down significant portions of an urban delivery network for 4–8 hours, making deliveries in entire city sectors impossible during peak hours. | Traffic authority route notifications + government protocol advisories. Trigger requires closure duration exceeding a minimum threshold and affecting more than a defined percentage of the zone's active delivery routes — brief closures do not qualify. |

> **Implementation Principle:** For every new trigger category, three requirements must be satisfied before it goes live: (1) a reliable, machine-readable, real-time data source must be available, (2) a defensible and tested numerical threshold must be established, and (3) an external reality verification step must be built in to prevent gaming. Categories above are listed in approximate implementation priority order.

---

## 7. Parametric Trigger System

The trigger system is the operational core of InsurEdge — it is what converts a real-world event into a validated insurance activation. A trigger is not simply a threshold crossed on a single API call. InsurEdge applies a multi-condition validation stack before a trigger is considered confirmed, because single-signal triggers are trivially exploitable.

### Trigger Validation Steps

1. **Threshold Condition:** The raw API reading must exceed the predefined threshold for the trigger type (e.g., rainfall > X mm/hr).
2. **Duration Condition:** The condition must persist for a minimum time window, preventing false positives from short spikes or temporary API anomalies.
3. **Zone Match:** The rider's registered working zone must overlap with the area where the condition is active — a flood in a different part of the city does not trigger a payout for an unaffected rider.
4. **Cross-Source Verification:** Where possible, the condition is validated against at least two independent data sources to reduce the risk of API error or data manipulation.

Only when all four conditions are satisfied does the trigger advance to the fraud and trust validation stage.

### Trigger Decision Matrix

| Trigger Valid? | Trust Score | Fraud Signals | Decision |
|---|---|---|---|
| Yes | High (≥80) | None | Auto-approve payout |
| Yes | Medium (60–79) | None | Standard review pipeline |
| Yes | Any | Cluster anomaly detected | Hold — initiate investigation |
| Yes | Low (<60) | None | Manual verification required |
| Yes | Any | Location mismatch detected | Hold — flag for review |
| No | Any | Any | Reject — trigger not verified |
| Partial | High | None | Delayed — await full verification |

---

## 8. Fraud & Market Crash Defense

The biggest systemic vulnerability in any parametric insurance product is coordinated fraud. Because payouts are triggered by real-world conditions rather than individual loss evidence, a fraud ring could theoretically exploit a genuine weather event to generate mass illegitimate claims. InsurEdge's defense architecture is built around this threat model from the beginning, treating fraud resistance as a first-class design requirement rather than an afterthought.

### Threat Categories

**Individual Fraud** is the most common vector — a single rider attempts to fake their location, manipulate their activity data, or claim during a trigger event they were not genuinely affected by. This is addressed through location consistency checks and behavioral anomaly scoring.

**Coordinated Ring Fraud** is the parametric-specific threat — a group of riders or bot accounts simultaneously file claims during a real trigger event, exploiting the automated payout system to drain the claim pool. This is the "market crash" scenario and is addressed through cluster detection and trust score gating.

**API Spoofing** is an advanced threat where attackers attempt to inject fake readings into external data feeds to artificially create trigger conditions. This is addressed through cross-source verification and anomaly detection on the API data itself.

### Defense Layer Stack

| Defense Layer | What It Checks | How It Works |
|---|---|---|
| Location Consistency | Is the rider actually in the zone they claim? | Current GPS is cross-referenced against historical movement patterns and the registered zone. Large deviations flag the claim. |
| Activity Consistency | Does this rider's behavior match their typical patterns? | Sudden activity changes during trigger periods — e.g., a rider who never works on rainy days suddenly claiming rain disruption — are anomalous and flagged. |
| Behavioral Anomaly Detection | Is this rider statistically unusual relative to their own history and the rider cohort? | ML-based anomaly scoring compares current behavior to the rider's personal baseline and the broader distribution of similar riders. |
| Cluster Detection | Are many suspicious claims happening simultaneously from the same zone? | If claim volume from a zone spikes beyond a statistical threshold relative to historical norms during a trigger event, a cluster fraud flag is raised for all affected claims. |
| Trust Score Gate | Does the rider's behavioral history support this claim? | Low Trust Score riders face additional verification steps even when the trigger itself is valid and genuine. |
| External Reality Verification | Did the disruption actually happen where the rider claims? | All triggers are verified against authoritative external APIs. No self-reported disruption claims are accepted without independent confirmation. |
| Cross-Source Validation | Do multiple data sources agree on the trigger condition? | Wherever possible, conditions are confirmed by at least two independent sources before a trigger is considered validated. |

### Market Crash Response Flow

When InsurEdge detects a potential coordinated fraud event, it does not shut down payouts entirely — which would harm genuine riders who deserve compensation. Instead, it applies a tiered response that separates genuine riders from suspicious actors:

<p align="center">
  <img src="imgs/Market_Crash.png" width="750"/>
</p>

This design ensures that even during a coordinated attack, genuine riders in genuinely disrupted zones receive their payouts — with a slight delay during the review process. The system is designed to protect legitimate users first, and protect itself second.

---

## 9. Claim Validation & Payout Logic

Once a trigger has been verified and fraud checks have passed, InsurEdge calculates the payout amount. The payout is not a flat fixed figure — it is calibrated to the severity of the disruption, the duration of the event, and the rider's typical exposure profile.

**Payout Calculation Factors:**
- **Trigger severity:** How far above the threshold did the disruption condition peak? A zone with 80mm of rainfall gets a larger payout than one that barely crossed the trigger threshold.
- **Duration:** How long did the trigger condition persist? A 12-hour flooding event causes more income disruption than a 2-hour one.
- **Rider exposure:** The rider's registered average working hours determine how much income was at risk during the disruption window.
- **Zone income disruption factor:** Each trigger type has a calibrated income disruption multiplier per zone type, based on historical data on how much that trigger typically suppresses order volume.
- **Payout cap:** The payout cannot exceed a defined multiple of the weekly premium, preventing over-insurance while still providing meaningful compensation.

**Payout Timeline:**

| Claim Status | Expected Timeline |
|---|---|
| Auto-approved (High Trust, clean signals) | Within 24 hours of trigger end |
| Standard review | 48–72 hours |
| Held for investigation | 5–7 business days |
| Rejected | Notification within 24 hours with reason |

All payout decisions come with an explanation accessible in the rider's dashboard — what triggered the payout, what checks were run, why the amount is what it is, or why a claim was held. Transparency is non-negotiable.

---

## 10. System Architecture

InsurEdge is built as a layered system where each layer has a clearly defined responsibility. This design makes the platform easier to scale, maintain, and audit independently.

```
┌─────────────────────────────────────────────────────────────┐
│                        FRONTEND LAYER                       │
│               Flutter Web / Android Application             │
│  Dashboard · Premium View · Risk Status · Payout History    │
└──────────────────────────┬──────────────────────────────────┘
                           │  REST API calls
┌──────────────────────────▼──────────────────────────────────┐
│                        BACKEND LAYER                        │
│                    FastAPI (Python)                         │
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │ Risk Score  │  │ Trust Score │  │   Premium Engine    │  │
│  │   Service   │  │   Service   │  │      Service        │  │
│  └─────────────┘  └─────────────┘  └─────────────────────┘  │
│                                                             │
│  ┌─────────────────────────────────────────────────────┐    │
│  │         Trigger Monitoring + Fraud Detection        │    │
│  └─────────────────────────────────────────────────────┘    │
│                                                             │
│  ┌─────────────────────────────────────────────────────┐    │
│  │              Payout Calculation Engine              │    │
│  └─────────────────────────────────────────────────────┘    │
└───────────┬──────────────────────────┬──────────────────────┘
            │                          │
┌───────────▼──────────┐  ┌────────────▼────────────────────┐
│    DATA LAYER        │  │      EXTERNAL DATA LAYER        │
│  Supabase /          │  │  Weather · AQI · Traffic APIs   │
│  PostgreSQL          │  │  NDMA · Alert Feeds (planned)   │
│  Rider Profiles      │  │  Government Notification APIs   │
│  Claim History       │  │  (planned)                      │
│  Model Outputs       │  └─────────────────────────────────┘
└──────────────────────┘
```
<p align="center">
  <img src="imgs/System_Architecture.png" width="750"/>
</p>

**Frontend:** Flutter is used to deliver a consistent experience across web and Android from a single codebase. The UI is deliberately simple the riders should be able to understand their risk score, trust score, and weekly premium in under 30 seconds of use. All complexity is in the backend; none of it is pushed onto the rider.

**Backend:** FastAPI is chosen for its Python-native ecosystem (matching the ML stack perfectly), its automatic OpenAPI documentation, and its async capabilities which are critical for polling multiple external APIs simultaneously during trigger monitoring. Each AI model runs as a separate service behind the FastAPI router, so models can be retrained and redeployed independently without touching the rest of the system.

**Database:** Supabase provides a managed PostgreSQL instance with built-in authentication, row-level security, and real-time subscriptions. Rider profiles, claim histories, model inference outputs, and payout records are all stored here. Row-level security ensures each rider can only access their own data — a non-negotiable requirement for a financial product.

**External APIs:** The trigger monitoring system polls multiple external data sources on a configurable interval. Responses are cached to avoid hitting rate limits during high-volume trigger events, and a fallback source hierarchy is defined for each trigger type to ensure the system degrades gracefully rather than silently failing.

---

## 11. Tech Stack

| Layer | Technology | Why This Choice |
|---|---|---|
| Frontend | Flutter | Single codebase for web + Android; fast iteration; strong UI component library |
| Backend | FastAPI (Python) | Native Python ML integration; async support; auto-generated API docs |
| Database | Supabase / PostgreSQL | Managed Postgres with built-in auth, RLS, and real-time subscriptions |
| ML Development | Python, Google Colab | Rapid experimentation; GPU availability for model training |
| ML Models | CatBoost, XGBoost, Random Forest | Best-in-class on structured tabular data; handles mixed feature types well |
| ML Libraries | Pandas, NumPy, Scikit-learn, Joblib | Standard ML ecosystem; reliable model serialization via Joblib |
| Visualization | Matplotlib, Seaborn | Training diagnostics, feature importance plots, and model performance charts |
| Model Serving | Joblib `.pkl` via FastAPI | Lightweight inference without a separate model server at MVP scale |
| Deployment | Vercel (frontend) + Cloud backend | Easy CI/CD for frontend; scalable serverless-compatible backend |
| External APIs | OpenWeatherMap, AQI APIs, Google Maps | Reliable, well-documented, developer-friendly at MVP pricing |
| Payments (Mock) | Razorpay Sandbox | Real payment gateway UX for demos without live transaction risk |

---

## 12. Datasets

InsurEdge deliberately uses separate datasets for different models rather than forcing one dataset to serve all purposes. Each model learns from the most relevant signals for its specific question, rather than compromising on a shared dataset that fits no question perfectly.

| Model | Dataset | Source | Why This Dataset |
|---|---|---|---|
| Risk Score | Indian Road Accident Dataset 2022–2025 | [Kaggle](https://www.kaggle.com/datasets/sehaj1104/indian-road-accident-dataset-20222025) | Road accidents are a direct proxy for dangerous working conditions — driven by the same weather, traffic, and visibility factors that disrupt gig delivery |
| Trust Score | Car Insurance Claim Prediction | [Kaggle](https://www.kaggle.com/datasets/ifteshanajnin/carinsuranceclaimprediction-classification) | Claim-making behavioral signals transfer across insurance domains; the features predicting a car insurance claimant correlate meaningfully with gig insurance behavioral risk |
| Dynamic Premium | Synthetic + domain-derived | Internal generation | No public dataset exists for gig worker insurance pricing in India; synthetic generation based on actuarial principles is the appropriate approach |
| Fraud Detection | Synthetic anomaly / behavioral signals | Internal generation | Labeled fraud datasets are rare and domain-specific; synthetic data with known fraud patterns allows controlled and reproducible model development |

As InsurEdge scales and accumulates real policyholder data, the proxy and synthetic datasets will be progressively replaced with real anonymized data, improving all model accuracies over time.

---

## 13. Challenges & Honest Limitations

A strong project acknowledges what it cannot do yet rather than hiding gaps under aspirational language.

| Challenge | Why It Exists | Current Mitigation |
|---|---|---|
| No real gig-insurance dataset | Gig worker parametric insurance is nascent in India; no large labeled dataset exists publicly | Using proxy datasets and synthetic generation; plan to transition to real data at scale |
| Cold-start trust problem | New riders have no insurance history to evaluate trust from | New riders receive a neutral mid-range trust score and build history over time; cold-start premium is set conservatively |
| Trigger threshold calibration | Setting the right threshold (how much rain = payout?) requires actuarial validation against real claim data | Initial thresholds set based on domain research and rider income impact studies; will be refined with real actuarial input |
| API dependency | All trigger verification depends on external APIs that can go down or return stale data | Response caching, fallback source hierarchy, and graceful degradation modes built into the monitoring layer |
| False positives in fraud detection | Overly aggressive fraud detection can deny genuine claims, harming the riders the platform exists to protect | Precision/recall trade-off is tuned at launch to minimize false denials; thresholds are tightened as real fraud data accumulates |
| Regulatory landscape | Parametric micro-insurance for gig workers is a new product category with evolving IRDAI regulations | Built with regulatory compliance as a planned phase; sandbox-style operation initially; consulting InsurTech regulatory advisors |
| Premium sustainability | Without real actuarial data, premium levels are estimates — over or under-pricing both create problems | Conservative initial pricing with a planned actuarial review cycle every quarter |

---

## 15. Future Scope

InsurEdge in its current form is an AI-backed MVP with two fully functional models and a clearly defined product architecture. The path from here to a full InsurTech platform involves three parallel expansion tracks.

### Track 1: Broader Trigger Coverage

The most impactful near-term expansions are war/conflict triggers and infrastructure failure triggers — these represent the largest categories of disruption currently uncovered by *any* insurance product for gig workers anywhere. Implementing these requires establishing reliable data partnerships with government alert systems, which will be pursued in parallel with IRDAI regulatory engagement.

### Track 2: Smarter Models

| Improvement | Description |
|---|---|
| Premium Regression Model | Replace the three-band system with a continuous ML regression model trained on synthetic + real data for precise ₹/week output |
| Fraud Ring Detection | Graph-based anomaly detection to identify coordinated fraud across connected rider networks |
| Real-time Trust Updates | Trust Score recalculation after every claim event rather than only at enrollment |
| Explainability Layer | SHAP-based explanations for every risk and trust score decision, surfaced directly in the rider's dashboard |
| Adaptive Threshold Learning | Trigger thresholds that self-calibrate over time based on observed claim accuracy and zone-level disruption history |
| Seasonal Risk Adjustment | Risk Scores that shift automatically based on monsoon, winter, or summer patterns for each city |

### Track 3: Platform & UX Expansion

| Feature | Description |
|---|---|
| Multi-City Risk Heatmaps | Zone-level disruption visualization for city operations dashboards, showing where payouts are concentrating |
| Instant UPI Payouts | Direct wallet disbursement within hours of payout approval, replacing the current batch processing approach |
| Platform API Integrations | Direct data feeds from Swiggy / Zomato / Blinkit to verify active rider status and order volume during trigger events |
| Worker Category Expansion | Extend coverage to cab drivers, logistics couriers, e-commerce last-mile workers, and healthcare field workers |
| Multilingual Rider App | Hindi and regional language support for non-English-speaking riders across Tier 2 and Tier 3 cities |
| Policy Personalization | Riders choose coverage tiers and specific trigger categories they want insured, enabling opt-in modular coverage |

---

> **InsurEdge** — Because gig workers deserve protection from the risks they didn't choose and cannot control.

---

