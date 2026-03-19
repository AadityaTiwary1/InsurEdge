# MARKET CRASH SEPERATE (.md) CREATED.

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

Deliverables include a README document and a prototype demonstration video.

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

## Innovation Highlights

InsurEdge introduces an automated parametric insurance system tailored specifically for gig workers.

Key innovations include:

* AI-driven dynamic premium calculation
* Automated claim settlement without manual intervention
* Real-time disruption monitoring
* Simple mobile-first user experience

The goal is to provide gig workers with a reliable financial safety net while simplifying the insurance process through automation and AI.
