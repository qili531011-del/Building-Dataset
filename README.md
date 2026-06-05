# Introduction

Building datasets form the foundation of data-driven building energy research, supporting tasks such as energy benchmarking, load forecasting, distributed energy resource planning, and urban-scale energy modeling. As the built environment generates increasingly rich streams of operational and geometric data, curated datasets have become essential for reproducible research and cross-study comparison.

Building datasets can be broadly categorized into three types based on the aspect of building performance they capture:

| Dataset Category | Description |
| --- | --- |
| **[🏗️ Building Footprint Datasets](#building-footprint-datasets)** | Geospatial datasets that capture the physical shape, location, and extent of building structures, typically derived from satellite imagery, LiDAR, or cadastral records. They enable urban morphology analysis, building stock characterization, and spatial energy modeling at city or national scales. |
| **[⚡ Energy Consumption Datasets](#energy-consumption-datasets)** | Time-series datasets recording building-level or sub-meter energy use (electricity, gas, thermal), often at hourly or sub-hourly resolution. They support load profiling, demand forecasting, anomaly detection, and benchmarking across building types and climates. |
| **[☀️ Distributed Energy Resource (DER) Datasets](#distributed-energy-resource-datasets)** | Datasets characterizing on-site generation and storage assets — such as rooftop solar PV, battery systems, and EV chargers — including their capacity, output profiles, and grid interaction patterns. They are critical for studying behind-the-meter flexibility, microgrid design, and grid integration of building-sited renewables. |

# 🏗️ Building Footprint Datasets

Building footprint datasets provide geospatial information about the physical outline, location, and geometric attributes of individual building structures. These datasets are typically derived from high-resolution satellite imagery using deep learning-based detection pipelines, and serve as foundational inputs for urban morphology analysis, population estimation, energy demand modeling, and sustainable development monitoring.

| Dataset | Coverage | Scale | Key Features | Source |
| --- | --- | --- | --- | --- |
| **GlobalBuildingAtlas (GBA)** | Global | 2.75B buildings | First open dataset offering complete global building polygons, heights (3m×3m resolution), and LoD1 3D models. ML-based pipeline from PlanetScope satellite data. Height RMSE: 1.5–8.9m across continents. | [Zhu et al., 2025](https://essd.copernicus.org/articles/17/6647/2025/) |
| **Google Open Buildings** | Africa, South & SE Asia, Latin America & Caribbean | 1.8B buildings | Building footprints derived from high-resolution satellite imagery with confidence scores. V3 covers 58M km². Licensed under CC BY-4.0 and ODbL v1.0. | [Google Research](https://sites.research.google/gr/open-buildings/) |
| **Microsoft Global Building Footprints** | Global | 1.4B buildings | Bing Maps imagery (2014–2024) processed with deep learning. Includes 174M building height estimates. Open Data Commons license. | [Microsoft, 2023](https://github.com/microsoft/GlobalMLBuildingFootprints) |
| **OpenBuildingMap** | Global | 2.7B buildings | Comprehensive global footprints with semantic attributes including occupancy type classification. Combines multiple open data sources. | [Nature Scientific Data, 2025](https://www.nature.com/articles/s41597-025-06132-z) |
| **EUBUCCO** | Europe (27+ countries) | 202M buildings | European building stock with individual footprints, heights, and construction year. Harmonized from 50+ open government datasets. | [Milojevic-Dupont et al., 2023](https://www.nature.com/articles/s41597-023-02040-2) |
| **3D-GloBFP** | Global | — | First global 3D building footprint dataset at building-level scale, leveraging Earth Observation data for height estimation. | [ESSD, 2024](https://essd.copernicus.org/articles/16/5357/2024/) |

## Key Observations

- **Coverage progression**: Building footprint datasets have evolved from national/continental scope (e.g., EUBUCCO for Europe) to truly global coverage (GBA, Microsoft, OpenBuildingMap), driven by advances in satellite imagery resolution and ML-based detection.
- **From 2D to 3D**: Recent datasets (GBA, 3D-GloBFP) extend beyond planar footprints to include building heights and volumetric information, enabling more accurate urban energy modeling and carbon emission estimation.
- **Semantic enrichment**: Newer datasets like OpenBuildingMap add functional classification (residential, commercial, industrial), which is critical for building energy use type disaggregation.
- **Energy research relevance**: Building footprint data supports urban building energy modeling (UBEM), district heating/cooling network planning, rooftop solar potential assessment, and building stock turnover analysis.

# ⚡ Energy Consumption Datasets

Energy consumption datasets record building-level or aggregated energy use (electricity, gas, thermal) over time, typically at hourly or sub-hourly resolution. These datasets are essential for load profiling, demand forecasting, energy benchmarking, anomaly detection, demand response research, and validating building energy models across diverse climates and building types.

| Dataset | Coverage | Scale | Key Features | Source |
| --- | --- | --- | --- | --- |
| **Demand.ninja** | Global (40+ countries) | National/regional/building-level | Customisable model for hourly heating and cooling demand; validated against thousands of buildings across 4 continents; provides temperature, BAIT, HDD/CDD data (1980–2022); open-source code in R and Python | [Staffell et al., 2023 (Nature Energy)](https://www.demand.ninja/) |
| **ecobee Donate Your Data** | North America | 200,000+ homes | Anonymized smart thermostat data (indoor/outdoor temperature, HVAC runtime, occupancy) from real residential buildings; supports energy use pattern analysis, public health, and climate adaptation research | [ecobee Research](https://www.ecobee.com/en-us/donate-your-data/) |
| **BuildingsBench (NREL)** | United States | 900K buildings | Large-scale synthetic energy consumption time series derived from NREL End-Use Load Profiles (EULP); designed as benchmark for short-term load forecasting models | [Emami et al., 2024 (OEDI)](https://data.openei.org/submissions/5859) |
| **NREL End-Use Load Profiles (EULP)** | United States | 550K+ residential & commercial | Hourly/sub-hourly end-use load profiles covering all US climate zones and building types; calibrated with AMI data; enables sector-level demand analysis | [NREL, 2022](https://www.nrel.gov/buildings/end-use-load-profiles.html) |
| **BDG2 (Building Data Genome 2)** | Global (19 sites) | 3,053 meters from 1,636 buildings | Two years of whole-building hourly electricity, heating, and cooling meter data; widely used benchmark for load prediction and anomaly detection | [Miller et al., 2020 (Scientific Data)](https://www.nature.com/articles/s41597-020-00712-6) |
| **ASHRAE Great Energy Predictor III** | Global | 2,380 meters from 1,448 buildings | One year of hourly meter data (electricity, chilled water, steam, hot water) with weather; Kaggle competition dataset for energy prediction | [ASHRAE/Kaggle, 2019](https://www.kaggle.com/c/ashrae-energy-prediction) |
| **Benchmark Datasets for Buildings (BDB)** | United States | Handful of high-resolution buildings | Multi-year, high-resolution (sub-hourly) building system data from 4 national labs; includes HVAC subsystem, lighting, and plug loads | [DOE/NREL, 2022](https://bbd.labworks.org/) |
| **Pecan Street Dataport** | United States (Austin, TX & others) | 1,000+ homes | Sub-minute circuit-level electricity data with solar PV, EV charging, and appliance disaggregation; supports NILM and demand-side management research | [Pecan Street Inc.](https://www.pecanstreet.org/dataport/) |

## Key Observations

- **From simulation to real-world**: The field has progressed from relying heavily on physics-based simulation outputs (e.g., EnergyPlus reference buildings) to large-scale real metered data (ecobee, Pecan Street) and hybrid synthetic-real datasets (BuildingsBench calibrated with AMI), improving the ecological validity of data-driven models.
- **Temporal resolution diversification**: Datasets now span from hourly aggregates (BDG2, ASHRAE) to sub-minute circuit-level measurements (Pecan Street), enabling research across scales — from seasonal demand forecasting to real-time NILM and fault detection.
- **Climate and typology coverage**: Global datasets like Demand.ninja and BDG2 enable cross-climate generalization studies, while US-centric datasets (EULP, BuildingsBench) offer unmatched depth in building type and end-use disaggregation within a single regulatory framework.
- **Privacy-preserving data sharing**: Crowdsourced programs (ecobee Donate Your Data) demonstrate a scalable model for acquiring large residential datasets while maintaining occupant anonymity, addressing the long-standing barrier of data access in the residential sector.
- **Benchmarking standardization**: Purpose-built benchmark datasets (BuildingsBench, ASHRAE GEPIII) provide standardized train/test splits and evaluation protocols, enabling fair comparison of forecasting algorithms — a practice the building energy community increasingly adopts from the ML research paradigm.
