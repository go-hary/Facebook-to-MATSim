# Facebook-to-MATSim

This repository provides an open workflow to **generate a synthetic population and travel demand** from aggregated **Facebook/Meta Movement Range data** and export it into a **MATSim-ready scenario**.  
It accompanies the publication:

> **Using Social Media Data to Construct an Agent-Based Model in a Data-Scarce Environment: A Case Study of Alexandria, Egypt**  
> *Mohamed Elgohary, Corneel Casier, Paola Pucci, and Frank Witlox*  
> *Journal of Urban Technology* (2025)  
> DOI: [https://doi.org/10.1080/10630732.2025.2546785](https://www.tandfonline.com/doi/full/10.1080/10630732.2025.2546785)

---

## Overview

The workflow demonstrates how **social-media mobility data** can be translated into **agent-based mobility simulations**, especially for **data-scarce cities**.  
The Jupyter notebook (`MATSim_Syn_pop_genrator.ipynb`) performs the following steps:

1. **Import aggregated OD flows** (e.g., from Facebook’s Data for Good program).  
2. **Disaggregate flows spatially** into origin–destination points using quadkeys or tile geometries.  
3. **Assign departure times** within a selected period.  
4. **Estimate travel modes** using distance-based heuristics or multinomial logit probabilities.  
5. **Label activities** (home–work, education, other).  
6. **Export** a full **MATSim-compatible scenario** (population, network, config, vehicles, PT schedule).

---

##  Data Sources

### 1. [Facebook Data for Good](https://dataforgood.facebook.com/)

The main input dataset for population movement is retrieved from **Facebook’s Data for Good** initiative, specifically the **Movement Range Maps**.  
These provide aggregated and privacy-preserving origin–destination (OD) metrics derived from anonymized user mobility patterns.  
They describe travel flows under both **baseline** and **n_crisis** conditions and allow researchers to infer city-wide travel behavior where official data is limited.  
You can explore and download the dataset and related documentation here:  
https://dataforgood.facebook.com/dfg/tools/movement-maps
---

### 2. [OpenStreetMap + JOSM-MATSim Plugin](https://github.com/matsim-org/josm-matsim-plugin)

The street network used for routing and simulation was built from **OpenStreetMap (OSM)** data.  
The data was processed using the **[JOSM-MATSim Plugin](https://github.com/matsim-org/josm-matsim-plugin)** — an official extension for the JOSM editor that converts OSM geometries (nodes and ways) into MATSim-compatible network files (`network.xml`).  
The plugin enables:
- Importing and visualizing OSM data directly in JOSM.  
- Assigning transport modes, capacities, and speeds to OSM links.  
- Exporting the processed data as a valid **MATSim network** (nodes, links, and optionally public transport facilities).

In this project, the MATSim network derived from OpenStreetMap was **enriched with OD flows** from the Facebook dataset to create a data-driven scenario for Alexandria.

Users are encouraged to explore the [Movement Range Data]([[https://dataforgood.facebook.com/tools/movement-range-maps](https://dataforgood.facebook.com/dfg/tools/movement-distribution-maps)](https://dataforgood.facebook.com/dfg/tools/movement-distribution-maps)) portal for methodological notes, coverage, and available time windows.

## Repository structure

- **`data/`**  
  - `0.config.xml` — MATSim configuration file  
  - `population.xml` — Synthetic population plans  
  - `transitVehicles.xml` — Public transport vehicles  
  - `transitSchedule.xml` — Transit schedule (GTFS-based)  
  - `scenario/` — Generated MATSim scenario folder  

- **`MATSim_Syn_pop_genrator.ipynb`** — Main Jupyter notebook that converts [Facebook Data for Good](https://dataforgood.facebook.com/) OD data to MATSim inputs  
- **`LICENSE`** — MIT license  
- **`README.md`** — Project documentation

---

## Citation

If you use this repo, kindly cite us. 

@article{Elgohary2025FacebookMATSim,
  title   = {Using Social Media Data to Construct an Agent-Based Model in a Data-Scarce Environment: A Case Study of Alexandria, Egypt},
  author  = {Elgohary, Mohamed and Casier, Corneel and Pucci, Paola and Witlox, Frank},
  journal = {Journal of Urban Technology},
  year    = {2025},
  volume  = {32},
  number  = {8},
  pages   = {1--24},
  doi     = {10.1080/10630732.2025.2546785},
  url     = {https://doi.org/10.1080/10630732.2025.2546785

---



