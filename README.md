# Business Performance Insight Suite 📊

An enterprise-grade, interactive Power BI Project (PBIP) designed to track, model, and optimize key corporate performance metrics, commercial performance, and target goals. 

This repository leverages Power BI’s modern developer-mode layout, splitting the data infrastructure into transparent semantic schemas (`.SemanticModel`) and customizable report visuals (`.Report`) to support scalable, version-controlled business intelligence workflows.

---

## Project Architecture & Data Modeling

The business intelligence architecture is built on an optimized star/snowflake schema to ensure rapid query processing, clear relationship paths, and efficient memory usage inside the VertiPaq storage engine.

### Data Model Schema Components:
*   **Fact Tables:** Core transactional logic housing business tracking metrics (e.g., `All_orders`).
*   **Dimension Tables:** Contextual mapping tables providing deep descriptive layers (e.g., `People`, `Returns`, `Risk_Labels`).
*   **Time Intelligence:** A highly optimized calendar dimension (`Date_Table`) utilized for dynamic period-over-period performance tracking.
*   **Target Metrics:** Explicit threshold parameters (`Target`) built into the semantic core to map actual outcomes against corporate goals.

---

## Key Dashboard Features & Insights

*   **Dynamic Executive Overview:** High-level executive views tracking primary Key Performance Indicators (KPIs) across multiple dimensions.
*   **Goal Tracking & Target Analysis:** Visualizations highlighting variances between forecasted organizational targets and real-time outcomes.
*   **Risk Profile Mapping:** Segments tracking operational discrepancies, returns, and vulnerability points using custom categorical mapping.
*   **Advanced DAX Logic:** Leverages dedicated DAX script metrics (structured within the `Measures` folder) to build dynamic time-intelligence filters and contextual variance scoring.

---

## Dashboard Visuals & Interface

This dashboard is divided into 4 specialized views, allowing users to drill down from high-level executive performance to deep regional, target achievement, and operational efficiency analysis.

### 1. Business & Overview Page
<img width="1009" height="802" alt="Business   OverView" src="https://github.com/user-attachments/assets/2aed1cd5-1dc3-4773-be8e-9919d464928e" />
*   **Purpose:** Acts as the primary executive view, tracking high-level metrics across sales, profits, profit margins, and volume trends.
*   **Key Highlights:** 
    *   Tracks macro KPIs (e.g., Total Sales of \$653K, Profit Margin of 12.87% for the active filter year).
    *   Features an interactive monthly sales trend line chart alongside category pie distribution (Office Supplies dominating at 37%).
    *   Displays performance broken down by core customer segments (Consumer, Corporate, Home Office) and year-over-year growth metrics.

### 2. Region & Manager Scorecard View
<img width="1008" height="801" alt="Region   Manager" src="https://github.com/user-attachments/assets/61680d1a-712c-4552-a531-ed11215a6143" />

*   **Purpose:** Focuses on geographical data and operational leadership performance analysis.
*   **Key Highlights:**
    *   Breaks down sales performance and profit margin metrics across key European regional segments (Central, North, South).
    *   Includes a structured Manager Performance Scorecard displaying individual metrics for regional leaders (Emily Burns, Ross DeVincentis, Damala Kotsonis).
    *   Tracks discrete categorical distribution (Furniture vs. Office Supplies vs. Technology) dynamically mapped by geographic territory.

### 3. Target Achievement & Variance Analysis
<img width="1008" height="806" alt="Target Achievement" src="https://github.com/user-attachments/assets/1693d125-7f0b-467c-baa4-2eaf4da59391" />

*   **Purpose:** Tracks business goals and highlights shortfalls or surpluses against corporate benchmarks.
*   **Key Highlights:**
    *   Compares total targets directly to actual sales using clear variance bars (e.g., highlighting an active achievement rate baseline of 17%).
    *   Features a detailed Manager × Category matrix mapping total targets directly beside actual sales to reveal the precise performance gap.
    *   Includes a conditional, color-coded visual indicator displaying whether product lines successfully achieved corporate goals or fell into shortfall thresholds.

### 4. Returns & Operational Delays View
<img width="1019" height="813" alt="Returns   Delays" src="https://github.com/user-attachments/assets/579f0036-27f3-41f2-9579-052adb361626" />

*   **Purpose:** Highlights supply chain vulnerabilities, processing bottle-necks, and product risk factors.
*   **Key Highlights:**
    *   Monitors supply chain risk via absolute metrics like Total Returns, Return Rate (18%), Delayed Orders, and overall Delay Rate (94%).
    *   Breaks down returns cleanly across product categories and regions to pinpoint defective inventories or shipping pipelines.
    *   Features an Average Shipping Days metrics card analyzed by shipping tier mode (Standard Class, Second Class, First Class, Same Day) paired with a regional breakdown of order backlogs exceeding 4 days.

---

## Technical Stack Used

*   **BI Platform:** Power BI Desktop (Saved as `.pbip` for version control)
*   **Data Modeling Layer:** Power Query (M Language) for ETL pipelines and data sanitization
*   **Analytical Expressions:** DAX (Data Analysis Expressions) for complex, optimized measurements
*   **Semantic Language Engine:** Tabular Model Definition Language (TMDL) metadata structures

---

## Repository File Structure

```text
├── Business Performance Insight Suite.pbip      # Main project entry file
├── Business Performance Insight Suite.Report    # Front-end visual settings and layouts
│   ├── item.config.json
│   └── report.json
└── Business Performance Insight Suite.SemanticModel  # Data schema and underlying modeling files
    ├── definition.pbmism
    ├── database.tmdl                            # Tabular database schema
    ├── tables/                                  # Individual semantic table models
    │   ├── All_orders.tmdl                      
    │   ├── Date_Table.tmdl                      
    │   ├── Measures.tmdl                        # Centralized DAX definitions
    │   └── Target.tmdl                          
    └── diagramLayout.json
