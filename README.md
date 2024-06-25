
# Floodrisk Hazard Modeling

This repository contains the following files for flood risk hazard modeling:

- `EstimateVulnerability.ipynb`: Contains the code to transform tabular data to estimate vulnerability indexes.
- `FloodHazardModelClean.ipynb`: Script to create a raster hazard flood model based on elevation, slope, and precipitation data.
- `FloodRiskModel.ipynb`: Code to create a composite flood risk model based on raster and vector information.

## Overview

This project aims to model flood risk hazards by combining vulnerability estimates due to infrastructure, sensitivity to water, and social and demographic issues. The flood hazard model is created based on elevation, slope, and precipitation data, and a composite flood risk model was developed using the following equation:

\[ FloodRisk = Hazard x Vulnerability ]


