# ENERGY DEMAND ANALYSIS – NB Power (May 2025)

## 📘 Project Overview

The **Energy Demand Analysis Dashboard** provides a comprehensive view of hourly electricity demand and inter-regional energy flows for **New Brunswick Power (NB Power)** during the month of **May 2025**. The dashboard is built in **Power BI** and leverages dynamic visualizations and KPIs to help analysts, policymakers, and stakeholders monitor and interpret power usage patterns and cross-border electricity exchange.

The project aims to:
- Monitor **peak and off-peak energy demand** at an hourly level
- Compare **energy demand and load trends**
- Assess **net energy inflows and outflows** across regions like ISO-NE, NMISA, PEI, Quebec, and Nova Scotia
- Provide **interactive date filtering** to explore custom time frames

---

## 📊 Dashboard Components

### 🧮 Key Performance Indicators (KPIs)

Three KPIs are displayed prominently to summarize critical energy demand metrics:

| KPI                          | Description |
|-----------------------------|-------------|
| **Total Energy Demand**     | The total sum of hourly NB_DEMAND over May 2025, representing the total energy consumed during the month |
| **Peak Demand (MW)**        | The **highest hourly demand** recorded in the month (maximum of NB_DEMAND) |
| **Lowest Demand (MW)**      | The **lowest hourly demand** recorded in the month (minimum of NB_DEMAND) |

These indicators are dynamically updated based on date slicer selection.

---

### 📈 Visualizations and Charts

#### 1. **Hourly Energy Demand Trend**
- **Type**: Line chart
- **X-Axis**: Hour (DateTime)
- **Y-Axis**: NB_DEMAND
- **Purpose**: Tracks the hourly fluctuations in energy demand over the month. Useful to identify peaks, dips, and operational trends.

#### 2. **Demand by Hour of Day**
- **Type**: Column chart
- **X-Axis**: HourOfDay (0–23)
- **Y-Axis**: Average of NB_DEMAND
- **Purpose**: Shows the average demand at each hour of the day across May. Helps in identifying recurring demand patterns (e.g., morning/evening peaks).

#### 3. **Average NB Demand vs NB Load**
- **Type**: Horizontal bar chart
- **Values**: Average of NB_DEMAND and NB_LOAD
- **Purpose**: Provides a comparative view of the energy demand and load generation capacity, helping assess system balance.

#### 4. **Net Flow by Region**
- **Type**: Bar chart (unpivoted data)
- **X-Axis**: Net Flow (MW)
- **Y-Axis**: Region
- **Purpose**: Visualizes energy exchanged with each neighboring region. Positive values indicate net import; negative values represent net export.

#### 5. **Total Energy Flow by Region**
- **Type**: 100% stacked bar chart (Region-level)
- **X-Axis**: % of Total Flow
- **Y-Axis**: Region
- **Purpose**: Displays the proportion of energy flow distribution among connected regions.

---

### 🎛️ Interactive Features

- **Date Range Slicer**
  - Field: `HOUR` (DateTime)
  - Purpose: Allows users to dynamically filter the entire dashboard by selecting a custom date range within May 2025.

All visuals and KPIs update automatically based on the selected date range.

---

## 🗂️ Dataset Description

| Column Name         | Description |
|---------------------|-------------|
| `HOUR`              | Timestamp for each hourly record |
| `NB_DEMAND`         | Measured energy demand in megawatts (MW) |
| `NB_LOAD`           | Actual load generation in NB (MW) |
| `ISO_NE`, `NMISA`, `PEI`, `QUEBEC`, `NOVA_SCOTIA` | Energy flow values for each region (in MW) |
| `Flow (MW)`         | Unpivoted value of flow for dynamic visuals |
| `Region`            | Region name corresponding to each Flow (MW) record |
| `HourOfDay`         | Hour extracted from HOUR (used for aggregation by time of day) |

The dataset was cleaned and transformed in Power BI to:
- Extract `HourOfDay` from the `HOUR` column
- Unpivot regional flow columns for flexible visualization
- Create calculated measures for KPIs (Peak, Lowest, Total Demand)

---

## 📌 Use Cases

This dashboard is intended for use by:
- **Grid operators** – to analyze demand fluctuations and optimize generation scheduling
- **Energy analysts** – for tracking consumption trends and identifying usage behaviors
- **Policy planners** – for evaluating energy trade dependencies with other regions
- **Infrastructure teams** – to monitor strain points and plan load balancing systems

---

## Implemented Enhancements

- Calculated measures for:
  - Peak Hourly Demand (MW)
  - Lowest Hourly Demand (MW)
  - Total Monthly Demand
- Created custom time-based dimension (`HourOfDay`)
- Unpivoted regional columns to create flexible net flow visuals
- Integrated interactive slicer for filtering visuals and KPIs by date
- Designed consistent color theme and spacing for presentation-quality visuals

---


## 👨‍💻 Author

**Kusuma Sri Neelapala**  
 Data Analyst  
📜 Certifications:  
- Microsoft Certified: Power BI Data Analyst Associate (PL-300)  
- Microsoft Azure Data Fundamentals  
- ISTQB Certified Tester  
💡 Skills: Power BI, Python, SQL, Data Visualization, Predictive Modeling

---

## 📎 File Information

- **Power BI File**: `EnergyDemand_May2025.pbix`
- **Last Updated**: June 2025
- **Dataset Source**:  NB Power system hourly dataset 

