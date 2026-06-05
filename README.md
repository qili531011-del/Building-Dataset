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

# ☀️ Distributed Energy Resource (DER) Datasets

Distributed energy resource datasets characterize on-site and near-site renewable generation, storage, and flexible assets — such as rooftop solar PV, building-integrated photovoltaics (BIPV), battery energy storage systems (BESS), and wind turbines. These datasets capture spatial locations, installed capacities, temporal output profiles, and grid interaction patterns, and are critical for behind-the-meter flexibility analysis, microgrid design, urban energy planning, and grid integration studies.

| Dataset | Coverage | Scale | Key Features | Source |
| --- | --- | --- | --- | --- |
| **Global Renewables Watch** | Global | 375,197 wind turbines; 86,410 solar PV installations | Temporal dataset of utility-scale solar PV farms and onshore wind turbines derived from high-resolution satellite imagery using deep learning; includes estimated construction dates and capacity at subnational/national/global levels | [Microsoft/Planet Labs, 2025](https://www.globalrenewableswatch.org/) |
| **Urban Photovoltaics Map** | Global (120+ cities) | City/grid-level | Building-integrated rooftop and facade PV potential and generation estimates; cost-effective deployment pathways for 2030–2050; combines 3D building footprints with spatio-temporal irradiance data | [City-Photovoltaics, 2025](https://city-photovoltaics.com/) |
| **Renewables.ninja** | Global | Country/site-level | Hourly power output simulation for solar PV and wind at any global location; based on NASA MERRA-2 reanalysis; validated against real farm output; ready-made country-level datasets available for download | [Pfenninger & Staffell, 2016](https://www.renewables.ninja/) |
| **US DER Dataset (MIT)** | United States | Project-level (nationwide) | Project-driven dataset integrating rooftop solar PV, home battery storage, and utility-owned DERs into a unified US grid model; supports grid planning and policy analysis | [Zhu et al., 2023 (ACM e-Energy)](https://dl.acm.org/doi/abs/10.1145/3599733.3600250) |
| **Ausgrid Solar Home Electricity** | Australia (Sydney) | 300 residential customers | Half-hourly load and rooftop PV generation data over 3 years; widely used for peer-to-peer energy trading, battery co-location, and self-consumption studies | [Ratnam et al., 2017](https://www.ausgrid.com.au/Industry/Our-Research/Data-to-share/Solar-home-electricity-data) |
| **Harmonised Global Wind & Solar Farm Dataset** | Global | 28,000+ wind & 10,000+ solar farms | First global open-access harmonised spatial dataset of wind and solar installations with capacity and location; enables energy system modeling and land-use analysis | [Dunnett et al., 2020 (Scientific Data)](https://www.nature.com/articles/s41597-020-0469-8) |
| **Open-Source Microgrid Dataset** | United States (single site) | Multi-year, 1-min resolution | Rooftop solar PV, fuel cell, battery storage, and diesel generator output in a real microgrid; all sources individually metered | [Borghini et al., 2021 (J. Renewable Sustainable Energy)](https://pubs.aip.org/aip/jrse/article/13/2/025301/926842) |
| **High-Resolution Rooftop PV Dataset** | Urban (single city) | 3-year, sub-hourly | Open-source dataset for rooftop PV generation analytics with power optimizer-level granularity; supports shading, degradation, and mismatch loss studies | [Nature Scientific Data, 2025](https://www.nature.com/articles/s41597-025-04397-y) |

## Key Observations

- **From potential estimation to operational monitoring**: Early DER datasets focused on static resource assessment (e.g., solar irradiance maps and rooftop area estimates). Recent datasets like Global Renewables Watch and the Urban Photovoltaics Map bridge this gap by combining satellite-detected installations with temporal generation profiles, enabling dynamic tracking of DER deployment and performance.
- **Satellite imagery as a scalable sensing layer**: Deep learning applied to high-resolution satellite imagery (Global Renewables Watch) now enables automated, repeatable detection and dating of renewable installations at global scale — a paradigm shift from manual surveys and registry-based approaches that suffer from incompleteness and reporting lags.
- **Simulation-based datasets filling data scarcity**: Tools like Renewables.ninja provide validated hourly generation time series for any global location without requiring metered data access, making them indispensable for energy system modeling in data-scarce regions. However, they rely on reanalysis weather data and generic system assumptions, introducing biases at the individual-building level.
- **Building-integrated PV gaining attention**: The Urban Photovoltaics Map highlights that facade PV potential averages ~68% of rooftop potential, with some cities exceeding rooftop values — underscoring the need for 3D building data (linking back to footprint datasets) to unlock the full BIPV resource.
- **Integration with grid models**: Project-level DER datasets (MIT US DER Dataset) that are co-registered with grid topology enable power flow analysis, hosting capacity studies, and distribution system planning — moving beyond isolated asset-level data toward system-level DER integration research.
