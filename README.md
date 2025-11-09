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

## Data Source

The main input dataset used in this workflow is retrieved from [**Facebook Data for Good**](https://dataforgood.facebook.com/), particularly their **Movement Range Maps**.  
These provide aggregated, privacy-preserving origin–destination (OD) metrics that capture mobility trends during both **business-as-usual** and **emergency** conditions.  
Users are encouraged to explore the [Movement Range Data](https://dataforgood.facebook.com/tools/movement-range-maps) portal for methodological notes, coverage, and available time windows.

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



