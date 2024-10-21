# Washington_BEV_analysis
This is a data analysis/data science project reviewing Washington state electric vehicles and impact to power grid

# Executive Summary
Over the past few years, I have seen an increase in the number of electric vehicles where I live (Seattle, Washington). This made me wonder about the energy consumption of these vehicles and do Washington state’s power grid/power plants have the capacity. Currently the short answer is yes. 

As of early September 2024, there are 161,197 electric vehicles in the state of Washington. Assuming that each is fully charged twice a month (based average electric range of 261 miles; average battery size of 69 kilowatts per hour) the additional annual energy draw is 428 gWh. For 2023 the estimated household unit annual energy draw is 43,889 gWh (3.361mm household units for 2023; estimated annual energy usage 13,056 kilowatt-hours). The annual power plant capacity (in aggregate) is 257,352 gWh. 

Total power plant annual capacity = 257,352 gWh
Electric vehicles annual electric use = 428 gWh
Household unit annual use = 43,889 gWh
Surplus of 213,034 gWh

Caveats
1)	This brief based on publicly available information I found through web search and use of Microsoft Copilot and Chat GPT.
2)	This brief does not take into account Washington state’s commercial not industrial energy needs/usage. 
3)	Resources used are noted at the end of this brief.

# Business Problem
Determine how Washington state’s electricity availability is impacted by the increase in electric vehicles.
1)	Define total number of electric cars in Washington state.
   -  By year through 2024
   -  By county
2)	Calculate the increase in kilowatt usage of this population for a year.
 - Define kilowatt-hour usage to charge each electric car.
 - Convert kilowatt-hour to gigawatt-hour.
3)	Define the total number of household units within the state and the annual kilowatt-hour usage for each (kilowatt-hour will need to be converted to gigawatt-hour). 
4)	Identify and determine the total number of power plants (biomass, batteries, coal, hydroelectric, natural gas, nuclear, petroleum, solar, wind) and their collective annual capacity.
  - Convert how energy production in measured: megawatts to gigawatts-hour.
5)	Note – this study is only looking at impact of electric vehicles to available electricity based on residential demands. Industrial and commercial needs were not taken into consideration. Additionally, I want to acknowledge that the increased use of Artificial Intelligence and the electricity needed for compute power (in datacenters run by Microsoft, Google, Amazon, and others) will absolutely impact the availability of electricity in Washington state.

# Methodology
Electric Vehicle Identification
1)	Pulled current electric car population in Washington State for DATA.GOV - https://catalog.data.gov/dataset/electric-vehicle-population-data. This is a csv file - I converted to .xls file. Cleaned data by:
-  Removed all non-Washington state data
-  Updated Electric Range and Base MSRP columns due to missing data. Used MS Copilot and ChatGPT to find data for each car. To keep data consistent, I pulled base model information
   -  Electric range for vehicles
   -  Base MSRP
   -  Base Battery size
   -  Fast DC charging supportability (informational purposes)
-  Added column that highlights kilowatts used to fully charge battery – manually pulled data (kilowatts per battery) per car brand, model, model year using Microsoft Copilot and/or Chat GPT.
-  Aggregated electric vehicle data by county - counties with largest population of battery electric vehicles:
  
![image](https://github.com/user-attachments/assets/a55fa920-8ade-46f8-bf22-fa9e4370f29a)

Power Plant Identification 
1)	Created an Excel file/data set that includes all the power plants in Washington state. This was used to calculate total energy capacity for the state. Added column for county. Leveraged “County” across Excel spreadsheet as a key in the event I wanted or needed to merge data sets. (https://www.zipdatamaps.com/en/us/poi/energy/state/washington/power-plants#table-list)
   
Household Unit Determination 
1)	Through the U.S. Census Bureau, Population Division created a data set of housing units for all of Washington state and by individual counties for the years 2016 thru 2023. (https://www.census.gov/data/tables/time-series/demo/popest/2020s-total-housing-units.html) 
2)	Leveraging Chat GPT found information from the Washington State Department of Commerce, Energy Office (via Chat GPT) showed 2023, the average annual residential electricity usage in Washington state was approximately 13,056 kilowatt-hours (kWh)

# Skills Used
-  Excel – data set manipulation, data cleaning
-  Artificial intelligence – using Microsoft Copilot and Chat GPT to supplement data sets
-  Python -exploratory data analysis (Pandas), data set manipulation, data visualization (GeoPandas, MatPlotLib)

# Results and Business Recommendations
As shared above, the current state of power plant capacity to residential plus electric vehicle needs is in very good shape for Washington state. With that said, a few things to consider could impact the surplus of energy.
1)	Seventy-one of the one hundred and thirty-three power plants are hydroelectric. These plants produce seventy percent of the capacity of all Washington state power plants. If there is a drought then things could be challenging. This is something I’m sure the electric companies and Washington state government have developed contingency plans. I do not have access to that information.
2)	Increases in population could impact the energy grid specifically in the more densely populated area counties of King, Snohomish, Pierce, Thurston, Clark, Whatcom, and Spokane counties. State and local governments as well as energy companies most likely have planned for. 
3)	Washington state passed the “Move Ahead Washington” bill in 2022 which states that all 2030 model year cars sold, purchased, or registered in the state are to be electric. (https://www.nbcnews.com/news/us-news/washington-state-plans-ban-non-electric-vehicles-2030-rcna21683). This will, over time, impact the state’s annual surplus capacity and should be on the government’s radar to plan for additional energy sources. 

# Additional Deep Dive Opportunites
1)	Marketing and sales of electric vehicles: Year over year sales of electric vehicles have been trending up since 2017 with large increases of 51% for 2021, 52% for 2022, and 119% for 2023. The largest concentrations of sales are in King County, Snohomish County, and Pierce County. This makes sense as King County hosts office space for Microsoft, Amazon, Google, Meta, Costco and others.  Large number of employees of these companies have stock options with a typical vesting cycle of five years. Over the past 5 years these companies’ stock prices have increased 50% to 270%. Deep dive into county demographics to understand potential buyers and strategic planning for 2024 through 2027/28.
   
2)	Entrepreneurial-minded folks will have an interest in this report as the number of privately and governmental owned charging stations has not, in my opinion, kept up with the increase in EV sales. As of September I found there to be a total of 2,150 charging stations throughout the state. My feeling is there is opportunity to service the increasing need for EV charging stations as state drivers transition from combustion engines to electric (with the help of Washington’s “Move Ahead Washington” bill. A deep dive leveraging this brief with additional data analysis of traffic flow, current EV charging station locations/mapping, data on current usage, cost to develop, and anticipated ROI from operations needs to be done. 

3)	The lion’s share of the “EV population” are in counties of King, Snohomish, Pierce, Thurston, Kitsap, Whatcom, Clark, and Spokane. This makes sense as these counties have the largest population sizes, higher income, and near urban areas. With the Move Ahead Washington bill coming in 2030 how will the other counties that don’t have the infrastructure nor income afford electric vehicles be impacted? This is an opportunity for politicians, who represent these counties, to study and plan ways to help their respective communities.   

4)	Government and Power Companies: Deep dive analysis of energy requirements for datacenters – increased energy consumption due to AI and increased compute needs. Based on my research there are 67 data centers in Washington state. From news reports data centers that host AI compute draw a significant amount of energy – I don’t have access to actual numbers. A broad question to be answered is how this will impact energy availability for Washington residents. 

# Resources
Electric Vehicle Population Data – Washington - https://catalog.data.gov/dataset/electric-vehicle-population-data 
Vehicle Title Transactions by Department of Licensing | Data.WA | State of Washington

Power plants in Washington State - https://www.zipdatamaps.com/en/us/poi/energy/state/washington/power-plants#table-list
Northwest Power and Conservation Council Map - https://www.nwcouncil.org/energy/energy-topics/power-supply/map-of-power-generation-in-the-northwest/

“Move Ahead Washington” bill - https://electrek.co/2022/03/25/washington-passes-bill-targeting-all-electric-car-sales-by-2030-for-real-this-time/

EV cars in Washington State ( https://catalog.data.gov/dataset/electric-vehicle-population-data

Median Household Income in Washington state by county  - https://ofm.wa.gov/washington-data-research/economy-and-labor-force/median-household-income-estimates 
Washington State Energy Profile - https://www.eia.gov/state/print.php?sid=WA 
1)	As of February 2024 – 2,150 EV charging stations with 5,900 ports
 
Housing Unit Estimates for Washington - https://www.census.gov/data/tables/time-series/demo/popest/2010s-total-housing-units.html and https://www.census.gov/data/tables/time-series/demo/popest/2020s-total-housing-units.html

Washington State Department of Commerce, Energy Office (via Chat GPT) showed for 2023 the average annual residential electricity usage in Washington state was approximately 13,056 kilowatt-hours (kWh). This figure is based on an average monthly consumption of about 1,088 kWh


   
