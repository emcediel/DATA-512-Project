# DATA-512-Project for Oklahoma County, OK.

## Part I - Common Analysis

Our goal is to analyze the effect of masking policies in the rate of infection in Oklahoma, OK. We want to understand how this county progressed through the pandemic, how they got infected through time using timeseries analysis and if possible associate these trends with masking policies that existed during this time in this county. 

## Part II & III & IV - Individual Analysis

Given that this is a free research project and that we really want to try to find important insights that might help society. I first searched in the worldwide web for the different data sources that Oklahoma County had to offer and found many areas that could potentially be used for analysis such as diversity, economy, civic, education, housing & living, health, etc. Given that I wanted to focus on areas that had greater impact in our society due to the pandemic, I decided to narrow my search to only economical and health data. After quickly checking and analyzing some of the economic data, I grew interest in it as it is an area that is indirect to COVID but at the same time I’m very positive it got truly hit by it. I would like to know in depth how hard did the pandemic affected the economy inside Oklahoma county, how much relationship there is and if there were any actions taken by the county to counter any changes. To do this, I found two interesting indicators of economy, unemployment insurance claims and employment by industry sector that will be the basis of my analysis to answer the following research questions and hypothesis:

Research question: What effect on employment did the pandemic generate inside Oklahoma county? Is there any trend or correlation between employment statistics and confirmed COVID cases in Oklahoma county?
Hypothesis: I expect to see multiple effects between employment and the pandemic, specifically I consider:
1.	The highest peak of unemployment occurred right at the beginning of the pandemic; this initial peak can be up to 30x the average rate of unemployment for the previous year before the pandemic.
2.	The industry sectors that got the heaviest unemployment rates were leisure & hospitality as well as other heavy blue collar job industries.
3.	Is working in Finance or Government sectors a safer bet when facing pandemic layoff?
4.	After 1 year of pandemic, all sectors have been able to recuperate at least 80% of their layoffs.

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

- *employment_by_sector_OK_cases_part_2.csv*: Monthly employment data with monthly confirmed COVID cases merged month-by-month for Oklahoma County.
- *employment_by_sector_OK_part_2.csv*: The source data is already filtered by Oklahoma, OK. We want to filter such that it's between January 1, 2017 through October 1, 2021. For this table we retieve 1 year more (2017) given that we will later calculate Year-over-Year data.
- *mask_mandates_OK.csv*: Row per day if there was a mask mandate required in Oklahoma, OK.   
- *mask_use_OK.csv*: One row with the percentages of population with different criteria around the survey about using mask usage. 
- *unemployment_OK_cases_part_2.csv*: Weekly Unemployment data with weekly confirmed COVID cases merged week-by-week for Oklahoma County.
- *unemployment_OK_part_2.csv*: WA table with a week date per row, so we filter for Oklahoma, OK. We also want to filter such that it's between January 1, 2018 through October 1, 2021. Additionaly, we want to know the week number.
- *us_cases_OK.csv*: Row per day with cummulative positive cases in Oklahoma, OK. 
- *us_cases_OK_part_2.csv* : A table with a date per row, so we filter for Oklahoma, OK and then we unpivot the table. We also want to filter such that it's between January 1, 2017 through October 1, 2021. For this table we retieve 1 year more (2017) given that we want to be able to match (inner join) with employment_by sector table

### Output files (results)

9 graphs were created:
*Bar plot of post-pandemic percentage of recovered layoffs by sector.png*: Self-explanatory title.
*Box plot: Post-pandemic YoY monthly growth of all sectors Post-pandemic YoY monthly growth of all sectors.png*: Self-explanatory title.
*Box Plot: Pre vs. post pandemic YoY weekly growth of unemployment claims.png*: Self-explanatory title.
*Box Plot: Pre vs. post vs. new-normal YoY weekly growth of pandemic unemployment claims.png*: Self-explanatory title.
*Line plot of confirmed COVID cases vs. employment by sector (monthly).png*: Self-explanatory title.
*Line plot of confirmed COVID cases vs. employment by sector YoY growth (monthly).png*: Self-explanatory title.
*Line plot of confirmed COVID cases vs. unemployment insurance claims (weekly).png*: Self-explanatory title.
*Normality assumption check for Weekly Unemployment Growth.png*: Self-explanatory title.
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

### Additional data sources for part II, III, IV:

All additional data sources come from datausa.io: 

**Unemployment Insurance Claims (API retrieved in notebook)**
Source: https://datausa.io/about/api/
Time series containing monthly employees per sector for Oklahoma county (not-seasonally adjusted) between December 2017 and April 2021. 

**Employment by Industry Sector (API retrieved in notebook)**
Source: https://api-ts-vibranium.datausa.io/tesseract/ This data has already been filtered for Oklahoma, OK in the requests URL.
Time series containing weekly unemployment insurance claims in Oklahoma county (not-seasonally adjusted) between January 2018 and September 2021.

### datausa.io usage, permissions and licensing:

In the following link: https://datausa.io/about/usage/, datausa.io specifies all licence/terms of use required to use this data, they allow access to this data for educational purposes, it is presented under the following [GNU Affero General Public Licence v3.0 (GPLv3)](https://www.gnu.org/licenses/agpl-3.0.txt). The content can be copied, downloaded for own use provided that suitable acknowledgment of Data USA as source is given.

**datausa.io disclaimers:**

nformation on this site is provided on an "as is" and "as available" basis. Data USA makes every effort to ensure, but does not guarantee, the accuracy or completeness of the information on the Data USA website(s). Our goal is to keep this information timely and accurate. If errors are brought to our attention, we will try to correct them.

Data USA may add, change, improve, or update the information of the website without notice. Data USA reserves its exclusive right in its sole discretion to alter, limit or discontinue part of this site. Under no circumstances shall Data USA be liable for any loss, damage, liability or expense suffered which is claimed to result from use of this site, including without limitation, any fault, error, omission, interruption or delay. Use of this site is at User's sole risk.

We make every effort to minimize disruption caused by technical errors. However some data or information on Data USA website(s) may have been created or structured in files or formats which are not error-free and we cannot guarantee that our service will not be interrupted or otherwise affected by such problems. Data USA accepts no responsibility with regards to such problems (failure of performance, computer virus, communication line failure, alteration of content, etc.) incurred as a result of using Data USA website(s) or any link to external sites.

The User specifically acknowledges and agrees that Data USA is not liable for any conduct of any other User, including, but not limited to, the types of conduct listed above.

Data USA reserves the right to deny at its sole discretion any User access to Data USA website(s) or any portion thereof without notice.

For site security purpose and to ensure that Data USA website(s) remain(s) available to all users, it (they) employ(s) software programs to monitor network traffic to identify unauthorised attempts to upload or change information, or otherwise cause damage and to detect other possible security breaches.

For more information about these additional datasources visit: https://datausa.io/about/usage/
