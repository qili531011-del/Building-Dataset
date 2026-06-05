# Introduction

Building datasets form the foundation of data-driven building energy research, supporting tasks such as energy benchmarking, load forecasting, distributed energy resource planning, and urban-scale energy modeling. As the built environment generates increasingly rich streams of operational and geometric data, curated datasets have become essential for reproducible research and cross-study comparison.

Building datasets can be broadly categorized into three types based on the aspect of building performance they capture:

| Dataset Category | Description |
| --- | --- |
| **[🏗️ Building Footprint Datasets](#building-footprint-datasets)** | Geospatial datasets that capture the physical shape, location, and extent of building structures, typically derived from satellite imagery, LiDAR, or cadastral records. They enable urban morphology analysis, building stock characterization, and spatial energy modeling at city or national scales. |
| **[⚡ Energy Consumption Datasets](#energy-consumption-datasets)** | Time-series datasets recording building-level or sub-meter energy use (electricity, gas, thermal), often at hourly or sub-hourly resolution. They support load profiling, demand forecasting, anomaly detection, and benchmarking across building types and climates. |
| **[☀️ Distributed Energy Resource (DER) Datasets](#distributed-energy-resource-datasets)** | Datasets characterizing on-site generation and storage assets — such as rooftop solar PV, battery systems, and EV chargers — including their capacity, output profiles, and grid interaction patterns. They are critical for studying behind-the-meter flexibility, microgrid design, and grid integration of building-sited renewables. |

# Building Footprint
## 🏗️ Building Footprint Datasets

Building footprint datasets provide geospatial information about the physical outline, location, and geometric attributes of individual building structures. These datasets are typically derived from high-resolution satellite imagery using deep learning-based detection pipelines, and serve as foundational inputs for urban morphology analysis, population estimation, energy demand modeling, and sustainable development monitoring.

| Dataset | Coverage | Scale | Key Features | Source |
| --- | --- | --- | --- | --- |
| **GlobalBuildingAtlas (GBA)** | Global | 2.75B buildings | First open dataset offering complete global building polygons, heights (3m×3m resolution), and LoD1 3D models. ML-based pipeline from PlanetScope satellite data. Height RMSE: 1.5–8.9m across continents. | [Zhu et al., 2025](https://essd.copernicus.org/articles/17/6647/2025/) |
| **Google Open Buildings** | Africa, South & SE Asia, Latin America & Caribbean | 1.8B buildings | Building footprints derived from high-resolution satellite imagery with confidence scores. V3 covers 58M km². Licensed under CC BY-4.0 and ODbL v1.0. | [Google Research](https://sites.research.google/gr/open-buildings/) |
| **Microsoft Global Building Footprints** | Global | 1.4B buildings | Bing Maps imagery (2014–2024) processed with deep learning. Includes 174M building height estimates. Open Data Commons license. | [Microsoft, 2023](https://github.com/microsoft/GlobalMLBuildingFootprints) |
| **OpenBuildingMap** | Global | 2.7B buildings | Comprehensive global footprints with semantic attributes including occupancy type classification. Combines multiple open data sources. | [Nature Scientific Data, 2025](https://www.nature.com/articles/s41597-025-06132-z) |
| **EUBUCCO** | Europe (27+ countries) | 202M buildings | European building stock with individual footprints, heights, and construction year. Harmonized from 50+ open government datasets. | [Milojevic-Dupont et al., 2023](https://www.nature.com/articles/s41597-023-02040-2) |
| **3D-GloBFP** | Global | — | First global 3D building footprint dataset at building-level scale, leveraging Earth Observation data for height estimation. | [ESSD, 2024](https://essd.copernicus.org/articles/16/5357/2024/) |

### Key Observations

- **Coverage progression**: Building footprint datasets have evolved from national/continental scope (e.g., EUBUCCO for Europe) to truly global coverage (GBA, Microsoft, OpenBuildingMap), driven by advances in satellite imagery resolution and ML-based detection.
- **From 2D to 3D**: Recent datasets (GBA, 3D-GloBFP) extend beyond planar footprints to include building heights and volumetric information, enabling more accurate urban energy modeling and carbon emission estimation.
- **Semantic enrichment**: Newer datasets like OpenBuildingMap add functional classification (residential, commercial, industrial), which is critical for building energy use type disaggregation.
- **Energy research relevance**: Building footprint data supports urban building energy modeling (UBEM), district heating/cooling network planning, rooftop solar potential assessment, and building stock turnover analysis.
