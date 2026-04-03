# India’s Air Quality 2025

Project Objective :

The objective of this project is to analyze, visualize, and communicate air quality data across Indian cities and states using pollutant-level monitoring information. By integrating station-level readings (PM2.5, PM10, NO2, SO2, CO, Ozone, NH3) with geospatial and concern-level classifications, the dashboard aims to:
Monitor Pollution Trends
Track pollutant concentrations across 3,000+ cities and 30 states/UTs, highlighting hotspots and temporal variations.
Assess Public Health Risk
Translate AQI ranges into concern levels (Good, Moderate, Poor, Very Poor, Severe) to make technical data accessible for stakeholders and citizens.
Enable Geospatial Insights
Map pollutant distribution geographically to identify regional disparities and clusters of poor air quality.
Support Decision-Making
Provide actionable intelligence for policymakers, environmental boards, and urban planners to prioritize interventions.
Enhance Transparency & Awareness
Present pollutant breakdowns (e.g., PM2.5 vs PM10 dominance) and monitoring board performance to improve accountability and public engagement.

The goal of this project is to develop a comprehensive, interactive dashboard that transforms raw air quality monitoring data into actionable insights for policymakers, environmental boards, researchers, and the public.


Data Sources :
Data Source : Indian Government website https://www.google.com/url?q=https://www.data.gov.in/catalog/real-time-air-quality-index&sa=D&source=editors&ust=1770185091263853&usg=AOvVaw0RR81SNRhC5ceWW-RTCqRZ
Domain: Environment
Problem Statement :

India faces a critical challenge in monitoring and managing air quality across its diverse states and cities. Rapid urbanization, industrial activity, and vehicular emissions have led to rising levels of pollutants such as PM2.5, PM10, NO2, SO2, CO, Ozone, and NH3, which pose severe risks to public health and the environment.
Despite the availability of monitoring stations and raw pollutant data, the information is often:
• 	Fragmented across multiple boards and regions.
• 	Difficult to interpret for non-technical stakeholders due to its complexity.
• 	Lacking in actionable insights, making it hard for policymakers to prioritize interventions.
• 	Geospatially scattered, preventing clear identification of pollution hotspots and regional disparities.

Attribute Details :

<img width="753" height="481" alt="Image" src="https://github.com/user-attachments/assets/9eb88073-9718-42fd-931f-f9547353079f" />

Tools :
Microsoft Excel 
Data Cleaning 
Data Transformation 
Removing duplicates 
Handling missing values 
Standardizing formats 
Conditional Formatting

Power BI 
Data modelling 
DAX calculations 
Interactive dashboard creation
Risk categorization 
Drill-down analysis

Data Pre-Processing :
Data Cleaning
Standardized Column Names
Raw dataset had inconsistent headers (country, state, city, station, pollutant_id, etc.).
Cleaned dataset uses consistent, properly capitalized names (Country, State, City, Station, Pollutant_id, etc.).
Added new descriptive columns like Monitoring Board, AQI range, and Concern level.
Removed Redundancy
Raw data contained duplicate entries for the same station with different pollutants.
Cleaned dataset organizes pollutants per station in a structured way, avoiding repetition.
Corrected Station Metadata
Raw dataset had station names with appended board identifiers (e.g., “Naharlagun, Naharlagun - APSPCB”).
Cleaned dataset separates Station and Monitoring Board into distinct columns (e.g., “MIT Daudpur Kothi, Muzaffarpur” and “BSPCB”).

Date/Time Handling
Raw dataset had last_update timestamps.
Cleaned dataset removed them, focusing on pollutant values and AQI classification.
Consistent Units & Values
Raw pollutant values (pollutant_min, pollutant_max, pollutant_avg) were retained but normalized.
Cleaned dataset ensures these values are numeric and aligned for AQI calculation.

Data Imputation :
AQI Calculation
Added AQI range column by applying AQI formula/lookup tables to pollutant averages.
Example: For NO2 avg = 2 → AQI ≈ 3.33 (Good).
Concern Level Classification
Mapped AQI ranges to qualitative categories:
0–50 → Good
51–100 → Satisfactory
101–200 → Moderate
201–300 → Poor
301–400 → Very Poor
401+ → Severe
Example: PM2.5 avg = 100 → AQI ≈ 231.72 → Poor.
Missing Value Handling
Raw dataset had pollutants with identical min/max/avg (e.g., NH3 = 1,1,1).
Cleaned dataset imputes AQI values using standard conversion factors instead of leaving them blank or zero.
Normalization Across Pollutants
Different pollutants (SO2, NO2, PM10, PM2.5, CO, Ozone, NH3) were scaled to AQI equivalents.
Ensures comparability across stations.



Analysis and Visualizations

India Air Quality Index
<img width="1289" height="719" alt="Image" src="https://github.com/user-attachments/assets/2de136d9-b73c-476c-b76b-529600f51c37" />

Pie Chart
The pie chart highlights the relative contribution of different pollutants to India’s overall AQI values. PM10 (33.62%) and PM2.5 (33.28%) together account for nearly two-thirds of the total AQI burden, making particulate matter the dominant factor in poor air quality. In contrast, gaseous pollutants such as Ozone (10.66%), CO (9.77%), NO2 (7.99%), and SO2 (3.38%) contribute smaller shares.

Tree map
The tree map provides a comparative overview of air quality concern levels across Indian states and union territories. Larger and darker blocks represent regions with more severe pollution. States such as Haryana, Delhi, Uttar Pradesh, and Bihar stand out with Very Poor to Severe AQI levels, indicating critical hotspots of particulate and gaseous pollution. In contrast, regions like Gujarat, Telangana, and Kerala show Moderate to Poor levels, reflecting relatively better but still concerning air quality.


Line and Stacked Column Chart
 This visualization compares the average maximum pollutant levels (bars) with the average AQI values (line) across different monitoring boards. The chart reveals that certain boards, such as those in Delhi, Haryana, and Uttar Pradesh, consistently report higher pollutant maxima and elevated AQI values, indicating severe air quality challenges in their jurisdictions. In contrast, boards from regions with relatively cleaner air show lower pollutant averages and correspondingly lower AQI values.

Line Chart 
The line graph shows how Indian cities are distributed across different AQI concern levels. The trend begins with a high number of cities in the “Good” category, then steadily declines as concern levels worsen, reaching the lowest count in the “Severe” category. This indicates that while many cities enjoy relatively clean air, a smaller but significant portion experiences Poor to Severe air quality, posing serious health risks.

Map
The map provides a geospatial overview of air quality levels across India, with markers color-coded by concern categories (Good, Satisfactory, Moderate, Poor, Very Poor, Severe). The majority of markers fall into Poor, Very Poor, and Severe categories, indicating widespread pollution across urban and industrial regions. Cleaner air pockets exist but are limited, with relatively fewer markers in the Good or Satisfactory ranges.

Slice
This slice provides India’s air quality monitoring coverage and overall pollution levels. It shows an average AQI value of 108.98, indicating that air quality across the country generally falls into the Moderate category. The dataset spans 3,194 cities across 30 states and union territories, reflecting extensive monitoring coverage and a broad geographic scope.

Guage 
The dual gauge indicators display the average concentrations of PM10 (253.29) and PM2.5 (252.37) across monitored cities. Both values are significantly elevated, reflecting widespread particulate matter pollution. Since PM2.5 particles are finer and penetrate deeper into the respiratory system, their high levels pose serious health risks, including respiratory and cardiovascular issues.




Interactive Features: 
• Slicers (Concern Level and State and Union Territory) 
• Drill-down capability
 • Clear titles and labels
 • Consolidated layout

Insight

Particulate Dominance: PM10 and PM2.5 together represent ~67% of AQI values, underscoring the urgent need for targeted particulate reduction strategies.
Regional Hotspots: Northern states—particularly Uttar Pradesh, Delhi, Bihar, and Haryana—consistently register Very Poor to Severe AQI levels, making them priority intervention zones.
Monitoring Variability: Data shows uneven pollutant reporting across boards (IMD, APSPCB, JSPCB, etc.), highlighting the need for standardized monitoring protocols to ensure comparability and reliability.
Secondary Risks: Ozone and CO collectively contribute ~20% of AQI values, pointing to risks of photochemical smog and respiratory hazards beyond particulate exposure.
Baseline Concern: The majority of readings fall within Moderate to Poor categories, with “Good AQI” being rare. This indicates that unhealthy air quality is the prevailing baseline across India.
Coverage Gaps: Monitoring stations are concentrated in urban clusters, leaving rural exposures underrepresented. This risks underestimating pollution from biomass burning, dust storms, and agricultural practices.

Descriptive Analysis

The dataset paints a clear picture of India’s air quality crisis—with Delhi and industrial hubs consistently showing hazardous levels of PM2.5 and PM10, while smaller towns remain relatively cleaner. This duality highlights the need for region-specific strategies: stricter emission controls in industrial/urban centers and preventive monitoring in smaller towns.

Diagnostic Analysis

The dataset shows that particulate matter (PM2.5 & PM10) is the single most consistent root cause of poor AQI, with industrial clusters and dense urban centers being the worst affected. Secondary pollutants like Ozone amplify the problem in high-NOx regions like Delhi. Smaller towns remain cleaner largely due to lower industrialization and traffic density.

Prescriptive Insight

Short-term actions: Dust control, stricter vehicle checks, real-time AQI alerts.
Medium-term actions: Industrial emission monitoring, EV adoption, green buffers.
Long-term actions: Renewable energy transition, integrated urban planning, regional collaboration.

Conclusion

The India Air Quality dataset provides a comprehensive view of pollution levels across multiple states, cities, and monitoring stations. By capturing pollutant concentrations (PM2.5, PM10, NO2, SO2, CO, Ozone, NH3) alongside AQI ranges and concern levels, the dataset highlights both regional disparities and pollutant-specific drivers of air quality deterioration.

Key findings show that:
Particulate matter (PM2.5 and PM10) is the dominant contributor to poor and severe AQI, especially in Delhi NCR and industrial hubs such as Raipur, Vatva, and Baddi.
Smaller towns and less industrialized regions generally report “Good” to “Moderate” air quality, though occasional spikes indicate localized or seasonal pollution events.
Secondary pollutants like Ozone exhibit variability, with severe episodes in urban centers driven by photochemical reactions.
Monitoring boards (DPCC, GPCB, HPPCB, etc.) provide localized insights, enabling comparisons across regions and governance structures.
Overall, the dataset underscores the urgent need for region-specific interventions: stricter vehicular and industrial emission controls in urban-industrial clusters, preventive monitoring in smaller towns, and coordinated policy measures across states. It serves as a valuable foundation for diagnostic and prescriptive analytics, enabling stakeholders to design targeted strategies for improving air quality and safeguarding public health.
