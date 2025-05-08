# 🌊 Flood Risk Hazard Modeling

This repository implements a machine learning-based flood risk mapping framework using **GARP (Genetic Algorithm Rule-set Production)**, inspired by the study _Hazard and vulnerability in urban flood risk mapping_ (Eini et al., 2020). The project integrates environmental factors and urban vulnerability indicators to generate flood hazard, vulnerability, and composite risk maps.

This particular implementation was conducted for **New York City (NYC)**.

## 🗂️ Data Sources

To replicate or extend this work in NYC, you can use the following publicly available datasets:

- **NYC Census Data**: [Census Download and Metadata](https://www.nyc.gov/site/planning/data-maps/open-data/census-download-metadata.page)
- **NASA GPM Precipitation Data**: [Giovanni - NASA GPM](https://gpm.nasa.gov/data/sources/giovannie)
- **NYC Population FactFinder**: [Population Explorer](https://popfactfinder.planning.nyc.gov/explorer/selection/9616098ee87fcc69b264c2cf3c0)
- **NYC Zoning and Land Use Map (ZoLa)**: [ZoLa Map](https://zola.planning.nyc.gov/about?layer-groups=%5B%22building-footprints%22%2C%22commercial-overlays%22%2C%22street-centerlines%22%2C%22subway%22%2C%22zoning-districts%22%5D&selectedOverlays=%5B%5D#9.72/40.7669/-73.8292)
- **CoreData by NYU Furman Center**: [CoreData NYC](https://app.coredata.nyc/?mlb=true&ntii=hh)
- **Digital Elevation Model (1-foot DEM)**: [NYC Open Data - DEM](https://data.cityofnewyork.us/City-Government/1-foot-Digital-Elevation-Model-DEM-/dpc8-z3jc/about)

## 🧭 Objective

To produce a spatial flood risk map by modeling:
- Flood **hazard** using GARP and environmental variables.
- Urban **vulnerability** based on infrastructure, socio-demographics, and exposure.
- **Flood risk** as the combination of hazard × vulnerability.

---

## 📁 Repository Structure

| File | Description |
|------|-------------|
| `EstimateVulnerability.ipynb` | Computes infrastructure, social, and economic transform tabular data to estimate vulnerability indexes.  |
| `FloodHazardModelClean.ipynb` | Applies GARP-based modeling using flood occurrence data and conditioning factors (e.g., slope, DEM, rainfall). |
| `FloodRiskModelClean.ipynb` | Multiplies the hazard and vulnerability layers to produce the final flood risk map. |

---

## 🔍 Methodology

### Flood Risk Equation

```math
Flood Risk = Flood Hazard × Vulnerability
```

- **Hazard Model (GARP)**  
  Environmental predictors used:
  - Elevation  
  - Slope  
  - Land use  
  - Curve number  
  - Distance to rivers  
  - Distance to channels  
  - Precipitation

- **Vulnerability Estimation**  
  Based on three dimensions:
  - Economic (building quality, density, urban texture)
  - Social (age, education, income, household structure)
  - Infrastructure (access to roads, hospitals, fire stations, schools)


---

## 📊 Results

The model outputs:
- Raster flood hazard zones
- Vulnerability indices per urban neighborhood
- Combined flood risk classifications (Very Low to Very High)



---

## ⚙️ Dependencies

You will need the following Python packages:

```bash
pip install numpy pandas geopandas rasterio scikit-learn matplotlib seaborn
```

---

## ▶️ Usage

1. **Clone the repo:**

```bash
git clone https://github.com/tarunluthra/floodrisk-hazard-modeling.git
cd floodrisk-hazard-modeling
```

2. **Launch Jupyter and run notebooks in order:**
   - `EstimateVulnerability.ipynb`
   - `FloodHazardModelClean.ipynb`
   - `FloodRiskModelClean.ipynb`

---

## 🗂️ Data Requirements

This repo assumes availability of:
- DEM (Digital Elevation Model)
- Rainfall raster
- Land use classification
- Vector layers: infrastructure (roads, hospitals, etc.), neighborhoods
- Flood occurrence points (for training GARP)

> Data is not bundled in this repository due to size or licensing restrictions. Replace data layers with your region-specific datasets.

---

## 📚 Reference

Eini, M., Kaboli, H.S., Rashidian, M., & Hedayat, H. (2020).  
_Hazard and vulnerability in urban flood risk mapping: Machine learning techniques and considering the role of urban districts_,  
International Journal of Disaster Risk Reduction, 50, 101687.  
[DOI: 10.1016/j.ijdrr.2020.101687](https://doi.org/10.1016/j.ijdrr.2020.101687)

---

## 📬 Contact

For questions or collaboration inquiries, please reach out via [GitHub](https://github.com/tarunluthra).

---







