# California Sustainability Groundwater Management Act Analysis

### About

In 2014, California passed the Sustainable Groundwater Management Act (SGMA) aimed at addressing the over-exploitation of groundwater across California (Water Education Foundation, n.d.). The need for groundwater regulation was made urgent by the severe California drought of 2012-2016. This act required local and regional agencies to develop and implement sustainable groundwater management plans. High and medium-priority basins in critical overdraft were required to submit and begin implementing management plans by January 2020, while the rest had until January 2022 (Water Education Foundation, n.d.).

This analysis uses a segmented regression model to evaluate whether groundwater level trends changed significantly from January 2012 through November 2025 for monitoring wells across California operated by the California Department of Water Resources. The associated breakpoint estimate from this model will hint at whether it was due to the SGMA implementation of 2020 or something else.

### Hypothesis

**Null Hypothesis (H₀):** The slope of groundwater levels over time does not change before and after a breakpoint.

$$H_0: \beta_2 = 0$$

**Alternative Hypothesis (Hₐ):** The slope of groundwater levels over time changes before and after a breakpoint.

$$H_a: \beta_2 \neq 0$$

$\beta_2$ represents the change in slope after the breakpoint. If $H_0$ is true, a single linear trend describes the entire time series. If $H_a$ is true, two different slopes are needed.

### Data limitation

The groundwater level data used in this analysis exhibits several features that affect the statistical analysis:

Seasonality: Groundwater levels fluctuate seasonally, increasing during wet seasons and decreasing during dry periods. This could make it difficult to distinguish seasonal groundwater water depletion from over drafting.

Autocorrelation not addressed: This analysis does not account for autocorrelation in the regression model. Groundwater levels depend on previous levels. This creates autocorrelation for our response variables. Therefore, groundwater level observations cannot be considered independent. This can affect the reliability of standard errors and significance tests.

Policy Intervention Variation: Not all wells were subject to the January 2020 SGMA Sustainable Groundwater Plan submission and implementation. Some wells had until January 2022 to start implementing their plan. Despite this, a single policy intervention date (January 2020) was used in order to make a single breakpoint for groundwater level observations over time.

### DAG
This directed acyclic graph (DAG) visualizes the different causal relationships influencing groundwater levels. 

![Directed Acyclic Graph](dag.png)

1. **Seasonality → Precipitation:** Season influences when California experiences different precipitation intensities - which replenish groundwater (i.e. wet winters vs. dry summers).

2. **Seasonality → Groundwater Level:** Seasonal cycles directly affect groundwater levels due to different seasons having different evapotranspiration and precipitation patterns. 

3. **Precipitation → Groundwater Level:** Rainfall and snowmelt are the primary contributors to groundwater recharge.

4. **Time → SGMA Implementation:** The policy was implemented at a specific point 
   in time (January 2020 for priority basins).

5. **SGMA Implementation → Groundwater Level:** This policy directly impacted groundwater pumping, withdrawal restrictions and recharge projects. Therefore it is expected to affect groundwater levels.

### Repository Structure
```
├── Cal_SGMA_files
├── Cal_SGMA.html
├── Cal_SGMA.qmd
├── Cal_SGMA.Rproj
├── dag.png
├── data
│   ├── 03967113-1556-4100-af2c-b16a4d41b9d0.csv
│   └── 16f256f8-35a4-4cab-ae02-399a2914c282.csv
├── LICENSE
└── README.md

```
### Folder Descriptions: 

/data:
* 03967113-1556-4100-af2c-b16a4d41b9d0.csv: California Department of Water Resources groundwater station metadata
   
    Data can be accessed [here](https://data.cnra.ca.gov/dataset/continuous-groundwater-level-measurements/resource/03967113-1556-4100-af2c-b16a4d41b9d0)
* 16f256f8-35a4-4cab-ae02-399a2914c282.csv: California Department of Water Resources groundwater continuous monthly average per station.
   
    Data can be accessed [here](https://data.cnra.ca.gov/dataset/continuous-groundwater-level-measurements/resource/16f256f8-35a4-4cab-ae02-399a2914c282)

/Cal_SGMA.Rproj

* R project space for analysis

/Cal_SGMA_files
* Supporting files needed for the HTML document to work properly

/Cal_SGMA.html
* Output pdf with code and figures

/Cal_SGMA.qmd
* Quarto document containing code and scripts for analysis

### Author: [Richard Montes Lemus](richardmonteslemus.github.io)

### Acknowledgement: Bren School Master of Environmental Data Science EDS 222 final project coursework materials

### Language: R 

| Citation |
|---------------------|
| California Department of Water Resources. (November 1, 2025). Continuous Groundwater Level Measurements. California Natural Resources Agency Open Data Portal. Retrieved December 4, 2024, from https://data.cnra.ca.gov/dataset/continuous-groundwater-level-measurements
| California Department of Water Resources. (November 1, 2025). Groundwater Sustainability Agencies. Retrieved December 4, 2024, from https://water.ca.gov/Programs/Groundwater-Management/SGMA-Groundwater-Management/Groundwater-Sustainable-Agencies |
Purohit, S. (2025). Rainfall in California: Special Reference to 2023 Rains That Caused Floods. Annals of the American Association of Geographers, 115(1), 97–109. https://doi.org/10.1080/24694452.2024.2400078 |
| Water Education Foundation. (n.d.). Sustainable Groundwater Management Act (SGMA). Aquapedia. Retrieved December 4, 2024, from https://www.watereducation.org/aquapedia-background/sustainable-groundwater-management-act-sgma|
