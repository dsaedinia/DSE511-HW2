# Data Dictionary

## Dataset Overview

This dataset contains country-level environmental, economic, population, and energy-related indicators for selected South American countries from 1990 to 2024.

* **Observations:** 420
* **Countries:** 12
* **Years:** 1990–2024
* **Variables:** 16

## Selected Variables

| Column                       | Title                                              | Description                                                                                                                      | Unit                                     | Source                                                                                                                                      |
| ---------------------------- | -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `country`                    | Country                                            | Geographic location.                                                                                                             | —                                        | Our World in Data - Regions (2024)                                                                                                          |
| `year`                       | Year                                               | Year of observation.                                                                                                             | —                                        | Our World in Data - Regions (2024)                                                                                                          |
| `population`                 | Population                                         | Population by country, based on data and estimates from different sources.                                                       | people                                   | Population based on various sources (2024)                                                                                                  |
| `co2`                        | Annual CO₂ emissions                               | Annual total emissions of carbon dioxide (CO₂), excluding land-use change.                                                       | million tonnes (Mt)                      | Global Carbon Budget (2025)                                                                                                                 |
| `gdp`                        | Gross domestic product (GDP)                       | Total economic output of a country or region per year, adjusted for inflation and differences in living costs between countries. | international-$ in 2011 prices ($)       | Bolt and van Zanden – Maddison Project Database 2023                                                                                        |
| `co2_per_gdp`                | Annual CO₂ emissions per GDP                       | Annual total CO₂ emissions, excluding land-use change, relative to GDP.                                                          | kilograms per international-$ (kg/$)     | Global Carbon Budget (2025); Maddison Project Database 2023                                                                                 |
| `co2_per_capita`             | CO₂ emissions per capita                           | CO₂ emissions from fossil fuels and industrial processes, excluding land-use change, divided by population.                      | tonnes per person (t/person)             | Global Carbon Budget (2025); Population based on various sources (2024)                                                                     |
| `co2_growth_abs`             | Annual CO₂ emissions growth (abs)                  | Annual growth in total CO₂ emissions, excluding land-use change.                                                                 | million tonnes (Mt)                      | Global Carbon Budget (2025)                                                                                                                 |
| `co2_growth_prct`            | Annual CO₂ emissions growth (%)                    | Annual percentage growth in total CO₂ emissions, excluding land-use change.                                                      | %                                        | Global Carbon Budget (2025)                                                                                                                 |
| `cumulative_co2`             | Cumulative CO₂ emissions                           | Total cumulative CO₂ emissions, excluding land-use change, since the first year of available data.                               | million tonnes (Mt)                      | Global Carbon Budget (2025)                                                                                                                 |
| `land_use_change_co2`        | Annual CO₂ emissions from land-use change          | Annual CO₂ emissions resulting from land-use change.                                                                             | million tonnes (Mt)                      | Global Carbon Budget (2025)                                                                                                                 |
| `cumulative_luc_co2`         | Cumulative CO₂ emissions from land-use change      | Cumulative CO₂ emissions from land-use change since the first year of available data.                                            | million tonnes (Mt)                      | Global Carbon Budget (2025)                                                                                                                 |
| `co2_including_luc`          | Annual CO₂ emissions including land-use change     | Annual total CO₂ emissions including land-use change.                                                                            | million tonnes (Mt)                      | Global Carbon Budget (2025)                                                                                                                 |
| `total_ghg`                  | Annual greenhouse gas emissions including land use | Annual greenhouse gas emissions including land use, measured in CO₂-equivalents over a 100-year timescale.                       | million tonnes (Mt)                      | Jones et al. - National contributions to climate change (2025)                                                                              |
| `primary_energy_consumption` | Primary energy consumption                         | Primary energy consumption.                                                                                                      | terawatt-hours (TWh)                     | U.S. Energy Information Administration (2026); Energy Institute - Statistical Review of World Energy (2025)                                 |
| `energy_per_gdp`             | Primary energy consumption per GDP                 | Primary energy consumption relative to GDP.                                                                                      | kilowatt-hours per international-$ (kWh) | U.S. Energy Information Administration (2026); Energy Institute - Statistical Review of World Energy (2025); Maddison Project Database 2023 |

## Data Sources

* Global Carbon Budget (2025)
* Our World in Data - Regions (2024)
* Population based on various sources (2024)
* Bolt and van Zanden – Maddison Project Database 2023
* U.S. Energy Information Administration - International Energy Data (2026)
* Energy Institute - Statistical Review of World Energy (2025)
* Jones et al. - National contributions to climate change (2025)

## Data Quality Notes

The dataset contains 420 observations. Three selected variables contain missing values:

| Variable         | Missing Values | Percentage |
| ---------------- | -------------: | ---------: |
| `gdp`            |             35 |      8.33% |
| `co2_per_gdp`    |             35 |      8.33% |
| `energy_per_gdp` |             35 |      8.33% |

The dataset contains **no duplicate rows**.

Missing values will be investigated during the exploratory data analysis before any decision is made regarding their treatment.

