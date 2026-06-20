Green Electricity Generation Analysis by State, 1990 - 2024

The purpose of this project is to investigate how green electricity generation has been adopted by the U.S. from the last 3 decades. The short answer is that the country's energy generation sources went from about 31% in 1990 to 41% in 2024, which doesn't seem like a lot, but this nationwide number hides variation that can only be seen at a more granular level. For instance, some states transformed their grids to clean energy almost completely while others have went 'backwards.'

To start, I have defined green energy as the following: Nuclear, Hdryo, Wind, Solar, Geothermal, Wood, and Other Biomass. Eevrything else is deemed non-green (coal, natural gas, petroleum, etc.)

All data comes from the US Energy Information Administration (EIA), specifically their annual net generation by state.

Source: https://www.eia.gov/electricity/data/state/

Python and pandas were used to load, clean, categorize, and rank the data.
Power BI was used for the interactive dashboard.

The full analysis is in notebooks/analysis.ipynb

Files

decarbonization-by-state/
|
├── README.md
|
├── data/
|   ├── energy-analysis-by-state.ipynb      jupyter notebook analysis
|   ├── annual_generation_state.xls         EIA source data
|   ├── emission_annual.xls                 EIA source data (not used, yet)
│   ├── clean_state_green.csv               cleaned data file, generation by state and year
│   └── state_summary.csv                   one row per state, used for the ranking comparison
|
└── dashboard/
    ├── decarbonization.pbix    the Power BI file
    └── screenshots/            dashboard images

The next step is to take CO2 emissions data and evaluate how emissions have varied alongside green energy generation adoption. As green energy generation increases for a state, we should expect lower CO2 emissions, hence an inverse proprtional relationship.