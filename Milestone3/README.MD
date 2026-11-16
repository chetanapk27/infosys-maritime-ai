# FreightQuote AI – Milestone 3: Digital Twin Simulator Enhancements

## Project Overview

**FreightQuote AI** is an Agentic AI-based application designed for maritime freight pricing and route optimization. It supports freight quote analysis, operational monitoring, risk assessment, and decision-making through multiple AI-powered components.

This repository documents my individual contribution to **Milestone 3 – Task 4**, focusing on enhancing the Digital Twin simulation capabilities of FreightQuote AI.

## Individual Contribution

My contribution focuses on developing and enhancing five simulation modules that help evaluate different operational scenarios and their potential impact on maritime freight operations.

### 1. Route Simulator
- Evaluates alternative shipping routes.
- Analyzes the impact of fuel price changes.
- Compares route distance, transit time, and additional costs.
- Helps assess route-related cost variations.

### 2. Pricing and Margin Simulator
- Allows adjustment of target profit margins.
- Evaluates fuel-price and carrier-rate changes.
- Analyzes discount impacts.
- Estimates expected profit and quote win probability.
- Identifies quotes that may fall below the target margin.

### 3. Carrier Outage Simulator
- Simulates carrier capacity disruptions.
- Evaluates carrier reliability.
- Identifies displaced shipments.
- Ranks alternative carriers for reassignment.
- Estimates additional costs associated with carrier disruptions.

### 4. Weather and Storm Simulator
- Allows adjustment of storm-related parameters such as wind speed, storm radius, and duration.
- Identifies vessels and shipments potentially affected by weather conditions.
- Estimates shipment delays and demurrage costs.
- Evaluates the operational impact of severe weather scenarios.

### 5. Customs Simulator
- Simulates changes in customs inspection rates.
- Evaluates the impact of missing shipment documents.
- Estimates additional customs delays.
- Calculates potential holding and storage costs.
- Analyzes the impact of duty changes on open quotes.

## Technologies Used

- Python
- Streamlit
- Pandas
- NumPy
- Plotly
- SQLite
- FastAPI

## Screenshots and Demonstration

The `screenshots/simulators/` directory contains screenshots demonstrating the simulator interfaces and their outputs.

These screenshots provide visual evidence of the implemented simulation modules and their scenario analysis results.

## Access Control

The simulator modules are available to authorized operational roles, including Admin and other permitted roles. Customer accounts do not have access to these internal simulation features.

## Important Note

The simulators use configurable assumptions and available application data to evaluate hypothetical operational scenarios. Simulation outputs should be interpreted as estimates rather than guaranteed real-world outcomes.

Some application data, including vessel positions, shipment information, and freight prices, may be simulated rather than sourced from live operational feeds.

## My Role and Contribution

**Milestone:** 3  
**Task:** 4 – Digital Twin Simulator Enhancements  
**Project:** FreightQuote AI – Agentic AI for Maritime Freight Pricing and Route Optimization

My individual contribution focused on enhancing the five simulator modules: Route, Pricing and Margin, Carrier Outage, Weather and Storm, and Customs Simulation.

