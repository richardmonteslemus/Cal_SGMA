# California Sustainability Groundwater Management Act Analysis

### About

In 2014, California passed the Sustainable Groundwater Management Act (SGMA) aimed at addressing the over-exploitation of groundwater across California (Water Education Foundation, n.d.). The need for groundwater regulation was made urgent by the severe California drought of 2012-2016. This act required local and regional agencies to develop and implement sustainable groundwater management plans. High and medium-priority basins in critical overdraft were required to submit and begin implementing management plans by January 2020, while the rest had until January 2022 (Water Education Foundation, n.d.).

This analysis uses a segmented regression model to evaluate whether groundwater level trends changed after SGMA implementation. The analysis examines water surface elevations from January 2012 through November 2025 for monitoring wells across California operated by the California Department of Water Resources.

### Data limitation

The groundwater level data used in this analysis exhibits several features that affect the statistical analysis:

Seasonality: Groundwater levels fluctuate seasonally, increasing during wet seasons and decreasing during dry periods. This could make it difficult to distinguish seasonal groundwater water depletion from overdrafting.

Autocorrelation not addressed: This analysis does not account for autocorrelation in the regression model. Groundwater levels depend on previous levels. This creates autocorrelation for our response variables. Therefore, groundwater level observations cannot be considered independent. This can affect the reliability of standard errors and significance tests.

Policy Intervention Variation: Not all wells were subject to the January 2020 SGMA Sustainable Groundwater Plan submission and implementation. Some wells had until January 2022 to start implementing their plan. Despite this, a single policy intervention date (January 2020) was used in order to make a single breakpoint for groundwater level observations over time. 

### Repository Structure
```
├── Cal_SGMA.qmd
├── Cal_SGMA.Rproj
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
| Water Education Foundation. (n.d.). Sustainable Groundwater Management Act (SGMA). Aquapedia. Retrieved December 4, 2024, from https://www.watereducation.org/aquapedia-background/sustainable-groundwater-management-act-sgma|
