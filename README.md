# E-commerce Delivery Fleet Deployment (Brazil) — Olist

This project diagnoses the delivery bottlenecks, quantifying cost drivers, and operationalizing a deployment playbook for Brazil-wide e-commerce logistics. 
The analysis focuses on high-value lanes (São Paulo, Rio de Janeiro, Minas Gerais), standardizes packaging to improve cube utilization, and implements forecast- and fuel-indexed operations to reduce late deliveries and margin erosion.

## Project Goals
- Reduce late deliveries by targeting the dominant fulfillment bottlenecks and implementing distance- and package-aware dispatch rules.
- Concentrate capacity and routing on Brazil’s highest-value states while protecting margins against fuel volatility.
- Standardize box sizes to cover >95% of shipments and improve vehicle fill, fuel efficiency, and handling time.
- Produce a 6-month demand forecast with surge overlays to staff and route for Black Friday and Carnival peaks.

## Key Outcomes
- Identified outbound as the primary bottleneck: late orders averaged 14 days outbound vs 5 days on time; baseline late rate: 6.23%.
- Prioritized São Paulo (SP), Rio de Janeiro (RJ), and Minas Gerais (MG) (~60% of freight value) for fleet focus; linked freight value with diesel/gasoline trends to define surcharge triggers.
- Verified top duration drivers using ML: buyer–seller distance, product volume, and weight; linked late deliveries to higher 1-star review rates (~35%).
- Proposed three standardized box sizes covering >95% of shipment dimensions to improve cube utilization and lower cost-to-serve.
- Forecasted monthly orders in a ~4,750–5,750 band with holiday spikes annotated for capacity planning.

## Dataset
- Source: Olist Brazilian E-commerce public dataset (orders, customers, sellers, products, items, reviews, geolocation, payments).
- Temporal coverage: 2017–2018; filtered to delivered orders for accurate duration and cost metrics.
- Granularity: Order-level with item, product dimensions (H/W/L/volume), payment/freight values, timestamps, and review scores.

## Methods
- **Exploratory Analysis:** Geospatial freight mapping, delivery class segmentation, and review sentiment analysis.
- **Statistical Modeling:** Random Forest for feature importance on delivery duration; linear regressions with rolling averages for distance, volume, and weight relationships.
- **Forecasting:** Time-series 6-month demand forecast with event annotations (Black Friday, Carnival) and weekday/weekend checks.
- **Packaging Optimization:** Dimension clustering and overlap histograms to propose a minimal box family covering >95% of SKUs.

## Tech Stack
- **Data & EDA:** Python (pandas, NumPy), Tableau for visual dashboards and geospatial/time-series mapping.
- **Modeling:** Random Forest, linear regression, distance bucketing, and rolling aggregation for robust feature analysis.
