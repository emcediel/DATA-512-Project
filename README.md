# DATA-512-Project

Our goal is to analyze the effect of masking policies in the rate of infection in Oklahoma, OK. We want to understandhow this county progressed through the pandemic, how they got infected through time using timeseries analysis and if possible associate these trends with masking policies that existed during this time in this county. 

## Files inside repo
### Source files (data_raw)
- *U.S._State_and_Territorial_Public_Mask_Mandates_From_April_10__2020_through_August_15__2021_by_County_by_Day.csv*: 
Row per day if there was a mask mandate required. 
- *mask-use-by-county.csv*:
Row per county with the percentages of population with different criteria around the survey about using mask usage.
- *RAW_us_confirmed_cases.csv*:
Row per day with cummulative positive cases.


### Intermediary files (data_clean)

Three csv files were created, each contains data from the original raw files, filtered to Oklahoma, OK and the dates we are interested in. 

- *mask_mandates_OK.csv*: Row per day if there was a mask mandate required in Oklahoma, OK.   
- *mask_use_OK.csv*: One row with the percentages of population with different criteria around the survey about using mask usage. 
- *us_cases_OK.csv*: Row per day with cummulative positive cases in Oklahoma, OK. 


### Output files (results)

1 graph was created:
*timeseries_rate_of_infection_for_Oklahoma, OK.png*: Time series of infection rate for Oklahoma, OK contrasted with CDC masking mandates. 
## Data limitations and special considerations

Not all data sources have full data, some contain nulls in multiple days.  

- *mask_mandates_OK.csv*: 
Data Provided by
Mara Howard-Williams, Public Health Law Program, Center for State, Tribal, Local, and Territorial Support, Centers for Disease Control and Prevention

- *mask_use_OK.csv*:
The source where I retreieved this data asks for the following attribution:
 
 This data is licensed under the same terms as our Coronavirus Data in the United States data. In general, we are making this data publicly available for broad, noncommercial public use including by medical and public health researchers, policymakers, analysts and local news media.
If you use this data, you must attribute it to “The New York Times and Dynata” in any publication. If you would like a more expanded description of the data, you could say “Estimates from The New York Times, based on roughly 250,000 interviews conducted by Dynata from July 2 to July 14.”
If you use it in an online presentation, we would appreciate it if you would link to our graphic discussing these results https://www.nytimes.com/interactive/2020/07/17/upshot/coronavirus-face-mask-map.html.
If you use this data, please let us know at covid-data@nytimes.com.
See our [LICENSE](https://github.com/nytimes/covid-19-data/blob/master/LICENSE) for the full terms of use for this data.

- *us_cases_OK.csv*:
Retrieved from Kaggle, has a [Attribution 4.0 International (CC BY 4.0) ](https://creativecommons.org/licenses/by/4.0/)

