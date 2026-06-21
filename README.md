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
|   ├── emission_annual.xlsx                EIA emissions source data
│   ├── clean_state_green.csv               cleaned generation by state and year
│   ├── state_summary.csv                   one row per state, used for the ranking comparison
│   ├── clean_state_emissions.csv           generation joined with emissions and carbon intensity
│   └── national_trend.csv                  national green energy share and carbon intensity by year
|
└── dashboard/
    ├── decarbonization.pbix    the Power BI file
    └── screenshots/            dashboard images

The next step is to take CO2 emissions data and evaluate how emissions have varied alongside green energy generation adoption. As green energy generation increases for a state, we should expect lower CO2 emissions, hence an inverse proportional relationship.


Part 2: Green Energy Generation vs. Carbon Emissions

The next step was to bring in CO2 emissions data and check whether greener grids actually emit less. Green energy share (e.g., percentage of total energy generated that is renewable) tells us how clean a state's generation mix is, but it doesn't directly tell us how much CO2 that state puts out. By merging EIA's emissions data to the generation data and calculating carbon intensity (CO2 emitted per MWh generated), we can do that. This puts every state on the same footing regardless of size, and it can be compared directly against green energy share.

The short answer is yes, greener grids do emit less. Across every year, states with a higher green energy share have a lower carbon intensity, and the relationship is strong. Vermont generates almost all of its electricity from green sources and emits next to nothing per MWh, while coal heavy states like West Virginia and Wyoming sit at the opposite end.

At the national level, green energy generation percentage rose from about 31% to 41% while carbon intensity dropped from about 0.63 to 0.35 tons of CO2 per MWh. Interestingly, carbon intensity fell faster than green energy share rose. Part of that is renewables coming online, but part of it is natural gas replacing coal, which emits roughly half the CO2 per MWh. What does this mean? That the grid got cleaner faster than it got "greener."

Data source: EIA, Emissions by State (https://www.eia.gov/electricity/data/state/)