Traffic Accidents Severity Analysis
A data-driven exploration of factors influencing accident severity in the U.S.

Project Overview
This project investigates patterns in traffic accident severity using a large dataset loaded and processed with PySpark for efficiency and scalability. The goal is to uncover key temporal, spatial, environmental, and infrastructural factors that relate to accident severity, ultimately highlighting areas for potential intervention.

Data Understanding
The dataset was initially explored using PySpark, focusing on understanding the structure, schema, and formats of each field. A preliminary sample inspection provided insights into variable distributions and possible data quality issues.

Data Preparation
A quality check was conducted across all columns to assess missing values, including the calculation of missing data percentages per column. Rather than mass deletion, a conservative approach was adopted, prioritizing strategic imputation to preserve data integrity.

The severity variable was identified as the primary target. Its distribution is heavily skewed:

Severity 2: 80% of cases
Severity 3: 17%
Severity 4: 3%

To better analyze this variable, two features were created:
average_severity
high_severity (defined as severity ≥ 3)

Duplicate records were removed (~7% of the dataset), and new features were engineered across multiple dimensions:

Temporal (hour of day, day of week)

Spatial (state, region)

Environmental (temperature, visibility)

Infrastructure (traffic control, POIs)

Exploratory Data Analysis (EDA)
Temporal Patterns
Accidents by hour of day and peak hours
Day-of-week trends
Weekday vs weekend comparisons

Spatial Patterns
State-level distribution
Urban vs rural analysis
Regional trends

Environmental Patterns
Weather impact
Temperature and visibility effects

Infrastructure Patterns
A key turning point in the analysis came from exploring structural factors beyond natural phenomena, which offer more limited room for intervention.

POI Impact
Areas with 0 POIs: average severity = 2.253

Areas with 1+ POIs: average severity = 2.176
This reflects an 8.1% reduction, possibly indicating a buffering effect from infrastructure or service density.

Traffic Control Effectiveness
Average severity reduced by 7.2% in areas with traffic signals or signs
High-severity accidents dropped by 60.4%
Without control: 22.9%
With control: 9.1%

Key Takeaways
Natural factors (like time and weather) show clear patterns, but offer limited actionability.
Infrastructure-related features—especially traffic control and POI presence—correlate with meaningful reductions in severity.
These findings suggest that investing in urban infrastructure and traffic regulation could directly impact accident outcomes.

Tech Stack
PySpark for scalable data processing
Pandas & NumPy for supplementary data manipulation
Matplotlib, Seaborn, Plotly for data visualization
Jupyter Notebooks as development environment

Next Steps
Build predictive models for severity classification
Test policy-based scenarios (e.g., increased traffic control)
Create an interactive dashboard for public agencies
