# Week 10 Interim Report: Change Point Analysis of Brent Oil Prices

## 1. Data Analysis Workflow

A robust workflow is essential for extracting actionable insights from Brent oil price data. The process is as follows:

- **Data Preparation:**
  - The raw dataset is loaded from CSV, containing daily Brent oil prices from 1987 to 2022. Dates are parsed and sorted to ensure chronological order. Missing values are checked and handled, and outliers are flagged for review.
  - Data cleaning includes converting date strings to datetime objects and verifying price values are numeric and within expected ranges.
- **Event Research:**
  - Major geopolitical, economic, and OPEC-related events are researched using reputable sources (e.g., news archives, OPEC reports, academic papers). Each event is documented with a clear description and an accurate start date.
  - The event dataset is structured in CSV format, allowing for easy merging with price data and facilitating time-based analysis.
  - Events are selected based on their potential to impact global oil markets, with a focus on those causing significant price shifts.
- **Exploratory Data Analysis (EDA):**
  - Time series plots of raw prices reveal long-term trends, cyclical patterns, and periods of high volatility. These visualizations help form initial hypotheses about market behavior and event impacts.
  - Log returns are calculated to transform the non-stationary price series into a stationary one, making it suitable for statistical modeling. Volatility clustering is observed, indicating periods where large price changes are followed by further volatility.
  - Summary statistics (mean, variance, skewness, kurtosis) are computed for both prices and log returns to understand distributional properties.
- **Change Point Modeling:**
  - Bayesian change point detection is implemented using PyMC. The model identifies points in the time series where the statistical properties (mean, volatility) shift, often corresponding to major events.
  - The model uses a discrete uniform prior for the change point (tau), and normal priors for the mean before and after the change. The likelihood is defined using a normal distribution for log returns.
  - MCMC sampling is run to estimate the posterior distributions of tau, mu_1, mu_2, and sigma.
- **Event Association:**
  - Detected change points are compared with the event dataset. Temporal proximity and qualitative analysis are used to hypothesize causal relationships between events and price shifts.
  - Multiple change points may be detected, and each is evaluated for its association with one or more events.
- **Impact Quantification:**
  - The magnitude of price changes before and after each change point is measured. This includes shifts in mean log return and changes in volatility.
  - Results are reported as percentage changes and visualized for clarity.

## 2. Event Dataset Quality

A high-quality event dataset is crucial for meaningful analysis:

- **Coverage:**
  - The dataset includes 15+ major events, such as wars, sanctions, OPEC policy changes, and economic crises. Each event is selected for its documented impact on oil prices.
- **Accuracy:**
  - Event dates are cross-checked with multiple sources to ensure precision. Descriptions are concise yet informative, providing context for each event.
- **Structure:**
  - The CSV format includes columns for date, event name, description, and type (e.g., conflict, policy, sanction). This structure supports filtering and analysis by event type.
- **Limitations:**
  - Some events may have indirect or delayed effects on prices. Market reactions can be influenced by speculation, sentiment, and other factors not captured in the dataset.
  - Not all impactful events may be included, and some may overlap or interact in complex ways.
- **Quality Control:**
  - Events are reviewed for relevance and accuracy. The dataset is updated as new information becomes available.

## 3. Time Series Properties

Understanding the statistical properties of Brent oil prices is foundational:

- **Non-Stationarity:**
  - Raw price data shows clear trends and cycles, indicating non-stationarity. This is typical for financial time series affected by macroeconomic forces.
- **Log Returns and Stationarity:**
  - Transforming prices to log returns stabilizes the mean and variance, making the series stationary and suitable for change point modeling.
  - Stationarity is confirmed using statistical tests (e.g., Augmented Dickey-Fuller, KPSS) and visual inspection of log return plots.
- **Volatility Clustering:**
  - Periods of high volatility are observed, often following major events. This clustering is a hallmark of financial time series and informs model selection.
- **Distributional Properties:**
  - Log returns are approximately normally distributed, but may exhibit skewness or kurtosis during crisis periods. These properties are considered when specifying model priors.

## 4. Assumptions and Limitations

All analyses are subject to assumptions and limitations:

- **Assumptions:**
  - Event dates are accurate and relevant to observed price changes.
  - Log returns are sufficiently normal for the chosen model.
  - Change points correspond to structural breaks caused by major events.
  - The model captures the main drivers of price changes, ignoring minor or short-term fluctuations.
- **Limitations:**
  - Statistical correlation does not prove causality; detected change points may coincide with events by chance.
  - Model results depend on data quality, prior selection, and sampling convergence.
  - Overlapping or compounding events may obscure individual impacts.
  - Real-time market factors, such as speculation or micro-events, are not modeled.
  - The model may miss gradual or multi-phase changes, focusing on abrupt shifts.

## 5. Purpose of Change Point Models

Change point models serve several key purposes in this context:

- **Detection of Structural Breaks:**
  - Identify statistically significant shifts in the mean or volatility of oil prices, often linked to external events.
- **Event Association:**
  - Pinpoint when changes occur and associate them with documented events, providing evidence for causal hypotheses.
- **Quantitative Insights:**
  - Estimate the magnitude of changes, supporting investment, risk management, and policy decisions.
- **Limitations:**
  - Models may miss subtle or gradual changes, and results are probabilistic. Multiple change points may be present, requiring careful interpretation.
- **Communication:**
  - Outputs are visualized and reported in a way that is accessible to stakeholders, including investors, analysts, and policymakers.

## 6. Future Work: Interactive Dashboard (Task 3)

### Dashboard Vision

A modern dashboard will empower stakeholders to explore analysis results interactively:

- **Backend (Flask):**
  - Develop RESTful APIs to serve cleaned data, event lists, and model outputs.
  - Support queries for specific time periods, events, and performance metrics.
  - Integrate real-time data sources for live updates, if required.
  - Ensure secure and efficient data handling.
- **Frontend (React):**
  - Build a responsive, user-friendly interface using React.
  - Integrate interactive charts (Recharts, React Chart.js 2, D3.js) to visualize price changes, event impacts, and model results.
  - Implement filters for event type, date range, and comparison of periods.
  - Enable users to drill down into specific events and time windows.
  - Ensure compatibility across devices (desktop, tablet, mobile).

### Key Features

- **Event-driven Exploration:**
  - Users can select events and instantly view associated price changes and model outputs.
- **Dynamic Filtering and Comparison:**
  - Filter by event type, date range, or compare multiple periods/events.
- **Actionable Visualizations:**
  - Clear, interactive charts support decision-making for investors, analysts, and policymakers.
- **Scalability and Extensibility:**
  - The dashboard is designed for future expansion, including new data sources, models, and user roles.

---

This expanded interim report provides a comprehensive foundation for the final dashboard development in Task 3, ensuring all stakeholders have the insights and tools needed for effective decision-making.
