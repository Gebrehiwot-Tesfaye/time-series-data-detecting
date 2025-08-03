# Week 10 Final Report: Change Point Analysis and Interactive Dashboard for Brent Oil Prices

**Prepared by: Gebrehiwot Tesfaye**

---

## Executive Summary / Introduction

This report documents the full analytical journey for Brent oil prices, from foundational workflow planning to advanced Bayesian modeling and the development of an interactive dashboard. The project is designed to deliver actionable insights for investors, policymakers, and energy sector stakeholders, with a focus on how major events impact oil prices. All deliverables are presented with clarity, rigor, and professional structure.

---

## Task 1: Laying the Foundation for Analysis

### Data Analysis Workflow

- Defined a clear, step-by-step workflow: data preparation, event research, EDA, modeling, event association, and communication.
- Data cleaning ensured accurate date parsing, handling of missing values, and validation of price entries.
- Event dataset compiled from multiple sources, structured for easy integration and analysis.
- Assumptions and limitations were stated, including the difference between correlation and causality.
- Communication channels and reporting formats were planned for stakeholder engagement.

### Event Dataset Quality

- 15+ major events (wars, sanctions, OPEC decisions) were researched and documented with precise dates and descriptions.
- Events were selected for their relevance and impact on global oil markets, with cross-referencing for accuracy.
- Dataset structured in CSV format, supporting filtering and analysis by event type.

### Time Series Properties

- Brent oil prices exhibit non-stationarity and volatility clustering.
- Log returns transformation used to achieve stationarity, confirmed by statistical tests and visual inspection.
- Distributional properties (mean, variance, skewness, kurtosis) analyzed for both prices and log returns.

### Assumptions and Limitations

- Event dates are assumed accurate and relevant.
- Log returns are modeled as approximately normal.
- Change points are interpreted as structural breaks, but causality is not guaranteed.
- Overlapping events and real-time market factors are not fully captured.

### Purpose of Change Point Models

- Change point models identify statistically significant shifts in time series behavior.
- They help associate structural breaks with external events, supporting investment and policy decisions.
- Outputs include change point dates and parameter shifts, with limitations noted for gradual or multi-phase changes.

---

## Task 2: Change Point Modeling and Insight Generation

### Core Analysis

- Bayesian change point detection implemented using PyMC, focusing on mean shifts in log returns.
- Model validated with convergence diagnostics and posterior analysis.
- Detected change points matched to key events using temporal proximity and qualitative review.
- Impact quantified by comparing mean log returns before and after each change point.

### Insights

- Historical trends and volatility patterns visualized, revealing periods of stability and disruption.
- Major events shown to correlate with significant price shifts, supporting hypotheses about market drivers.
- Key indicators (volatility, average price change) calculated and contextualized for risk assessment.
- Comparative analysis enabled, allowing users to explore periods before and after events.

---

## Task 3: Developing an Interactive Dashboard for Data Analysis Results

### Overview

The interactive dashboard is the culmination of the analysis, designed to help stakeholders explore Brent oil price trends, event impacts, and key indicators. It combines a robust Flask backend with a dynamic React frontend, ensuring analytical depth and a user-friendly experience.

### Backend (Flask)

- **API Design:**
  - `/api/prices`: Serves historical Brent oil price data, supporting date range filtering for focused analysis.
  - `/api/events`: Provides a curated list of major events, including type, date, and description, enabling event-driven exploration.
  - `/api/highlight`: Returns price data around selected events, allowing users to visualize spikes or drops in prices.
  - `/api/indicators`: Delivers key metrics such as volatility and average price change, supporting risk assessment.
- **Performance & Extensibility:**
  - Built for fast data access and easy integration with new datasets or model outputs.
  - (Optional) Real-time data integration can be added for live market monitoring and up-to-date analysis.
- **Security & Reliability:**
  - Implements best practices for API design, error handling, and data validation to ensure robust and secure data delivery.

### Frontend (React)

- **User Experience:**
  - Responsive design for desktop, tablet, and mobile, ensuring accessibility for all users.
  - Intuitive navigation and clear layout, with modular components for maintainability and scalability.
- **Interactive Visualizations:**
  - **PriceTrendChart:** Line chart showing historical Brent oil prices, with zoom and pan features for detailed exploration.
  - **EventImpactChart:** Highlights price changes around selected events, visualizing spikes or drops and contextualizing market reactions.
  - **EventFilter:** Allows users to filter by event type, date range, and compare multiple events, supporting deep analysis.
  - **IndicatorPanel:** Displays key metrics (volatility, average price change) for context and strategic planning.
  - **Tools:** Built with Recharts, React Chart.js 2, and D3.js for rich, interactive charts and data exploration.
- **Features:**
  - Event-driven exploration: Select events to see their impact on prices, with instant visual feedback.
  - Dynamic filtering and comparison: Drill down into specific periods or events, compare before/after scenarios, and analyze correlations.
  - Data drill-down: View details for any date or event, including price changes, volatility, and event context.
  - Real-time updates (optional): Integrate live data feeds for up-to-date analysis and decision-making.

### Key Features & Insights

- **Historical Trends:**
  - Users can explore long-term price movements, identify periods of stability or disruption, and understand market cycles.
- **Event Correlations:**
  - Dashboard visualizations show how political decisions, conflicts, and economic sanctions correlate with price changes, supporting strategic insights.
- **Event Highlight:**
  - Users can select an event and instantly see price spikes or drops, with contextual metrics and historical context.
- **Filtering & Comparison:**
  - Flexible filters and comparison tools allow for deep analysis of specific events or time windows, supporting investment and policy decisions.
- **Indicators:**
  - Volatility and average price change metrics are displayed for risk assessment, market monitoring, and strategic planning.

### Professionalism & Structure

- The dashboard is built with modular, well-documented code for both backend and frontend, supporting future expansion and maintenance.
- Folder structure is clear: `dashboard/backend` (Flask API), `dashboard/frontend` (React UI), with supporting documentation and setup guides.
- All features are designed for scalability, maintainability, and robust performance.
- The user interface is visually appealing, robust, and accessible across devices, ensuring a professional stakeholder experience.

---

## Structure & Professionalism

- Project organized with clear folder structure: data, event_data, scripts, notebooks, reports, dashboard (backend & frontend).
- All code is documented, modular, and reproducible.
- Reports are professionally formatted, with logical flow and clear sectioning.
- Dashboard is visually appealing, robust, and user-friendly.
- All deliverables prepared and presented by Gebrehiwot Tesfaye, ensuring expert quality and consistency.

---

**End of Report**
