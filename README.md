# 🧓 2026-01 Regional Digital Overload Analysis

This repository contains an early-stage data analysis project exploring regions affected by digital overload, classifying them into four types, and proposing potential solutions for each category.

## 📌 Project Overview

The rapid digitalization of public services has raised concerns about the growing digital gap for older populations.

Rather than focusing only on digital exclusion, this project began with a different question: could there be regions experiencing digital overload instead?

To explore this idea, we chose to analyze the usage of public self-service kiosks, specifically unmanned government service machines, as a reliable and consistent indicator of regional digital demand.

Commercial kiosk data from private businesses was considered less stable, so public-sector kiosks were selected as the primary proxy for measuring regional digitalization.

This question and data choice marked the starting point of the project.

## 🛠️ Core Workflow

**1. Data Collection**

The project began by collecting demographic and public administrative infrastructure data from two primary sources:

* KOSIS (Korean Statistical Information Service) population statistics
* Ministry of the Interior and Safety data on unmanned civil service kiosks

**2. Index Construction & Preprocessing**

The main objective of preprocessing was to construct two composite indicators: 

the **Digital Overload Index** and the **Unmanned Administrative Supply–Demand Imbalance Index**.

Key variables were defined as:

* Elderly population ratio = elderly population (region) / total population (region)
* Single-elderly household ratio = elderly living alone (region) / total population (region)
* Unmanned administrative supply ratio = number of kiosks (region) / total population (region)
* Administrative demand ratio = total population (region) / total population (nationwide)

Using normalized values:

* **Digital Overload Index**
  = normalized(elderly ratio) × normalized(single-elderly ratio) × normalized(kiosk supply ratio)

* **Administrative Supply–Demand Imbalance Index**
  = normalized(administrative demand ratio) − normalized(unmanned administrative supply ratio)

**3. Index-Based Regional Classification**

Regions were grouped using percentile thresholds:

* Top 30% (High) 
* Middle 40% (Medium)  
* Bottom 30% (Low)

Both indices were visualized separately through choropleth maps to examine their geographic distribution across administrative regions.

**4. Quadrant Analysis Framework**

The two indices were then designed to be combined into a quadrant framework to classify regions into four types:

* **Compound Risk Regions** — high on both indices
* **Digital Overload Regions** — high overload, low supply imbalance
* **Supply Deficit Regions** — low overload, high supply imbalance
* **Optimally Operated Regions** — low on both indices

This framework was intended to support the development of tailored policy and design recommendations for each region type.

## 📦 Project Status

The project progressed through the data collection and index construction stages.

However, during internal review, the team identified a critical assumption underlying the project: that increased exposure to digital devices has a measurable negative impact on older populations.

A follow-up literature review was conducted to validate this premise, but the team concluded that there was insufficient quantitative evidence to support the assumption at the level required for further analysis.

As a result, the project was intentionally concluded after the preprocessing and index design stage, and the repository is preserved as an archive of the early research workflow.


## 📝 Note

The original project proposal, notebook comments, and figures are written in Korean.

## 📂 Repository Contents

* `분석_노트북/` — preprocessing and index-construction notebooks
* `2_연구_주제/` — project proposal and selected presentation figures

## 🔒 Data Availability

Raw, processed, and reference materials are intentionally excluded from this public repository.
The analysis used public demographic and public-service infrastructure data collected from KOSIS
and the Ministry of the Interior and Safety. The notebooks are preserved to document the analytical
workflow; reproducing the results requires obtaining the source data separately and placing it in the
original local data directories.
