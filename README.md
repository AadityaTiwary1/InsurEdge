# MARKET CRASH DISCUSSED AT END.

# InsurEdge – AI Powered Parametric Insurance for Gig Workers

## Overview

InsurEdge is an AI-enabled parametric insurance platform designed to protect gig economy delivery workers from income loss caused by external disruptions such as extreme weather, pollution, or local restrictions.

Delivery partners rely heavily on daily working hours to earn income, and unexpected environmental or social disruptions can significantly reduce their weekly earnings. InsurEdge provides automated insurance coverage that detects disruptions using real-world data and triggers payouts automatically.

Unlike traditional insurance systems that require manual claim submission and verification, InsurEdge follows a parametric model where predefined triggers activate compensation automatically.

The system focuses strictly on income protection and excludes coverage for health, life, accidents, or vehicle repairs.

---

## Problem Statement

Gig workers such as food delivery riders depend on consistent working hours to maintain their weekly income. However, disruptions like heavy rainfall, flooding, extreme heat, severe pollution, or local restrictions can reduce their ability to work, causing significant income loss.

Currently, gig workers have no protection against these uncontrollable events, leaving them financially vulnerable. InsurEdge aims to address this gap by creating an automated parametric insurance system that provides financial protection when such disruptions occur.

---

## Target Persona

### Food Delivery Riders

Platforms:

* Swiggy
* Zomato
* Blinkit
* Zepto

### Characteristics

* Income depends on number of deliveries completed
* Works outdoors for long hours
* Highly impacted by environmental disruptions
* Primarily uses smartphones for work
* Prefers simple and fast mobile interfaces

### Example Scenario

Rahul is a delivery rider working with Swiggy in Mumbai. On a particular day, heavy rainfall floods roads and restaurants close early. As a result, Rahul loses several hours of work and earns significantly less that week.

With InsurEdge, the system automatically detects heavy rainfall in Rahul's delivery zone, verifies the disruption, and calculates the income loss. The compensation is added to his weekly payout automatically without requiring any manual claim.

---

## Application Workflow

### 1. User Onboarding

The delivery partner registers using the mobile application and provides basic details such as:

* Name
* Delivery platform
* Working city or zone
* Average daily working hours

The system then generates a weekly insurance plan for the rider.

---

### 2. AI Risk Assessment

The system analyzes multiple risk factors including:

* Historical weather disruptions
* Pollution levels
* City risk index
* Delivery activity density
* Rider working patterns

Based on these inputs, an AI model calculates the weekly premium dynamically.

---

### 3. Real-Time Trigger Monitoring

InsurEdge continuously monitors external data sources through APIs including:

* Weather conditions
* Air Quality Index
* Traffic disruptions
* Local restrictions

If predefined thresholds are exceeded, the system activates a parametric trigger.

---

### 4. Automated Claim Validation

Once a disruption trigger is detected:

1. The system verifies the rider’s location and activity
2. The disruption event is validated
3. Estimated lost working hours are calculated

---

### 5. Weekly Payout Processing

All triggered disruptions during the week are aggregated. Compensation is calculated and transferred through a mock payment system once per week.

---

## Weekly Premium Model

InsurEdge operates on a weekly insurance pricing model designed to align with gig workers' earning cycles.

Instead of long-term insurance commitments, workers subscribe to small weekly premiums that provide protection against income loss during disruptions.

### Premium Calculation Factors

* Location risk level
* Historical weather disruptions
* Pollution patterns
* Average working hours
* Delivery demand density

### Example Pricing

| City      | Risk Level | Weekly Premium |
| --------- | ---------- | -------------- |
| Bangalore | Low        | ₹25            |
| Mumbai    | Medium     | ₹35            |
| Delhi     | High       | ₹45            |

This dynamic pricing ensures that workers only pay premiums proportional to their risk exposure.

---

## Parametric Triggers

Parametric triggers define the environmental or social conditions that automatically activate insurance coverage.

### Environmental Triggers

* Rainfall exceeding threshold levels
* Heatwave alerts
* Flood warnings
* Severe AQI levels

### Social Triggers

* Local curfews
* Delivery zone shutdowns
* Restricted access areas

When these triggers occur within the rider’s working area, the system automatically activates protection and calculates compensation.

---

## AI and Machine Learning Integration

AI plays a central role in the InsurEdge platform.

### AI Risk Assessment

Machine learning models analyze historical disruption patterns to calculate dynamic weekly premiums for each user.

Possible models include:

* Random Forest
* Regression models
* Gradient boosting algorithms

---

### Fraud Detection

AI-based anomaly detection helps prevent fraudulent claims.

Potential fraud scenarios include:

* GPS location spoofing
* Duplicate claims
* Claim attempts during inactive hours

The system uses anomaly detection techniques and location validation to identify suspicious behavior.

---

### Risk Prediction

Predictive models analyze environmental trends to estimate the likelihood of disruptions such as extreme rainfall or pollution.

This helps improve premium accuracy and strengthens the reliability of the insurance system.

---

## Platform Choice

### Mobile Application

The primary platform for InsurEdge will be a mobile application.

Reasons include:

* Delivery workers primarily operate using smartphones
* Real-time location monitoring is easier on mobile devices
* Push notifications allow immediate disruption alerts
* Simpler interaction during work hours

The user interface will prioritize simplicity and quick access to important information.

---

## User Experience Design

The application is designed for non-technical users who require a simple and intuitive interface.

### Home Screen

Displays:

* Active insurance coverage
* Weekly premium
* Current protection status

---

### Disruption Alerts

Users receive real-time alerts when environmental disruptions activate insurance protection.

---

### Earnings Protection Dashboard

Users can view:

* Total protected income
* Weekly compensation
* Disruption events covered

---

## Technology Stack

### Frontend

Mobile Application
Flutter 

---

### Backend

FastAPI
REST API architecture

---

### AI / ML

Python
Scikit-learn
Pandas
NumPy

---

### APIs

Weather Data – OpenWeather API
Air Quality Data – AQICN API
Location Services – Google Maps API

---

### Database

PostgreSQL or Supabase

---

### Payment Simulation

Razorpay Sandbox / 
Stripe Test Mode

---

## System Architecture

<p align="center">
  <img src="System_Architecture.png" width="750"/>
</p>

---

## Development Plan

### Phase 1 – Research and Planning

* Define user persona and problem scope
* Design system architecture
* Create workflow documentation
* Design prototype user interface

---

### Phase 2 – MVP Development

The minimum viable product will include:

* User registration
* Insurance policy management
* Dynamic premium calculation
* Parametric trigger detection
* Automated claim processing

---

### Phase 3 – Advanced Features

The final stage will include:

* AI-based fraud detection
* Instant payout simulation
* Intelligent analytics dashboard
* Predictive disruption analysis

---

## Adversarial Defense & Anti-Spoofing Strategy

### The Market Crash Scenario

It starts quietly.

A sudden spike in claims.
Hundreds of partners involved in delivery report similar disruptions simultaneously.

On the surface, it appears real — maybe heavy rain, maybe a local shutdown.
But something feels off.

500 riders.
Same locations.
Impeccably synchronized claims.

This isn’t a disruption.
It is a payout-draining GPS spoofing fraud ring.

And this is exactly the kind of situation that **InsurEdge** is designed to handle.

---

### Step 1: Do Not Trust, Verify Everything

A conventional system would trust GPS.
InsurEdge does not.

Instead of relying on a single signal, we build a **multi-source location verification system**:

* Network location (cell tower / IP)
* Device fingerprint
* Historical movement patterns

When a rider claims to be in a specific location, all signals must align within a defined threshold.

If Server <-> Client shows Mumbai but network data indicates otherwise → **a flag is raised instantly**.

---

### Step 2: Learn the Rider Before Judging the Claim

Every genuine worker behaves in patterns.

Over time, InsurEdge builds a **behavioral profile**:

* Usual working hours
* Frequent delivery zones
* Average movement speed
* Order activity rhythm

Now consider a fraudster:

* Suddenly appears in a new zone
* No delivery history in that area
* Claims disruption without prior activity
* Shows unrealistic movement patterns

This deviation is not random — it is detectable.

Using anomaly detection, the system evaluates:

> Does this behavior match the rider’s historical pattern?

If not → **risk score increases**.

---

### Step 3: Capture the Network, Not Just the Individual

Fraud at this scale is never an individual effort.

InsurEdge analyzes **group behavior**.

In this scenario:

* Hundreds of users claim from nearly identical coordinates
* Identical timing patterns
* Similar device or network signatures
* Claims from zones with no real disruption

This creates a **cluster signature**.

Instead of evaluating claims independently, InsurEdge identifies:

> Are these users behaving like a coordinated system rather than independent workers?

If yes → the system flags a **fraud ring**, not just individual users.

---

### Step 4: External Data Reality Check

Every claim must match real-world conditions.

InsurEdge cross-verifies with:

* Weather APIs
* AQI levels
* Traffic data
* Local restriction alerts

If users report heavy rain but weather data shows clear conditions, the system detects inconsistency immediately.

This is the strongest filter:

> No real-world disruption → No valid parametric trigger

---

### Step 5: Risk Scoring Instead of Binary Decisions

InsurEdge does not rely on simple approval or rejection.

Each claim is assigned a **dynamic fraud risk score** based on:

* Location mismatch
* Behavioral deviation
* Cluster detection
* External data inconsistency

#### Decision Logic

* Low Risk → Auto payout
* Medium Risk → Delayed verification
* High Risk → Flagged or blocked

This ensures fraud prevention while avoiding unfair rejection of genuine users.

---

### Step 6: Protect the Honest, Isolate the Fraud

During a fraud spike, the system adapts in real time:

* Suspicious clusters are isolated
* Risk thresholds are temporarily tightened
* High-risk zones undergo stricter validation

Importantly:

> Genuine users in the same area are not blindly blocked

Their claims are validated individually using behavior, history, and real-world data.

This ensures:

* Fraud rings are stopped
* Honest workers still receive payouts

---

### Step 7: Build Long-Term Trust

InsurEdge implements a **progressive trust model**:

* Consistently legitimate users gain higher trust scores
* Trusted users experience faster approvals
* New or suspicious users face stricter validation

Over time:

* Genuine users enjoy seamless payouts
* Fraudsters encounter increasing resistance

---

### Final Outcome

In a Market Crash scenario:

* The fraud ring is detected through cluster behavior and data inconsistencies
* Fake claims are isolated before payouts
* System liquidity is protected
* Genuine stranded workers continue to receive compensation

InsurEdge does not just verify claims.

It understands **context, behavior, and patterns**.

And that is how it answers the core question:

> How do you differentiate between a fraudster and a genuinely stranded worker?

By not relying on a single signal but by combining **data, behavior, and intelligence into one unified decision system**.
