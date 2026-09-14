# Collaborative Data Wrangling & EDA

## Project Title

Homework #2: Collaborative Data Wrangling & EDA
DSE 511 – Fall 2026

## Collaborators

- Daniel Saedi Nia

- Mahbuba Jyoti

## Project Structure

```text
south-america-co2-eda/
├── README.md
├── LICENSE
├── requirements.txt
├── data
│   ├── processed      <- The final dataset.
│   └── raw            <- The original.
├── notebooks/
│   └── 01-data_parse.ipynb
│   └── 02-south-america-co2-eda_Viz.ipynb
├── references/
│   └── data_dictionary.md
└── reports/
    └── figures/
```

## Data Source

- Sources:

  - **CO2 and Greenhouse Gas Emissions, Our World in Data (OWID)** (<https://ourworldindata.org/co2-and-greenhouse-gas-emissions>) - underlying data from Global Carbon Budget (2025); Population based on various sources; Bolt and van Zanden – Maddison Project Database 2023. Accessed 09/07/2026. Annual CO2 Emissions and related variables (e,g,. per capita, growth rate, land-use change) for years 1870-2022. Annual CO2 is expressed in million tonnes (Mt). Licesed under Creative Commons BY (CC-BY 4.0). Size: 13.7 MB

  - **Gross Domestic Product, Our World in Data (OWID)** (<https://ourworldindata.org/grapher/gdp-worldbank>) - underlying data from Eurostat, OECD, IMF, and World Bank (2026) with minor processing by OWID. Accessed 09/10/2026. Annual purchasing power parity (PPP) adjusted GDP data from 1990-2025. GDP is expressed in international-$ in 2021 prices. Licesed under Creative Commons BY (CC-BY 4.0). Size: 241 KB

## Methods

### Data Cleaning (Daniel Saedi Nia)

- Sourced CO2 and GDP datasets through reproducible methods in data parse notebook.

- Filtered OWID's raw CO2 dataset down to South American countries and limit scope of analysis

- Reduced cols down to usable and relevant metrics when it comes to comparisons of GDP and CO2 emissions

- Filtered dataset to years 1990 - 2024 due to limitation in dataset from missing data

- Missing GDP values replaced for Guyana and Suriname (missing for all years making filling difficult). Both countries had data from World Bank dataset.

- Replaced GDP entirely for all coiuntries in the South American CO2 dataset for consistency, as World Bank GDP PPP data is expressed in international-$ in 2021 prices, while the original dataset was based in 2011

- Recomputed cols/variables dependent on GDP with necessary unit conversions like `co2_per_gdp` (converting co2 from million tonnes to kilograms)

- Validated the merge and checked for duplicates. Checked values against source pages to ensure correct merge and checked for errors in data.

- Tools/libraries used: Pandas, numpy

### Exploratory Data Analysis (Mahbuba Jyoti)

```text
1. Dataset Overview
2. Data Quality Check
   ├── Missing values
   ├── Duplicate observations
   └── Country/year coverage

3. Univariate Analysis
   ├── CO₂ emissions
   ├── CO₂ per capita
   ├── GDP
   └── Primary energy consumption

4. Country Comparisons
   ├── Total CO₂ by country
   └── CO₂ per capita by country

5. Temporal Analysis
   └── CO₂ trends, 1990–2024

6. Bivariate Analysis
   ├── GDP vs CO₂
   ├── Population vs CO₂
   └── Energy consumption vs CO₂

7. Correlation Analysis

8. Key Findings
```

## Results

## Key Findings from EDA

> **Key Summary:** South American $\text{CO}_2$ emissions are heavily right-skewed and concentrated in large economies like Brazil, showing near-perfect coupling with GDP ($r = 0.993$), primary energy use ($r = 0.990$), and population ($r = 0.939$). However, per-capita emissions follow a completely different pattern—led by smaller nations like Venezuela and Suriname—while a total absence of Venezuelan GDP data from 1990 to 2024 presents a major regional analytical constraint.
> 
The key findings from the exploratory data analysis (EDA) of South American $\text{CO}_2$ emissions are summarized below:

### 1. Large Differences in Total $\text{CO}_2$ Emissions Across Countries

The analysis shows substantial differences in total $\text{CO}_2$ emissions among South American countries. Brazil has the highest average annual $\text{CO}_2$ emissions, at approximately 391.59 Mt, followed by Argentina (160.16 Mt) and Venezuela (138.22 Mt). In contrast, Guyana and Suriname have considerably lower total emissions. This indicates that total regional $\text{CO}_2$ emissions are concentrated among a relatively small number of countries with larger populations and greater levels of economic and energy activity.

![Total CO2 Emissions Trend](./reports/figures/total_co2_emissions_trend.png)

***

### 2. Total $\text{CO}_2$ Emissions and $\text{CO}_2$ per Capita Show Different Patterns

Brazil has the highest total $\text{CO}_2$ emissions, but it does not have the highest average $\text{CO}_2$ emissions per capita. Venezuela and Suriname have the highest average $\text{CO}_2$ emissions per capita, at approximately 5.26 and 4.34 tonnes per person, respectively. This demonstrates that total emissions and per-capita emissions capture different aspects of environmental impact. A country with a smaller population can have relatively low total emissions while still having high emissions per person.

![Average CO2 Emissions per Capita by Country](./reports/figures/avg_co2_per_capita_by_country.png)

***

### 3. $\text{CO}_2$ Emissions Are Strongly Right-Skewed

The distribution of annual $\text{CO}_2$ emissions is strongly right-skewed. Most country-year observations have relatively low emissions, with many observations below approximately 100 Mt, while a smaller number of observations have substantially higher emissions, including values above 500 Mt. This indicates considerable variation in emissions across countries and years. Because of this skewed distribution, the median can provide a useful representation of a typical observation in addition to the mean.

![Distribution of Annual CO2 Emissions](./reports/figures/distribution_annual_co2_emissions.png)

***

### 4. GDP, Population, Energy Consumption, and $\text{CO}_2$ Are Strongly Associated

The correlation analysis reveals very strong positive relationships among population, economic activity, energy consumption, and total $\text{CO}_2$ emissions. Some of the strongest correlations are:

| Relationship | Correlation (r) |
| :--- | :--- |
| **GDP and $\text{CO}_2$** | 0.993 |
| **GDP and Primary Energy Consumption** | 0.997 |
| **$\text{CO}_2$ and Primary Energy Consumption** | 0.990 |
| **Population and $\text{CO}_2$** | 0.939 |
| **Population and GDP** | 0.976 |

These results indicate that observations with larger populations, higher GDP, and greater primary energy consumption tend to have higher total $\text{CO}_2$ emissions. However, these correlations represent associations and do not establish causal relationships.

![GDP vs CO2 Emissions](./reports/figures/gdp_vs_co2_emissions.png)

***

### 5. Per-Capita Measures Provide a Different Perspective

Although total $\text{CO}_2$ emissions are strongly associated with GDP and population, $\text{CO}_2$ per capita has a much weaker relationship with these variables. The correlation between $\text{CO}_2$ per capita and GDP is only 0.056, while its correlation with population is −0.066. This contrast shows that analyzing only total emissions can hide important differences in emissions intensity at the individual level. Therefore, both total and per-capita measures are important for understanding emissions patterns.

![Distribution of CO2 Emissions per Capita](./reports/figures/distribution_co2_per_capita.png)

***

### 6. Emissions Intensity Is Related to Energy Intensity

The correlation between $\text{CO}_2$ per GDP and energy per GDP is 0.708, indicating a relatively strong positive association between emissions intensity and energy intensity. This suggests that observations with higher energy use relative to GDP also tend to have higher $\text{CO}_2$ emissions relative to GDP. Measures of emissions and energy intensity therefore provide additional information beyond total emissions.

![Energy Consumption vs CO2 Emissions](./reports/figures/energy_consumption_vs_co2_emissions.png)

***

### 7. Missing GDP Data for Venezuela Is an Important Limitation

A significant data-quality limitation is the absence of GDP-related information for Venezuela across the 1990–2024 period. The variables `gdp`, `co2_per_gdp`, and `energy_per_gdp` contain missing values for Venezuela. Consequently, analyses involving these economic indicators may not fully represent all countries in the dataset. This limitation should be considered when interpreting GDP-related comparisons and correlations.

### 4. Important Data Quality Limitation: Venezuela GDP

A critical finding is the complete absence of GDP data (`gdp`), carbon intensity (`co2_per_gdp`), and energy intensity (`energy_per_gdp`) for **Venezuela across the entire study period (1990–2024)**. All analyses linking economic performance to environmental impact for the region are constrained by this missing data.

## Collaboration Notes

- Daniel Saedi Nia contributions: Repo setup, as well as data aquisition and cleaning. GDP source replacement and dataset validation.  

- Mahbuba Jyoti contributions:  Conducted the initial data overview, performed data preprocessing and organization, conducted exploratory data analysis (EDA), and contributed to documentation.

- Both: Collaborated on the project, discussed the analysis and Git workflow, reviewed each other's work, and worked together on the merge conflict resolution.

## Reproducibility Instructions

1. Clone the repository

2. Navigate to project directory

3. If using uv as your package manager, run the following command to install the dependencies:

```bash
uv sync
```

Otherwise, if you are using pip, you can install the dependencies by running:

```bash
pip install .
```

or

```bash
pip install -r requirements.txt
```

4.Run the notebooks located in the notebook folder in the following order.

- `data_parse.ipynb` for data aquisition and cleaning

- `south_america_co2_eda_Viz.ipynb` or `south_america_co2_eda_Viz.py` for EDA

## Merge Conflict Reflection

We first created a branch called `merge-conflict-branch`, then switched back to the main branch and edited the header line for the Merge Conflict Reflection section in the README and pushed our changes. Now that the newly created branch is 1 commit behind we explicitly do not pull or merge from main. We then edit that same line and also add to our merge conflict reflection. Upon pushes all our changes we initiated a pull request and encountered the merge conflict error "This branch has conflicts that must be resolved". When attempting to resolve we were met with three general options to accept the current change, incoming change, or merge both together. We opted to accept the current change as that had more information in the README filled out. With the conflict resolved, we merged the pull request.
